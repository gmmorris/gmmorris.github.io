---
layout: post
title:  "The Structured Reasoning Of Searching Through Structured Logging"
date: 2019-02-01 22:16:08 +0100
tags: JSON, grep, jq, logging, structured-logs
icon: terminal
description: "Why I created a command-line JSON processor."
banner: banner-occult
banner-desc: "The history of the devil and the idea of evil; from the earliest times to the present day"
banner-img: "/assets/img/banners/historydevil.png"
banner-desc-link: "https://www.flickr.com/photos/internetarchivebookimages/14773757364"
---
{::options parse_block_html="true" /}
<section>
I'm not one to advocate for _SSH_-ing into a server and manually sifting through logs.

I'm a big believer in investing in your logging structure & infrastructure at a level that allows you to offload the log sniffing and analysis to a more suitable time and place.

That said, there are still times when I find myself piping around log files on remote servers. Recently, feeling fed up with one of the more tedious examples of this, I threw together a little tool that I think might be of use to others as well.
</section>

# A Shed Load Of JSON
<section>
As I've mentioned before a core part of my job is to maintain a distributed system of Ad Exchanges. These Exchanges run _real-time bidding_ auctions in which we offer buyers the opportunity of buying advertising real-estate.

Each auction produces a large amount of information which we log into files. These logs are used both for monitoring and in order to support analysis at a later time. As our Ad Exchanges communicate with the outside world by using the [openRTB specification](https://www.iab.com/guidelines/real-time-bidding-rtb-project/), a superset of the JSON format, we chose to log everything that happens within the exchanges as structured JSON as well.

There is a whole variety of events which we wish to log when an auction executes, ranging from an _auction start_ event, when an auction begins, through to _bid requests_ and _bid responses_ which describe the back-and-forth communication with potential buyers of advertising real-estate, and of course a whole variety of follow up events such as a _bid won_ or _bid rejected_ event.

Whenever an event takes place within an Ad Exchange we write a JSON object into a log file containing all the metadata about the event. We try to enrich the log with as much information as possible, empowering ourselves and our analysts by enabling all sorts of business-related questions to be asked about what is happening within out system.

Ever wondered how often certain buyers bid on certain kinds of real-estate? No problem, thanks to these structured logs, we can analyse these events using third-party tools long after they took place in our system. Shortly after these log files are created on a server they get aggregated into a system maintained by our _Sh↑ft_ team who own all our <u>sh</u>ared <u>i</u>n<u>f</u>ras<u>t</u>ructure (hence the name), which streams these logs into a variety of such reporting tools.
</section>

# grep-ing JSON Is A Pain
<section>
Sometimes though, I might wish to take a look at these logs while they still reside on an Ad Exchange. There are several reasons why I might chose to do that.

For example, I may wish to get immediate feedback about something that is happening on an exchange (as it can take some time for the sheer amount of data to reach our reporting services). 

Another example would be a case where I was investigate a discrepancy which, as I suspected at the time, was caused by an error in the creation of our structured logs rather than a real world error taking place within the Ad Exchange. Sifting through the logs confirmed that theory quite quickly.

When such a situation occurs I will usually _SSH_ into one of our Ad Exchanges and use a variety of command-line tools to take a closer look at these log files, predominantly _grep_ and _jq_.

**grep** is a tool which allows you to <u>g</u>lobally search through text files using <u>r</u>egular <u>e</u>xpressions and <u>p</u>rint out every matching line. 

**jq** on the other hand is a tool used to dig into JSON structures and manipulate them. This tool is very useful if you're trying to _extract_ data out of a complicated JSON object.

## Why Is grep Unfit For Purpose?
I heavily use both of these tools, but often find both mildly infuriating as they will often fall short of my needs. Generally speaking, I use these tools when I'm searching for an answer to a business related question. For example, I might ask the question: "Are we getting any _bid responses_ which include bids on a specific _Private Marketplace Deal_, which have an _Ad Id_ on them and can be _skipped_?".

In order to answer this question I need to find all the logged events written to the log when an Ad Exchange receives a _Bid Response_ bidding to buy some space offered as part of a specific _deal_ in order to place a _skippable_ video ad in it.

I know, that's a whole load of vague domain knowledge that means nothing to you, so let me clarify what this means.

A _Bid Response_ is logged as a JSON structure which describes a bid by a potential buyer in an auction. In this bid the buyer can specify a variety of properties describing the use they would like to make of our advertising real-estate (in the case that they win the auction). Two such properties are a property specifying that they would like to buy this real-estate as part of a prenegotiated _deal_ offered on our _private marketplace_, and an attribute specifying that we should offer the end user an opportunity to _skip_ this ad if they would like to.

Bellow is an example of a logged event matching what I'm looking for:

```json
{
	"id": "300eb402-3a4d-3486-b2e3-9d2a2ba53ebc",
	"seatbid": [{
		"bid": [{
			"id": "1",
			"impid": "300eb402-3a4d-3416-b2e3-9d2a2ba53ebc",
			"price": 8.49,
			"adid": "8756987",
			"adm": "<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>",
			"adomain": ["gidi.io"],
			"dealid":"UNRX-GIDI-9d2a2ba53ebc",
			"attr": [16],
		}],
		"seat": "10000001"
	}],
	"cur": "USD"
}
```

The important parts of this _bid response_ are the following:
1. The _dealid_ field which described the ID of the Deal the bidder would like to buy under. In this case: _UNRX-GIDI-9d2a2ba53ebc_.
2. The value _16_ specified in the _attr_ field, which is a _Creative Attribute_ as described in the _openRTB_ specification, tells us that this ad should be _skippable_.

If I were to try and use _grep_ to find this JSON object in the logs I would have to try and use strings patterns to try and match with these fields.

Suppose, hypothetically, we had these events in a file called _bidresponses.json_ which contained a whole load of _bid responses_, finding the bids on the _deal_ would be easy:

```
$ grep 'UNRX-GIDI-9d2a2ba53ebc' bidresponse.json
```

```
{"id":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","seatbid":[{"bid":[{"id":"1","impid":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","price":8.49,"adid":"8756987","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"788be2a1-6c3a-3416-b2e3-867t786f57f5","seatbid":[{"bid":[{"id":"1","impid":"788be2a1-6c3a-3416-b2e3-867t786f57f5","price":2.49,"adid":"6736787","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidm.co.uk"],"dealid":"UNRX-GIDI-9d2a2ba53ebc"}],"seat":"10000001"}],"cur":"USD"}
```

As you can see our _grep_ command matched two bids on our _deal_, but only the first is _skippable_.

Identifying the _attr_ begins to get complicated. For example:

```
$ grep -E '(UNRX-GIDI-9d2a2ba53ebc|16)' bidresponse.json
```

```
{"id":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","seatbid":[{"bid":[{"id":"1","impid":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","price":8.49,"adid":"8756987","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"788be2a1-6c3a-3416-b2e3-867t786f57f5","seatbid":[{"bid":[{"id":"1","impid":"788be2a1-6c3a-3416-b2e3-867t786f57f5","price":2.49,"adid":"6736787","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidm.co.uk"],"dealid":"UNRX-GIDI-9d2a2ba53ebc"}],"seat":"10000001"}],"cur":"USD"}
{"id":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","seatbid":[{"bid":[{"id":"1","impid":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","price":7.49,"adid":"8762655","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[15, 16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"ca3c53a1-207f-485d-9c19-bac702b1b06f","seatbid":[{"bid":[{"id":"1","impid":"ca3c53a1-207f-485d-9c19-bac702b1b06f","price":3.09,"adid":"20044561","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["wwf.org.uk"],"attr":[16]}],"seat":"623234"}],"cur":"USD"}
```

Sadly that didn't work either. As the number _16_ appears in both the _attr_ field and in other places, such as a bid's unique identifier, some irrelevant events are printed too. Not only that, but this also matched a _bid response_ which wasn't on the deal at all, but happened to be _skippable_.

At this point you might try the following:

```
$ cat bidresponse.json | grep 'UNRX-GIDI-9d2a2ba53ebc' | grep '16'
```

```
{"id":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","seatbid":[{"bid":[{"id":"1","impid":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","price":8.49,"adid":"8756987","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"788be2a1-6c3a-3416-b2e3-867t786f57f5","seatbid":[{"bid":[{"id":"1","impid":"788be2a1-6c3a-3416-b2e3-867t786f57f5","price":2.49,"adid":"6736787","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidm.co.uk"],"dealid":"UNRX-GIDI-9d2a2ba53ebc"}],"seat":"10000001"}],"cur":"USD"}
{"id":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","seatbid":[{"bid":[{"id":"1","impid":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","price":7.49,"adid":"8762655","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[15, 16]}],"seat":"10000001"}],"cur":"USD"}
```

This solves the problem of matching the _bid responses_ that aren't on the deal, but still matches the random _16_ that appear in the object.

You might then try to match the end of the array too:

```
$ cat bidresponse.json | grep 'UNRX-GIDI-9d2a2ba53ebc' | grep '16\]'
```

```
{"id":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","seatbid":[{"bid":[{"id":"1","impid":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","price":8.49,"adid":"8756987","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","seatbid":[{"bid":[{"id":"1","impid":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","price":7.49,"adid":"8762655","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[15, 16]}],"seat":"10000001"}],"cur":"USD"}
```

This worked, as we lucked out and _16_ was at the end of the array, but what if a random _bidder_ were to order these differently and instead of _[15,16]_ they would have sent _[16,15]_? Or what if some other field had an array with the value _[16]_ which doesn't neceserily describe _skipability_?

And we haven't even began to check for the presence of an _Ad ID_ which appears under the _adid_ field.

Clearly, answering this question using _grep_ is very hard as the shape of our logs can be quite complex. Using the expressions supported by _grep_ can get very unwieldily complex when trying to match up with these shapes and while _jq_ is great for focusing in on certain parts of these logs, it isn't great for getting the big picture in which those parts reside.

Clearly the issue is deeper:
> There isn't much point having structured logs if you can't reason about them in a structured manner.

So I made a tool which would allow me to do so.
</section>

# jgrep - grep for JSON
<section>
I began to think about the complex questions I often ask when sniffing around in these logs and came to the following conclusions:
1. I need a tool that could describe a _JSON structure_ and match input against this structure
2. I need complex ways of describing not just the shape, but the data itself as well, ideally so I can identify  _containment_ or _exact values_
3. I need an API which will feel intuitive. A hard endeavour indeed as _intuitive to me_ isn't necessarily _intuitive to you_.

In order to address these points as well as possible I chose to emulate existing patterns I'm already familiar with and which are familiar to people working in a similar context to mine.

The first pattern to emulate was, obviously, the tools we we're already using - **jq** and **grep**.

The command-line API for my tool is as close to that of **grep** as possible.
The various flags, such as _-c_ (print count) and _-i_ (ignore case), are the same.
The ability to either _pipe_ input into **jgrep** or specify a specific file are supported too.

You get the idea.

As we saw earlier, using regular expressions doesn't make sense when trying to describe the shape of JSON input. **jq** solves this by specifying a syntax of _filters_ which allows you to dig deep into JSON objects. Instinctively you might think I should adopt the **jq** syntax but I actually decided against that for two reasons.

The first reason was that these filters are quite clearly geared towards slicing apart a JSON objects, rather than matching to them. This makes the syntax quite complex at times and unfit for my purposes.

The second reason is that, to be blunt, I don't find the **jq** syntax intuitive and always find myself looking things up in the documentation no matter how often I use the tool.

Instead I chose to emulate another syntax which I have been using to _match shapes_ for many years and am highly familiar with: _CSS Selectors_.

While the structure of _HTML Documents_, which is what _CSS Selectors_ are optimised for, is very differently from JSON structures, I could see enough similarities and I felt it would be quite intuitive to people who are used to both JSON and CSS, such as the web development community.

The project's [readme](https://github.com/gmmorris/jgrep) documents the entire syntax in detail. I'd appreciate feedback on this syntax, so please do tell me how intuitive you actually find it.
</section>

# Using jgrep To Answer The Question
<section>
So how would you use **jgrep** to answer the question I asked above? Can we find all the _bid responses_ which include bids on a specific _Private Marketplace Deal_, have an _Ad Id_ on them and can be _skipped_?"

Like so:

```
$ cat bidresponse.json | jgrep '{"dealid":"UNRX-GIDI-9d2a2ba53ebc"}' | jgrep '.adid'  | jgrep '{"attr":[16]}' 
```

```
{"id":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","seatbid":[{"bid":[{"id":"1","impid":"300eb402-3a4d-3486-b2e3-9d2a2ba53ebc","price":8.49,"adid":"8756987","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[16]}],"seat":"10000001"}],"cur":"USD"}
{"id":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","seatbid":[{"bid":[{"id":"1","impid":"cd56c8ce-7ed6-49b6-84f5-689dd5315196","price":7.49,"adid":"8762655","adm":"<?xml version=\"1.0\" encoding=\"UTF-8\"?><VAST version=\"2.0\"></VAST>","adomain":["gidi.io"],"dealid":"UNRX-GIDI-9d2a2ba53ebc","attr":[15, 16]}],"seat":"10000001"}],"cur":"USD"}
```

As you can see in this example, just like _grep_, we can combine searches by piping _jgrep_ commands into one another. Effectively this narrows our results down by filtering down the results using one pattern and then handing those over to another search with another pattern.

If, on the other hand, you want to print events that match one of multiple patterns (an _OR_ relationship, instead of _AND_) then you can use the _-e_ flag... again, just like _grep_.

So for example, if you wanted to find _bid responses_ that _either_ have an Ad ID _or_ have the specified deal ID, you could use the following:

```
$ jgrep -e '{"dealid":"UNRX-GIDI-9d2a2ba53ebc"}' -e '.adid' bidresponse.json
```
</section>

# Using jgrep On Bid Requests
<section>
To better showcase the benefit of using **jgrep** lets take a look at _openRTB_'s _Bid Request_, which is a somewhat more complex entity than the _Bid Response_.

_Bid Requests_ are an entity that the _Ad Exchange_ sends to potential buyers in order to offer them the opportunity of buying advertising real-estate. We're talking about a structure that can be vastly different depending on the ad format on offer, the type of the real-estate and a variety of other factors.

For example, here is a _Bid Request_ offering the opportunity of purchasing space on a publisher's site in which a video ad could be displayed in one of those annoying floating spaces.

```json
{
	"id": "521fc063-7db1-4bd3-a6f2-d457d46f8c3e",
	"imp": [{
		"id": "521fc063-7db1-4bd3-a6f2-d457d46f8c3e",
		"video": {
			"mimes": ["video/mp4", "application/javascript"],
			"minduration": 1,
			"maxduration": 7200,
			"protocols": [2, 5, 3, 6],
			"w": 375,
			"h": 603,
			"startdelay": 0,
			"linearity": 1,
			"sequence": 1,
			"boxingallowed": 1,
			"api": [2],
			"placement": 5
		},
		"displaymanager": "in_article",
		"displaymanagerver": "1.0",
		"instl": 1,
		"bidfloor": 5.82,
		"bidfloorcur": "USD",
		"secure": 1,
		"pmp": {
			"deals": [{
				"id": "UNRX-GIDI-1",
				"bidfloor": 4.00,
				"bidfloorcur": "USD",
				"at": 2
			}, {
				"id": "UNRX-GIDI-2",
				"bidfloor": 4.00,
				"bidfloorcur": "USD",
				"at": 2
			}],
			"private_auction": 0
		}
	}],
	"device": {
		"ua": "Mozilla/5.0 (iPhone; CPU iPhone OS 8_4_1 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) GSA/8.0.57838 Mobile/12H321 Safari/600.1.4",
		"ip": "00.000.00.000",
		"geo": {
			"country": "GBR"
		},
		"devicetype": 1
	},
	"user": {
		"ext": {
			"consent": ""
		}
	},
	"site": {
		"id": "08700a49-c92d-4b90-9f76-c7f2d514f86b",
		"domain": "www.gidi.io",
		"page": "https://www.gidi.io/",
		"ref": "https://www.google.co.uk/"
	},
	"at": 2,
	"allimps": 0,
	"bcat": ["IAB25-1", "IAB25-2", "IAB25-3", "IAB25-4", "IAB25-5", "IAB26-1", "IAB26-2", "IAB26-3", "IAB26-4", "IAB9-9"],
	"badv": ["noads.com"],
	"regs": {
		"ext": {
			"gdpr": 1
		}
	}
}
```

This is a relatively simple _Bid Request_ if you can believe it.

Bellow are a variety of example _jgrep_ cli calls that would match the above _bid request_. If you're unsure how the pattern works I suggest looking at the shape of the _Bid Request_ and finding the specified fields in the structure, hopefully it will make more sense then.

The following will match any JSON object that has an object under the key _"site"_ which has a key "ref":

```
$ jgrep '.site.ref' bidrequests.json
```

The following will match any JSON object that has a key _"country"_ whose value is _"GBR"_, meaning the user is located in Britain:

```
$ jgrep '{"country":"GBR"}' bidrequests.json
```

The following will match any JSON object that has a key _"pmp"_ followed by a key _"deals"_ whose value is a _non-empty_ array:

```
$ jgrep '.pmp.deals[.]' bidrequests.json
```

Following from the last example, this will only match if the array of deals has a deal with the id "UNRX-GIDI-2":

```
$ jgrep '.pmp.deals[{"id":"UNRX-GIDI-2"}]' bidrequests.json
```

More often than not I need to search for events which match several different things at once.

For example, what if I want to find all the _Bid Requests_ which were offered for:
1. A user using a mobile device (denoted by _devicetype_=_1_)
2. The browser being used by the user is the _Google Search App_ (denoted by _GSA_ appearing in the User Agent)
3. The user is located in _Britain_
4. The space on offer for the Video Ad is a full screen placement (denoted by _instl_=_1_)

```
$ cat bidrequests.json |              
  jgrep '.device{"devicetype":1}' |   
  jgrep '.device{"ua"*:"GSA/"}' |     
  jgrep '{"country":"GBR"}' |         
  jgrep '.imp[{"instl":1}]'
```
</section>

# Conclusion
<section>
The most important take away for me has been that structured logging opens up a whole world of options when you want to analyse what is going on in your system. But as I said earlier: **There isn't much point having structured logs if you can't reason about them in a structured manner in the place where you need them**.

Feel free to play around with **jgrep** and submit a [pull request](https://github.com/gmmorris/jgrep) if you spot an error or have an improvement to offer.

For example, if you look at that last example I gave, you might have noticed that even though the _devicetype_ and _ua_ fields are on the same _device_ object, you can't match against both at the same time. Ideally you would be able to do something like ```jgrep '.device{"devicetype":1,"ua"*:"GSA/"}'``` which would definitely be more intuitive. This is just one example of a still missing feature which I'll be more than happy to receive a [pull request](https://github.com/gmmorris/jgrep) for.

I haven't yet published the cli tool to _Homebrew_ or _APT_, but I hope to do so once I feel the tool is mature enough. In the meantime you can download the latest release on [Github](https://github.com/gmmorris/jgrep).
</section>