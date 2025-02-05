# Data Science Docker Environments - Version History

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

## Available Versions

### CPU Versions

#### Version 2.0 (Latest) - [Docker Hub](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=2.0)
- **Size**: 1.42GB
- **New Features**:
  - Multi-stage build for smaller size
  - Enhanced security with configurable authentication
  - Full Git integration with JupyterLab
  - Node.js 18.x for extension support
  - Performance optimization packages (Numba, Dask)
  - Advanced ML packages (LightGBM, XGBoost)
  - Resource monitoring tools
  - Container healthcheck
  - Version-pinned dependencies
  - SSH and Git configuration support

```bash
# Pull Version 2.0
docker pull bhumukulrajds/datasci-cpu:2.0
# or latest
docker pull bhumukulrajds/datasci-cpu:latest

# Run with Git integration
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -v ~/.ssh:/root/.ssh:ro \
  -v ~/.gitconfig:/etc/gitconfig.d/.gitconfig:ro \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

#### Version 1.0 - [Docker Hub](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=1.0)
- **Size**: 775MB
- **Features**:
  - Lightweight and minimal
  - Basic data science packages
  - Simple setup without authentication
  - Single-stage build
  - Core packages (NumPy, Pandas, Scikit-learn)
  - Basic visualization (Matplotlib, Seaborn)

```bash
# Pull Version 1.0
docker pull bhumukulrajds/datasci-cpu:1.0

# Basic run
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:1.0
```

## Version Comparison

### Size Comparison
- v1.0: 775MB (Basic setup)
- v2.0: 1.42GB (Full featured)

### Feature Comparison

| Feature                    | v1.0     | v2.0     |
|---------------------------|----------|-----------|
| Base Python               | 3.9      | 3.9      |
| Build Type                | Single   | Multi    |
| Security Authentication   | No       | Yes      |
| Git Integration           | Basic    | Full     |
| SSH Key Support           | No       | Yes      |
| Node.js Support          | No       | Yes      |
| NumPy/Pandas              | Yes      | Yes      |
| Scikit-learn             | Yes      | Yes      |
| Matplotlib/Seaborn        | Yes      | Yes      |
| JupyterLab               | Basic    | Advanced |
| Performance Tools         | No       | Yes      |
| Resource Monitoring       | No       | Yes      |
| Version-pinned Packages   | No       | Yes      |
| Healthcheck              | No       | Yes      |
| Advanced ML Packages      | No       | Yes      |
| Visual Diff Tools        | No       | Yes      |
| Credential Caching       | No       | Yes      |

### Package Version Comparison

| Package                   | v1.0     | v2.0         |
|--------------------------|----------|---------------|
| Python                   | 3.9      | 3.9          |
| NumPy                    | Latest   | 1.24.3       |
| Pandas                   | Latest   | 2.0.3        |
| Scikit-learn            | Latest   | 1.3.0        |
| Matplotlib              | Latest   | 3.7.1        |
| Seaborn                 | Latest   | 0.12.2       |
| JupyterLab              | Latest   | 4.0.2        |
| IPython Widgets         | Latest   | 8.0.7        |
| Numba                   | No       | 0.57.1       |
| Dask                    | No       | 2023.7.1     |
| LightGBM                | No       | 4.0.0        |
| XGBoost                 | No       | 1.7.6        |
| Node.js                 | No       | 18.x         |

### When to Use Each Version

#### Use Version 1.0 if you:
- Need a minimal environment
- Want faster downloads (smaller size)
- Don't need advanced ML packages
- Prefer simplicity over features
- Are running in a development environment
- Don't require Git integration

#### Use Version 2.0 if you:
- Need enhanced security
- Want Git integration in JupyterLab
- Need SSH key support
- Want performance optimization tools
- Use advanced ML packages
- Need resource monitoring
- Want reproducible builds with pinned versions
- Are running in a production environment
- Need visual diff tools
- Want credential caching

## Migration Guide

### Upgrading from v1.0 to v2.0

1. Pull the new image:
```bash
docker pull bhumukulrajds/datasci-cpu:2.0
```

2. Update your run commands to include security and Git integration:
```bash
# Old v1.0 command
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:1.0

# New v2.0 command with security and Git
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -v ~/.ssh:/root/.ssh:ro \
  -v ~/.gitconfig:/etc/gitconfig.d/.gitconfig:ro \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

3. Update your dependencies to use new packages if needed.
4. Set up Git configuration if using version control features.

## Documentation

### Docker Hub Links
- [Version 1.0 Image](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=1.0)
- [Version 2.0 Image](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=2.0)

### GitHub Documentation
- [Version 1.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v1/datasci_cpu/PREVIEW.md)
- [Version 2.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v2/datasci_cpu/PREVIEW.md)
- [Version Comparison](https://github.com/bhumukul-raj/docker-repo-info/blob/main/VERSIONS.md)

### Repository
- [GitHub Repository](https://github.com/bhumukul-raj/docker-repo-info)
  - Contains all Dockerfiles
  - Full documentation
  - Version history
  - Example code
  - Configuration files

## Notes
- Both versions are maintained and available on Docker Hub
- Version 2.0 is tagged as 'latest'
- Each version has its own detailed documentation
- Version 2.0 includes full Git integration and security features
- Choose the version that best fits your needs 