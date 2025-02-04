# Data Science Docker Environments - Version History

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

## Available Versions

### CPU Versions

#### Version 2.0 (Latest) - [Docker Hub](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=2.0)
- **Size**: 1.42GB
- **New Features**:
  - Multi-stage build for smaller size
  - Enhanced security with configurable authentication
  - Performance optimization packages (Numba, Dask)
  - Advanced ML packages (LightGBM, XGBoost)
  - Resource monitoring tools
  - Container healthcheck
  - Version-pinned dependencies

```bash
# Pull Version 2.0
docker pull bhumukulrajds/datasci-cpu:2.0
# or latest
docker pull bhumukulrajds/datasci-cpu:latest
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
```

## Version Comparison

### Size Comparison
- v1.0: 775MB
- v2.0: 1.42GB

### Feature Comparison

| Feature                    | v1.0     | v2.0     |
|---------------------------|----------|-----------|
| Base Python               | 3.9      | 3.9      |
| Build Type                | Single   | Multi    |
| Security Authentication   | No       | Yes      |
| NumPy/Pandas              | Yes      | Yes      |
| Scikit-learn             | Yes      | Yes      |
| Matplotlib/Seaborn        | Yes      | Yes      |
| JupyterLab               | Yes      | Yes      |
| Performance Tools         | No       | Yes      |
| Resource Monitoring       | No       | Yes      |
| Version-pinned Packages   | No       | Yes      |
| Healthcheck              | No       | Yes      |
| Advanced ML Packages      | No       | Yes      |

### When to Use Each Version

#### Use Version 1.0 if you:
- Need a minimal environment
- Want faster downloads (smaller size)
- Don't need advanced ML packages
- Prefer simplicity over features
- Are running in a development environment

#### Use Version 2.0 if you:
- Need enhanced security
- Want performance optimization tools
- Use advanced ML packages
- Need resource monitoring
- Want reproducible builds with pinned versions
- Are running in a production environment

## Migration Guide

### Upgrading from v1.0 to v2.0

1. Pull the new image:
```bash
docker pull bhumukulrajds/datasci-cpu:2.0
```

2. Update your run commands to include authentication:
```bash
# Old v1.0 command
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:1.0

# New v2.0 command with security
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

3. Update your dependencies to use new packages if needed.

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
- Choose the version that best fits your needs 