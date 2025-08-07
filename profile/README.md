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

## Community

- 🌐 **Website**: [fwdslsh.dev](https://fwdslsh.dev) _(coming soon)_
- 📦 **Packages**: [npmjs.com/org/fwdslsh](https://npmjs.com/org/fwdslsh)
- 💬 **Discussions**: Use GitHub Discussions on our tool repositories
- 🐛 **Issues**: Report bugs and request features in individual repos

---

_Providing tools to help developers forge their own path._
