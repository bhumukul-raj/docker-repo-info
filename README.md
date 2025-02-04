# Data Science Docker Environments

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A collection of Docker environments for data science and machine learning tasks, optimized for both CPU and GPU usage.

## 🌟 Quick Links

### CPU Version
- [Version 2.0 (Latest)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=2.0) - Enhanced features, security, and ML packages
- [Version 1.0](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/tags?name=1.0) - Lightweight and minimal

### Documentation
- [Version Comparison](VERSIONS.md) - Detailed comparison of features and sizes
- [CPU v2.0 Documentation](v2/datasci_cpu/PREVIEW.md) - Latest CPU version details
- [CPU v1.0 Documentation](v1/datasci_cpu/PREVIEW.md) - Original CPU version details

## 🚀 Quick Start

### Latest Version (2.0)
```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:2.0

# Run with security (recommended)
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
│   └── datasci_cpu/
│       ├── Dockerfile.cpu     # Version 1.0 Dockerfile
│       └── PREVIEW.md         # Version 1.0 Documentation
├── v2/
│   └── datasci_cpu/
│       ├── Dockerfile.cpu     # Version 2.0 Dockerfile
│       ├── requirements.txt   # Pinned package versions
│       └── PREVIEW.md         # Version 2.0 Documentation
├── VERSIONS.md               # Version comparison
└── README.md                # This file
```

## 🔄 Version Overview

### Version 2.0 (Latest - 1.42GB)
- Multi-stage build for optimization
- Enhanced security features
- Performance packages (Numba, Dask)
- Advanced ML packages (LightGBM, XGBoost)
- Resource monitoring
- Container healthcheck
- Version-pinned dependencies

### Version 1.0 (Minimal - 775MB)
- Single-stage build
- Basic data science packages
- Simple setup
- Minimal footprint
- Core ML capabilities

## 💻 Usage Examples

### Basic Usage
```bash
# Mount current directory and start JupyterLab
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0
```

### Resource-Limited Usage
```bash
# Run with CPU and memory limits
docker run -it --cpus=4 --memory=8g \
  -p 8888:8888 -v $(pwd):/workspace \
  bhumukulrajds/datasci-cpu:2.0
```

### Secure Usage
```bash
# Run with authentication
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

## 🛠️ Development

### Building Images
```bash
# Build Version 2.0
cd v2/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:2.0 .

# Build Version 1.0
cd v1/datasci_cpu
docker build -f Dockerfile.cpu -t datasci-cpu:1.0 .
```

### Contributing
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📝 Notes
- Choose version based on your needs (see [VERSIONS.md](VERSIONS.md))
- Version 2.0 recommended for production use
- Version 1.0 ideal for development/learning

## 🔗 Links
- [Docker Hub Repository](https://hub.docker.com/r/bhumukulrajds/datasci-cpu)
- [GitHub Repository](https://github.com/bhumukul-raj/docker-repo-info)
- [Version Comparison](VERSIONS.md)

## 📜 License
MIT License - See [LICENSE](LICENSE) for details