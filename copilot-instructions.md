# GitHub Copilot Instructions for fwdslsh Ecosystem

## Project Overview
**fwdslsh** is a monorepo ecosystem of minimal, composable tools for static site generation, web content extraction, and AI-powered Git workflows. All tools follow the "slash a path to simplicity" philosophy with zero dependencies when possible, CLI-first design, and cross-platform binaries.

**ALWAYS reference the tool-specific `.github/copilot-instructions.md` files for detailed implementation guidance on individual tools.**

## Architecture & Tool Boundaries

### Core Tools (Independent but Composable)
- **unify/** - Bun-native static site generator with Apache SSI-style includes (`@fwdslsh/unify`)
- **inform/** - High-performance web crawler converting pages to Markdown (`@fwdslsh/inform`) 
- **giv/** - AI-powered Git assistant for commit messages and changelogs (Python/Poetry)
- **lift/** - Documentation indexer generating `llms.txt` from Markdown directories (`@fwdslsh/lift`)

### Supporting Infrastructure
- **toolkit/** - Docker environment with all tools pre-installed
- **examples/** - Comprehensive documentation and tutorials for all tools
- **website/** - Official fwdslsh website (renders examples/ documentation)

### Unify Ecosystem
- **create-unify-site/** - NPM scaffolding tool (`npm create unify-site`)
- **unify-starter/** - Template repository for new Unify sites
- **unify-examples/** - Example sites demonstrating Unify features
- **unify-vscode/** - VS Code extension for Unify syntax highlighting

## Development Workflows

### Runtime Requirements by Tool
- **Bun tools** (unify, inform, lift): `bun >=1.0.0` for development, compile to standalone executables
- **Python tools** (giv): Poetry for dependency management, PyInstaller for binaries
- **Supporting tools**: Node.js for create-unify-site

### Cross-Tool Integration Workflow
```bash
# Typical content workflow pipeline:
inform https://docs.example.com --output docs/    # Crawl → Markdown
lift --input docs --output build/                  # Markdown → llms.txt index
unify build --source content --output site/        # Markdown/HTML → static site
giv changelog HEAD~10..HEAD                        # Git history → professional docs
```

### Universal Build Commands
Each tool provides these standardized patterns:
```bash
# Development
bun install          # For Bun tools
poetry install       # For Python tools

# Testing  
bun test            # Bun tools
poetry run pytest   # Python tools

# Build executables
bun build --compile  # Bun cross-platform binaries
poetry run build-binary  # Python PyInstaller binaries
```

## Project-Specific Conventions

### CLI Interface Consistency
- Universal flags: `--help`, `--version`, `--verbose/--silent`
- Path handling: Always use absolute paths, prevent traversal attacks
- Exit codes: 0=success, 2=template error, 3=git error, 4=config error, 5=api error

### Dependency Philosophy
- **Zero dependencies preferred** for Bun tools (use native APIs)
- **Minimal dependencies** for Python tools (managed via Poetry)
- **Self-contained binaries** for distribution across all platforms

### Security & Performance Standards
- Path traversal prevention in all file operations
- Rate limiting and robots.txt respect in web crawlers
- Concurrent processing where appropriate (inform crawling, unify builds)
- Incremental builds with dependency tracking (unify)

### Documentation Patterns
- Each tool: README.md + comprehensive examples/ documentation
- Complex tools: Tool-specific `.github/copilot-instructions.md` (unify, giv)
- CLI help text must be complete and accurate
- Installation via `install.sh` scripts for binary tools

## Integration Points

### Adding New Tools
1. Follow established directory structure (`src/`, `tests/`, `docs/`)
2. Implement consistent CLI patterns with proper help text
3. Add to main `CLAUDE.md` overview
4. Create tool-specific copilot instructions if complex
5. Ensure cross-platform binary builds

### Monorepo Development
- Each tool is independently versioned and publishable
- Shared assets in root `assets/` directory
- Examples repository serves as universal documentation
- Docker toolkit provides unified development environment

### Error Handling Standards
- Graceful failures with helpful error messages
- Consistent exit codes across tools
- No execution of untrusted code in any tool
- Proper resource cleanup (file handles, network connections)

## Quick Reference

### Essential Files for Each Tool
- `README.md` - Installation, basic usage, key concepts
- `package.json` or `pyproject.toml` - Dependencies and scripts
- `.github/copilot-instructions.md` - Detailed development guidance (complex tools)
- `install.sh` - Binary installation script

### Ecosystem Documentation
- `examples/README.md` - Complete ecosystem overview and guides
- `CLAUDE.md` - High-level architecture and development commands
- `.github/README.md` - fwdslsh manifesto and philosophy
