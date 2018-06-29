---
layout: post
title:  "Using ES6's Proxy for safe Object property access"
date:   2016-02-07 13:10:00 +0100
---
{::options parse_block_html="true" /}
<section class="cl2">
I can’t get over the feeling that ES6 (still refusing to say ES2015 ^_^) is a kind of playground offering me all these new toys and attractions to play around with.
Currently my focus is on exploring the Proxy object which gives us a new way to intercept fundamental operations on Objects, among them property access, which is something I want to play around with today.

**TL/DR**
Sick and tired of accessing a nested object under a property in a deep object just to have the ***Uncaught TypeError: Cannot read property ‘foo’ of undefined*** thrown in your face?
Well, by using a Proxy you can get around those errors without excessive key checking in a reusable manner.
The code example for doing this is down bellow, an **npm** module is available via ***npm install safeobj***, with the source on [Github](https://github.com/gmmorris/safeobj).
</section>

<section>
## Making our object access safe
Suppose we have an object describing Darth Vader and a function which receives a person and returns his father’s name.
How do we prevent this code from throwing an error?
</section>

```javascript
const DarthVader = {
  name : 'Anakin',
  mother : {
    name : 'Shmi'
  }
}

function getFatherName(person) {
  return person.father.name
}

// Throws the error:
// Uncaught TypeError: Cannot read property ‘name’ of undefined
let darthVadersFather = getFatherName(DarthVader)
```
### What have we seen before?
<section class="cl2">
There are lots of ways to make your object access safe from undefined properties. These have been extensively covered in other articles and usually involve either the approach of describing the deep property access as a string, or by wrapping your object in a “functional” wrapper (Such as a Functor) and abstracting away the access operation that way.

The Functor example is a little complicated to give an example of, so I suggest you read up using my favourite book on the subject, which is [Professor Frisby’s Mostly adequate guide to FP](https://github.com/MostlyAdequate/mostly-adequate-guide) (specifically what you want are **Maybe, Either, Left** and **Right**), but here is an example using a string to make safe deep object property access.
</section>

```javascript
const DarthVader = {
  name : 'Anakin',
  mother : {
    name : 'Shmi'
  }
};

function deepAccessUsingString(obj, key){
  return key.split('.').reduce((nestedObject, key) => {
    if(nestedObject && key in nestedObject) {
      return nestedObject[key];
    }
    return undefined;
  }, obj);
}

let mothersName = deepAccessUsingString(DarthVader, 'mother.name');
let fathersName = deepAccessUsingString(DarthVader, 'father.name');
  
console.log(mothersName); // prints "Shmi"
console.log(fathersName); // prints undefined 
```
<section class="cl2">
The approach I’d like to show you today is more in line with the Functor approach, but doesn’t require you to delve deep into the functional world of monads, lenses etc. (I would actually *highly* recommend you do do that, because its a wonderful ecosystem and paradigm, but if you don’t want to, this Proxies approach is a nice half step in that direction).

### How can we do this using a Proxy?

The solution is loosely based on the functional approach where we add an intermediary layer between the actual property access and the actual act of accessing the object’s property. This is exactly what proxies are designed for and we can do this by catching every “get” operation on the object, and every subsequent “get” operation on its nested objects as it digs deeper into the original complex object.

We start by defining some helper functions, which you might not need to do if you have a utility library you’re using (such as lodash or underscore), but to keep this example simple we’ll implement these ourselves with a couple of helper functions:
</section>

```javascript
const isObject = obj => obj && typeof obj === 'object';
const hasKey = (obj, key) => key in obj;

const Undefined = new Proxy({}, {
    get: function(target, name){
        return Undefined;
    }
  });
const either = (val,fallback) => (val === Undefined? fallback : val);
```

<section class="cl2">
These helpers are quite straight forward (lodash has equivalents for both):
**isObject** simply receives a variable and returns true or false, depending on whether it is in fact an Object.
**hasKey** receives an object and checks whether it has a property under a specific name.

Next we have a a dead simple object, sillily called **Undefined**. This is a ***terrible*** name for a variable, and I’d advise against using it for anything other than a code example like this, but I used it to express a clear idea which is that this object is, logically, equivalent to an *undefined property*.
The way ***Undefined*** works is that it is a proxy to an empty object, but every property access on that proxy will, in turn, return the proxy itself, so essentially what we have is circular reference from the object to itself, through any property access on it.
**either** is a small sort of predicate operation which receives a variable, checks wether it is, in fact, an *Undefined Property* value and if it is, returns a fallback value, otherwise it returns the original value and acts sort of like the *[identity](https://lodash.com/docs#identity)* function.

Now that we have these utilities its a small step towards implementing a proxy which will make our object access safe:
</section>

```javascript
function safe(obj) {
  return new Proxy(obj, {
    get: function(target, name){
      return hasKey(target, name) ? 
        (isObject(target[name]) ? safe(target[name]) : target[name]) : Undefined;
    }
  });
}
```

<section class="cl2">
What this little function does is receive an object and return a proxy for this object which implements a very simply wrapper for property access.
Whenever a property is accessed on the proxy, it will check whether that property exists and do one of two things:
If that property **exists** it will either return the value or, of its an object, wrap it in a new ***safe* **proxy and return it in place of the nested object.
If, though, the required property doesn’t exist, we’ll return our **Undefined** object (instead of the regular value we’d usually receive in such a situation, which is Javascript’s internal *undefined* type).

Now, what we get is the ability to dig deep into an object, including undefined properties, so that, if we continue with our **Darth Vader** example, we get the following behaviour:
</section>

```javascript
const mySafeObj = safe({
  name : 'Anakin',
  mother : {
    name : 'Shmi'
  }
});

// returns "Anakin"
console.log(mySafeObj.name);

// returns "Shmi"
console.log(mySafeObj.mother.name);

// returns a reference to Undefined (our Undefined, not Javascript's undefined)
console.log(mySafeObj.father.name);

// returns our fallback value, of false
console.log(either(mySafeObj.father.father.name, false)); 
```

<section class="cl2">
What you can see is a wonderful little piece of proxy usage, which allows us to access our object’s properties regularly, but if we access any kind of undefined property, we’ll get back a reference to our custom Undefined object.
Using the ***either*** function we can then write some very concise code which asks for a value on our object, without the danger of a TypeError, but also without having to type check for the **Undefined** type, and instead simply provide the fallback value we want to receive instead in the case that the property is actually missing.

In the last line in that example you can see that we can go quite a bit deeper without any danger. Its pretty cool, if you ask me.
</section>

## The downsides

<section class="cl2">
There are actually some downsides to this approach, which you should be aware of.

**The first**, and most obvious one, is that Proxies are hardly available at this stage. Happily **Firefox** and **MS Edge** (oh, how the tables have turned) have a full implementation for us to use, but **Chrome** has only just added a version compliant with the ES6 spec (version 49, which is still in Beta channel only) and other browsers are [still way off](http://caniuse.com/#search=proxy).

**The second**, and most important one, is that this essentially requires a new Proxy object to be created on every property access operation in the chain. This can have major costs in object allocation and performance. There are ways to improve this, for example, by replacing the nested objects under the properties with **safe** objects as well.
This approach is experimental and has some more work to do in order to be production ready, but its a nice start.
</section>

## Bottom line

ES6 is awesome, have fun with it!
Here is the original problematic example I gave, using the safe access function as a solution.

```javascript
const safeDarthVader = safe({
  name : 'Anakin',
  mother : {
    name : 'Shmi'
  }
});

function getFatherName(person) {
  return person.father.name
}
function getName(person) {
  return person.name
}


let darthVadersFather = either(
  getFatherName(safeDarthVader),
  `${getName(safeDarthVader)} has no father`
);

// Prints 'Anakin has no father'
console.log(darthVadersFather);
```
