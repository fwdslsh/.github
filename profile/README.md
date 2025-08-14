# fwdslsh

We build developer experience focused tools for devs who remember when tools where not monoliths. Zero deps, instant setup, no frameworks to babysit.

## Our Tools

### [giv](https://github.com/fwdslsh/giv) - Git workflows on autopilot

AI-powered commit messages, changelogs, and release notes. Ships as a static binary, talks to any LLM backend, doesn't break your flow.

```bash
# Better messages, less time
git commit -m "$(giv message)"
giv changelog v1.0.0..HEAD
```

**Why we built it**: Writing commit messages is grunt work. Let the machine do grunt work while you build.

### [unify](https://github.com/fwdslsh/unify) - Static sites for people who remember HTML

Build sites with Apache SSI syntax and modern tooling. No JSX, no build step hell, no framework lock-in. Just fast sites that ship.

```bash
# One binary, zero ceremony
unify build
unify serve --live-reload
```

**Why we built it**: Static site generators became more complex than the sites they build. We fixed that.

### [inform](https://github.com/fwdslsh/inform) - High-performance web crawler

Convert web pages to clean Markdown with intelligent content extraction. Built for documentation workflows and content archival.

```bash
# Crawl docs into Markdown
inform https://docs.example.com --output docs/
inform --recursive --depth 3 https://api.example.com
```

**Why we built it**: Web scraping shouldn't require learning a framework. Point, extract, markdown.

### [catalog](https://github.com/fwdslsh/catalog) - Centralized resource hub

Curated collection of tools, examples, and resources for the fwdslsh ecosystem. Your one-stop reference for finding the right tool for the job.

```bash
# Browse the catalog
git clone https://github.com/fwdslsh/catalog
cd catalog && unify serve --live-reload
```

**Why we built it**: Finding the right tool shouldn't require hunting through scattered repos. One place, everything organized.

---

## The Path Forward

**Old-school principles, new-school execution**: Unix philosophy meets modern tooling. Small, sharp programs that do one thing well.

**Ship binaries, not ecosystems**: Download once, run everywhere. No package manager roulette or dependency hell.

**Hack with the grain**: Work with web standards and POSIX conventions instead of reinventing everything.

**Performance starts in your head**: Tools should amplify human intelligence, not fight it with ceremony and complexity.

---

## Quick Start

```bash
# Install giv (cross-platform, no dependencies)
curl -L -o giv https://github.com/fwdslsh/giv/releases/latest/download/giv-linux-x86_64
chmod +x giv && sudo mv giv /usr/local/bin/

# Install unify (requires Bun)
bun add -g @fwdslsh/unify

# Use them together for documentation workflows
giv changelog > docs/CHANGELOG.md
unify build
```

---

## Philosophy in Practice

We're not building the next unicorn framework. We're building tools for devs who value craft over hype.

Every tool should be:

- **Comprehensible** - Understand each tool in one session
- **Reliable** - Works the same way today and next year
- **Composable** - Plays nice with your existing scripts and workflows
- **Fast** - Both runtime fast and "get shit done" fast

This isn't luddism. It's choosing signal over noise, substance over ceremony, paths that actually lead somewhere.

The `/` isn't just our logo - it's a commitment to cutting through the cruft.

---

## Catalog & Ecosystem

### [examples](https://github.com/fwdslsh/examples) - Documentation catalog

Comprehensive guides, tutorials, and examples for all fwdslsh tools. Your starting point for learning the ecosystem.

```bash
# Clone the catalog
git clone https://github.com/fwdslsh/examples
cd examples && unify serve --live-reload
```

**What's inside**: Tool guides, integration examples, best practices, and real-world workflows.

### Supporting Infrastructure

- **[toolkit](https://github.com/fwdslsh/toolkit)** - Docker environment with all tools pre-installed
- **[website](https://github.com/fwdslsh/website)** - Official fwdslsh.dev site

### Unify Ecosystem

- **[create-unify-site](https://github.com/fwdslsh/create-unify-site)** - NPM scaffolding tool (`npm create unify-site`)
- **[unify-starter](https://github.com/fwdslsh/unify-starter)** - Template repository for new Unify sites
- **[unify-examples](https://github.com/fwdslsh/unify-examples)** - Example sites demonstrating Unify features
- **[unify-vscode](https://github.com/fwdslsh/unify-vscode)** - VS Code extension for Unify syntax highlighting

---

## Community

- 🌐 **Website**: [fwdslsh.dev](https://fwdslsh.dev)
- 📚 **Catalog**: [examples](https://github.com/fwdslsh/examples) - Comprehensive guides and tutorials
- 📦 **Packages**: [npmjs.com/org/fwdslsh](https://npmjs.com/org/fwdslsh)
- 💬 **Discussions**: Use GitHub Discussions on our tool repositories
- 🐛 **Issues**: Report bugs and request features in individual repos

---

_A path to a more simple future._
