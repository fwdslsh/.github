# fwdslsh

We build developer experience focused tools for devs who remember when tools where not monoliths. Zero deps, instant setup, no frameworks to wrestle.

## Our Tools

### [giv](https://github.com/fwdslsh/giv) - Git workflows on autopilot

AI-powered commit messages, changelogs, and release notes. Ships as a static binary, talks to any LLM backend, doesn't break your flow.

```bash
# Better messages, less time
git commit -m "$(giv message)"
giv changelog v1.0.0..HEAD
```

**Why we built it**: Writing commit messages is grunt work. Let the machine do grunt work while you focus on the fun stuff.

### [unify](https://github.com/fwdslsh/unify) - Static sites for people with framework fatigue.

Build sites with Apache SSI syntax and modern tooling. No JSX, no config file hell, no framework lock-in. Just fast sites that ship.

```bash
# One binary, zero ceremony
unify build
unify serve --live-reload
```

**Why we built it**: Static site generators became more complex than the sites they build. We fixed that.

### [inform](https://github.com/fwdslsh/inform) - High-performance web crawler

Convert web pages to clean Markdown with intelligent content extraction. Built for documentation extraction and curation. Think context7 as a CLI tool.

```bash
# Crawl docs into Markdown
inform https://docs.example.com --output docs/
inform --recursive --depth 3 https://api.example.com
```

**Why we built it**: Web scraping shouldn't require learning a framework. Point, extract, markdown.

### [catalog](https://github.com/fwdslsh/catalog) - Content cataloging for Web 4.0

The next version of the web will be built for AI agents. Give them a content catalog to pick from.

**Why we built it**: The bot traffic to your site is only increasing. might as well let them save some GPU cycles.

---

## The Path Forward

**Old-school principles, new-school execution**: Unix philosophy meets modern tooling. Small, tatical programs that do one thing well.

**Ship binaries, not ecosystems**: Download once, run everywhere. No package manager roulette or dependency hell.

**Hack with the grain**: Work with web standards and POSIX conventions instead of reinventing them every six months.

**Performance starts in your head**: Tools should amplify human intelligence, not drain it with ceremony and complexity.

---

## Philosophy in Practice

We're not building the next unicorn framework. We're building tools for devs who value craft over hype.

Every tool should be:

- **Comprehensible** - Understand each tool in one session
- **Reliable** - Works the same way today and next year
- **Composable** - Plays nice with your existing scripts and workflows
- **Fast** - Both runtime fast and "get shit done" fast

This isn't luddism. It's choosing signal over noise, substance over ceremony, paths that actually lead somewhere.

The `/` isn't just our logo - it's a commitment to choosing a simpler path.

---

## Ecosystem Overview

### Documentation & Examples

- **[examples](https://github.com/fwdslsh/examples)** — Comprehensive guides, tutorials, and examples for all fwdslsh tools

### Supporting Infrastructure

- **[toolkit](https://github.com/fwdslsh/toolkit)** — Docker environment with all tools pre-installed
- **[website](https://github.com/fwdslsh/website)** — Official fwdslsh.dev site

### Unify Ecosystem

- **[create-unify-site](https://github.com/fwdslsh/create-unify-site)** — NPM scaffolding tool (`npm create unify-site`)
- **[unify-starter](https://github.com/fwdslsh/unify-starter)** — Template repository for new Unify sites
- **[unify-examples](https://github.com/fwdslsh/unify-examples)** — Example sites demonstrating Unify features
- **[unify-vscode](https://github.com/fwdslsh/unify-vscode)** — VS Code extension for Unify syntax highlighting

---

## Community

- 🌐 **Website**: [fwdslsh.dev](https://fwdslsh.dev)
- 📚 **Catalog**: [examples](https://github.com/fwdslsh/examples) - Comprehensive guides and tutorials
- 📦 **Packages**: [npmjs.com/org/fwdslsh](https://npmjs.com/org/fwdslsh)
- 💬 **Discussions**: Use GitHub Discussions on our tool repositories
- 🐛 **Issues**: Report bugs and request features in individual repos

---

_A path to a simpler future._
