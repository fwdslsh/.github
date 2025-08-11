---
mode: agent
---
# Project Release Automation Setup

Create a complete release automation setup for a JavaScript/TypeScript project that builds single executable files using Bun for a given project/directory. Use the README.md file to get information about the project and then complete the following steps.

The setup should include:

## 1. Installation Script (`install.sh`)

Create a bash installation script with the following features:

**Core Functionality:**
- Auto-detect platform (Linux, macOS, Windows) and architecture (x86_64, arm64)
- Download appropriate binary from GitHub releases
- Install to `/usr/local/bin` (with sudo) or `~/.local/bin` (user install)
- Verify installation and check PATH configuration
- Support version selection and force reinstall options

**Script Features:**
- Colored output with ASCII banner
- Command-line options: `--help`, `--version TAG`, `--dir PATH`, `--user`, `--force`, `--dry-run`
- Environment variable support: `PROJECT_INSTALL_DIR`, `PROJECT_VERSION`, `PROJECT_FORCE`
- GLIBC compatibility check on Linux
- Comprehensive error handling and logging

**Binary Naming Convention:**
- Format: `{project-name}-{os}-{arch}` (e.g., `myapp-linux-x86_64`)
- Windows executables should have `.exe` extension

## 2. GitHub Workflows

### Build Binaries Workflow (`.github/workflows/build-binaries.yml`)
Create a reusable workflow that:
- Builds Bun executables for multiple platforms using a matrix strategy
- Platforms: `ubuntu-latest`, `macos-latest`, `windows-latest`
- Architectures: `x86_64`, `arm64` (where supported)
- Uses `bun build --compile` to create single executables
- Generates SHA256 checksums for each binary
- Uploads artifacts with proper naming

### Release Workflow (`.github/workflows/release.yml`)
Create a release workflow that:
- Triggers on version tags (`v*`) and manual dispatch
- Downloads all binary artifacts from the build workflow
- Organizes release assets and generates consolidated checksums
- Creates GitHub release with auto-generated release notes
- Builds and publishes Docker image to Docker Hub
- Supports pre-release detection (tags containing `-`)

**Release Notes Template:**
```markdown
# {PROJECT_NAME} CLI {VERSION}

## Installation

### Binary Downloads
- **Linux x86_64**: [Download](release-link)
- **Linux ARM64**: [Download](release-link)
- **macOS Intel**: [Download](release-link)
- **macOS Apple Silicon**: [Download](release-link)
- **Windows**: [Download](release-link)

### Installation Script
```bash
curl -fsSL https://raw.githubusercontent.com/{user}/{repo}/main/install.sh | sh
```

### Docker
```bash
docker run {dockerhub-user}/{project-name}:latest --help
```

## Verification
Checksums available in checksums.txt
```

## 3. Dockerfile

Create a multi-stage Dockerfile that:
- Uses Ubuntu:latest base image for glibc compatibility
- Installs Bun runtime
- Copies source code and builds the executable using `bun build --compile`
- Creates non-root user for security
- Sets executable as entrypoint
- Defaults to `--help` command

**Dockerfile Structure:**
```dockerfile
FROM ubuntu:latest
# Install Bun and dependencies
# Copy source files
# Build executable with: bun build src/cli.js --compile --outfile /usr/local/bin/{project-name}
# Set permissions and user
# Configure entrypoint
```

## 4. Project Structure Requirements

The setup assumes this project structure:
```
{project-name}/
├── src/
│   └── cli.js              # Main CLI entry point
├── package.json            # Bun package configuration
├── Dockerfile
├── install.sh
└── .github/
    └── workflows/
        ├── build-binaries.yml
        └── release.yml
```

## 5. Required GitHub Secrets

Document these required repository secrets:
- `DOCKERHUB_USERNAME` - Docker Hub username
- `DOCKERHUB_TOKEN` - Docker Hub access token

## 6. Configuration Variables

Make the following configurable in the generated files:
- **PROJECT_NAME**: The name of your CLI tool
- **REPO_OWNER**: GitHub username/organization
- **REPO_NAME**: GitHub repository name
- **DOCKERHUB_USER**: Docker Hub username
- **CLI_ENTRYPOINT**: Main CLI file path (e.g., `src/cli.js`)
- **DEFAULT_CMD**: Default command for Docker container

## 7. Additional Features

**Install Script Enhancements:**
- Progress bars for downloads
- Automatic PATH detection and configuration advice
- Platform-specific installation instructions
- Fallback installation methods

**Workflow Features:**
- Matrix builds for all platform combinations
- Artifact retention (30 days)
- Pre-release support for development versions
- Comprehensive validation and testing
- Docker multi-platform builds

**Error Handling:**
- Network timeouts and retries
- Missing dependencies detection
- Clear error messages with solutions
- Graceful fallbacks

Generate all the necessary files with placeholder values filled in for the current project. Include detailed comments explaining each section and configuration option.