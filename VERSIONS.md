# Data Science Docker Environments - Version History

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

## Available Versions

### CPU Versions

#### Version 4.0 (Latest) - [Docker Hub](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=4.0)
- **Size**: 1.2GB
- **Features**:
  - Enhanced development tools
  - System utilities (vim, htop, tree)
  - Terminal enhancements with custom bashrc
  - Code formatting tools (black, isort)
  - Scientific computing packages
  - Security updates
  - Multi-stage build optimization
  - Core data science packages
  - Custom shell configuration
  - Welcome message and improved UX

```bash
# Pull Version 4.0
docker pull bhumukulrajds/datasci-cpu:4.0
# or latest
docker pull bhumukulrajds/datasci-cpu:latest

# Basic run
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

#### Version 3.0 (Latest) - [Docker Hub](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=3.0)
- **Size**: 1.1GB
- **Features**:
  - Simplified for personal use
  - On-demand extension installation
  - Automatic Git repository recognition
  - Multi-stage build optimization
  - Core data science packages
  - No pre-installed extensions
  - Node.js 18.x for extension support
  - Recommended extensions list

```bash
# Pull Version 3.0
docker pull bhumukulrajds/datasci-cpu:3.0
# or latest
docker pull bhumukulrajds/datasci-cpu:latest

# Basic run
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0
```

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
- v3.0: 1.1GB (Personal use)
- v4.0: 1.2GB (Enhanced tools)

### Feature Comparison

| Feature                    | v1.0     | v2.0     | v3.0     | v4.0     |
|---------------------------|----------|-----------|-----------|-----------|
| Base Python               | 3.9      | 3.9      | 3.9      | 3.9      |
| Build Type                | Single   | Multi    | Multi    | Multi    |
| Security Authentication   | No       | Yes      | No       | No       |
| Git Integration           | Basic    | Full     | Auto     | Auto     |
| SSH Key Support           | No       | Yes      | No       | No       |
| Node.js Support          | No       | Yes      | Yes      | Yes      |
| NumPy/Pandas              | Yes      | Yes      | Yes      | Yes      |
| Scikit-learn             | Yes      | Yes      | Yes      | Yes      |
| Matplotlib/Seaborn        | Yes      | Yes      | Yes      | Yes      |
| JupyterLab               | Basic    | Advanced | Simple   | Enhanced |
| Performance Tools         | No       | Yes      | Basic    | Yes      |
| Resource Monitoring       | No       | Yes      | Basic    | Full     |
| Version-pinned Packages   | No       | Yes      | Yes      | Yes      |
| Healthcheck              | No       | Yes      | No       | No       |
| Advanced ML Packages      | No       | Yes      | No       | Yes      |
| Extension Management     | No       | Fixed    | On-demand| On-demand|
| Extension List           | No       | No       | Yes      | Yes      |
| System Utilities         | No       | No       | No       | Yes      |
| Code Formatting          | No       | No       | No       | Yes      |
| Custom Shell Config      | No       | No       | No       | Yes      |
| Welcome Message          | No       | No       | No       | Yes      |

### Package Version Comparison

| Package                   | v1.0     | v2.0         | v3.0         | v4.0         |
|--------------------------|----------|---------------|---------------|---------------|
| Python                   | 3.9      | 3.9          | 3.9          | 3.9          |
| NumPy                    | Latest   | 1.24.3       | 1.24.3       | 1.24.3       |
| Pandas                   | Latest   | 2.0.3        | 2.0.3        | 2.0.3        |
| Scikit-learn            | Latest   | 1.3.0        | 1.4.2        | 1.4.2        |
| Matplotlib              | Latest   | 3.7.1        | 3.7.1        | 3.7.1        |
| Seaborn                 | Latest   | 0.12.2       | 0.12.2       | 0.12.2       |
| JupyterLab              | Latest   | 4.0.2        | 4.1.1        | 4.1.1        |
| IPython Widgets         | Latest   | 8.0.7        | 8.0.7        | 8.0.7        |
| Numba                   | No       | 0.57.1       | 0.57.1       | 0.57.1       |
| Dask                    | No       | 2023.7.1     | 2023.7.1     | 2023.7.1     |
| Node.js                 | No       | 18.x         | 18.x         | 18.x         |
| Black                   | No       | No           | No           | 24.1.1       |
| isort                   | No       | No           | No           | 5.13.2       |
| SciPy                   | No       | No           | No           | 1.11.3       |
| Statsmodels             | No       | No           | No           | 0.14.1       |
| Plotly                  | No       | No           | No           | 5.18.0       |

### When to Use Each Version

#### Use Version 4.0 if you:
- Want a complete development environment
- Need system utilities and monitoring tools
- Want code formatting and quality tools
- Need scientific computing packages
- Prefer a customized terminal experience
- Want security updates
- Need enhanced JupyterLab features

#### Use Version 3.0 if you:
- Want a personal development environment
- Prefer installing extensions on-demand
- Need automatic Git repository recognition
- Want a balance of features and size
- Don't need production security features
- Want flexibility in tool selection

#### Use Version 2.0 if you:
- Need enhanced security
- Want Git integration in JupyterLab
- Need SSH key support
- Want performance optimization tools
- Use advanced ML packages
- Need resource monitoring
- Want reproducible builds with pinned versions
- Are running in a production environment

#### Use Version 1.0 if you:
- Need a minimal environment
- Want faster downloads (smaller size)
- Don't need advanced ML packages
- Prefer simplicity over features
- Are running in a development environment
- Don't require Git integration

## Migration Guide

### Upgrading to v4.0

1. Pull the new image:
```bash
docker pull bhumukulrajds/datasci-cpu:4.0
```

2. Simple run command:
```bash
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

3. New features available:
- System utilities (vim, htop, tree)
- Code formatting (black, isort)
- Enhanced terminal experience
- Scientific computing packages
- Security updates

### Upgrading to v3.0

1. Pull the new image:
```bash
docker pull bhumukulrajds/datasci-cpu:3.0
```

2. Simple run command:
```bash
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0
```

3. Install extensions as needed through JupyterLab interface
4. Check recommended extensions in `/opt/recommended_extensions.txt`

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
- [Version 3.0 Image](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=3.0)
- [Version 4.0 Image](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=4.0)

### GitHub Documentation
- [Version 1.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v1/datasci_cpu/PREVIEW.md)
- [Version 2.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v2/datasci_cpu/PREVIEW.md)
- [Version 3.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v3/datasci_cpu/PREVIEW.md)
- [Version 4.0 Documentation](https://github.com/bhumukul-raj/docker-repo-info/blob/main/v4/datasci_cpu/PREVIEW.md)
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