# Build Module Reference

## Overview

The build system uses a modular architecture for compiling and packaging TentOfTrials.

## Modules

### Core Build (`build/core`)
- **Entry point**: Handles initialization and orchestrates the build pipeline
- **Configuration**: Reads `.buildrc` and environment variables

### Compiler Integration (`build/compiler`)
- **GCC/Clang**: Native compiler support with optimization flags
- **Cross-compilation**: Target different platforms from a single host

### Packaging (`build/package`)
- **Archive creation**: Generates `.tar.gz`, `.zip` artifacts
- **Checksum generation**: SHA256 verification files

### Testing (`build/test`)
- **Unit test runner**: Integrates with the test framework
- **Coverage reports**: Generates HTML coverage reports

## Usage

```bash
# Full build
python -m build

# Build specific module
python -m build --module core

# Build with optimizations
python -m build --release
```

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `BUILD_MODE` | `debug` | Build mode: debug/release |
| `BUILD_JOBS` | `4` | Parallel compilation jobs |
| `BUILD_TARGET` | `host` | Cross-compilation target |

## Output

Build artifacts are placed in `dist/` with the following structure:
```
dist/
├── tentoftrials-{version}.tar.gz
├── tentoftrials-{version}.zip
└── checksums.sha256
```
