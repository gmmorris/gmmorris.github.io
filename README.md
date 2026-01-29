# gmmorris.github.io

My Jekyll-powered blog. This README shows how to run it locally on macOS and common commands you'll use while developing.

## Prerequisites
- Ruby (preferably via Homebrew: `brew install ruby`) 
- Bundler (`gem install bundler`)
- Jekyll is provided via the Gemfile; you don't need to install it globally.

## Quick Start
1. Install dependencies:

```bash
bundle install
```

2. Serve locally (default at http://localhost:4000):

```bash
bundle exec jekyll serve
```

3. With live reload:

```bash
bundle exec jekyll serve --livereload
```

4. Include drafts from `_drafts/` while serving:

```bash
bundle exec jekyll serve --drafts
```

## Common Tasks
- Build the site to `_site/`:

```bash
bundle exec jekyll build
```

- Clean generated files:

```bash
bundle exec jekyll clean
```

## Notes
- The generated site lives in `_site/`; it is recreated on build/serve.
- If you use Homebrew Ruby, you may need to add it to your shell path, e.g. append to your shell config:

```bash
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
```

- If `bundle install` fails due to native extensions, ensure Xcode Command Line Tools are installed:

```bash
xcode-select --install
```

## Troubleshooting
- Bundler cannot find gems:
  - Try: `bundle update`
  - Or remove `Gemfile.lock` and run `bundle install` again.
- Port 4000 in use:
  - Serve on another port: `bundle exec jekyll serve --port 4001`
