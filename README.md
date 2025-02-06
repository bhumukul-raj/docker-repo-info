# Data Science Docker Environments

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A collection of Docker environments for data science and machine learning tasks, optimized for both CPU and GPU usage.

## 🌟 Quick Links

### CPU Version
- [Version 4.0 (Latest)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=4.0) - Enhanced development tools and security updates
- [Version 3.0](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=3.0) - Simplified personal use with on-demand extensions
- [Version 2.0](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=2.0) - Enhanced features, security, and ML packages
- [Version 1.0](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=1.0) - Lightweight and minimal

### Documentation
- [Version Comparison](VERSIONS.md) - Detailed comparison of features and sizes
- [CPU v4.0 Documentation](v4/datasci_cpu/PREVIEW.md) - Latest version with enhanced tools
- [CPU v3.0 Documentation](v3/datasci_cpu/PREVIEW.md) - Personal use version
- [CPU v2.0 Documentation](v2/datasci_cpu/PREVIEW.md) - Production version
- [CPU v1.0 Documentation](v1/datasci_cpu/PREVIEW.md) - Minimal version

## 🚀 Quick Start

### Latest Version (4.0)
```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:4.0

# Run with development tools
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

### Production Version (2.0)
```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:2.0

# Run with security
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

### Minimal Version (1.0)
```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:1.0

# Run the container
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:1.0
```

## 📦 Repository Structure

```
.
├── v1/
│   └── datasci_cpu/          # Version 1.0 - Minimal
│       ├── Dockerfile.cpu    
│       └── PREVIEW.md        
├── v2/
│   └── datasci_cpu/          # Version 2.0 - Production
│       ├── Dockerfile.cpu    
│       ├── requirements.txt  
│       └── PREVIEW.md        
├── v3/
│   └── datasci_cpu/          # Version 3.0 - Personal Use
│       ├── Dockerfile.cpu
│       ├── requirements.txt
│       ├── recommended_extensions.txt
│       └── PREVIEW.md
├── v4/
│   └── datasci_cpu/          # Version 4.0 - Enhanced Tools
│       ├── Dockerfile.cpu
│       ├── requirements.txt
│       ├── recommended_extensions.txt
│       ├── bashrc
│       └── PREVIEW.md
├── VERSIONS.md               # Version comparison
└── README.md                # This file
```

## 🔄 Version Overview

### Version 4.0 (Latest - 1.2GB)
- Enhanced development tools
- System utilities (vim, htop, tree)
- Terminal enhancements
- Code formatting tools
- Scientific computing packages
- Security updates
- Custom shell configuration

### Version 3.0 (1.1GB)
- Simplified for personal use
- On-demand extension installation
- Automatic Git repository recognition
- Multi-stage build optimization
- Core data science packages

### Version 2.0 (1.42GB)
- Multi-stage build for optimization
- Enhanced security features
- Performance packages
- Advanced ML packages
- Resource monitoring
- Container healthcheck
- Version-pinned dependencies

### Version 1.0 (775MB)
- Single-stage build
- Basic data science packages
- Simple setup
- Minimal footprint
- Core ML capabilities

## 💻 Usage Examples

### Enhanced Development (v4.0)
```bash
# Run with development tools
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

### Personal Use (v3.0)
```bash
# Basic run with extensions support
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0
```

### Production Use (v2.0)
```bash
# Run with security and resource limits
docker run -it --cpus=4 --memory=8g \
  -p 8888:8888 -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

### Development Use (v1.0)
```bash
# Simple run for development
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:1.0
```

## 🛠️ Development

### Building Images
```bash
# Build Version 4.0
cd v4/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:4.0 .

# Build Version 3.0
cd v3/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:3.0 .

# Build Version 2.0
cd v2/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:2.0 .

# Build Version 1.0
cd v1/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:1.0 .
```

## 📝 Version Selection Guide
- Version 4.0: Enhanced development with full tool suite
- Version 3.0: Personal use, flexibility with extensions
- Version 2.0: Production use, security-focused
- Version 1.0: Learning, development, minimal needs

## 🔗 Links
- [Docker Hub Repository](https://hub.docker.com/r/bhumukulrajds/datasci-cpu)
- [GitHub Repository](https://github.com/bhumukulraj/docker-repo-info)
- [Version Comparison](VERSIONS.md)

## 📜 License
MIT License - See [LICENSE](LICENSE) for details