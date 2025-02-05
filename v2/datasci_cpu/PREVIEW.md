# Data Science CPU Environment v2.0

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A comprehensive Docker environment for data science and machine learning tasks, optimized for CPU usage. Version 2.0 includes enhanced security, Git integration, performance optimizations, and additional ML packages.

## 🔐 Current Security Token
The current JupyterLab security token is:
```
db5bd5722b1491f4a44c21b976fd9a752bb3d0b3ef4929dd
```

Access your JupyterLab instance using either:
- Direct URL: `http://127.0.0.1:8888/lab?token=db5bd5722b1491f4a44c21b976fd9a752bb3d0b3ef4929dd`
- Or visit `http://127.0.0.1:8888` and enter the token when prompted

Note: This token changes each time you restart the container.

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:2.0

# Basic run (not recommended for production)
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0

# Recommended run with security and Git integration
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -v ~/.ssh:/root/.ssh:ro \
  -v ~/.gitconfig:/etc/gitconfig.d/.gitconfig:ro \
  -e JUPYTER_TOKEN="your_secret_token" \
  bhumukulrajds/datasci-cpu:2.0
```

## 📦 What's Included

### Base Image & Build Optimization
- Python 3.9 (slim version)
- Multi-stage build for reduced image size
- Virtual environment for better package isolation
- Node.js 18.x for JupyterLab extensions

### Core Data Science Packages (Pinned Versions)
- **Data Processing**: 
  - NumPy (1.24.3)
  - Pandas (2.0.3)
  - Scikit-learn (1.3.2) - Updated for security patch

### Performance Optimization Packages
- Numba (0.57.1) - for CPU-intensive computations
- Dask (2023.7.1) - for parallel processing
- LightGBM (4.0.0) - efficient gradient boosting
- XGBoost (1.7.6) - scalable gradient boosting

### Visualization
- Matplotlib (3.7.1)
- Seaborn (0.12.2)

### Development Environment
- JupyterLab (4.1.2) - Updated with security fixes
- IPython Widgets (8.0.7)
- Git Integration with JupyterLab
- SSH and Git configuration support
- Jupyter Server Proxy (4.1.2) - Updated with security fixes

### Monitoring Tools
- Jupyter Resource Usage (0.7.2)
- System Monitoring (psutil 5.9.5)

## 💻 Usage Examples

### Basic Usage
```bash
# Run with current directory mounted
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0

# Run with custom port
docker run -it -p 9999:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0

# Run with resource limits
docker run -it --cpus=4 --memory=8g -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0
```

### Secure Usage with Git Integration
```bash
# Run with Git configuration and SSH keys
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -v ~/.ssh:/root/.ssh:ro \
  -v ~/.gitconfig:/etc/gitconfig.d/.gitconfig:ro \
  -e JUPYTER_TOKEN="your_secure_token" \
  bhumukulrajds/datasci-cpu:2.0

# For Windows users (PowerShell)
docker run -it -p 8888:8888 `
  -v ${PWD}:/workspace `
  -v $HOME/.ssh:/root/.ssh:ro `
  -v $HOME/.gitconfig:/etc/gitconfig.d/.gitconfig:ro `
  -e JUPYTER_TOKEN="your_secure_token" `
  bhumukulrajds/datasci-cpu:2.0
```

## 🔧 Features

### Git Integration
- Full Git support in JupyterLab interface
- Clone, commit, push, and pull directly from JupyterLab
- Visual diff viewer and merge conflict resolution
- SSH key and Git configuration support
- Credential caching for convenience

### Security Features
- Token-based authentication (default)
- Optional password-based authentication
- Protection against XSS vulnerabilities
- Secure WebSocket authentication
- Protection against DOM Clobbering
- Secured authentication and CSRF tokens
- Protected against data leakage
- Configurable JupyterLab authentication
- Environment variable based configuration
- Read-only mounting of sensitive files
- Isolated Python environment
- Healthcheck implementation

### Performance Features
- Multi-stage build for smaller image size
- Optimized package versions
- Support for parallel processing
- Resource monitoring and management

## 🛠️ Technical Details

### Container Specifications
- Base Image: python:3.9-slim
- Working Directory: /workspace
- Exposed Port: 8888
- Healthcheck: Enabled (30s interval)
- Node.js: 18.x
- Git: Latest version

### Environment Variables
```bash
JUPYTER_TOKEN       # Set custom access token (current: 2c3bf6d948802aea5e662da4857123deeb5d4ad0bf4dd0ac)
JUPYTER_PASSWORD    # Set custom password (optional)
```

### Volume Mounts
```bash
/workspace              # Your working directory
/root/.ssh             # SSH keys (optional)
/etc/gitconfig.d       # Git configuration (optional)
```

## 📝 Best Practices

### Security
- Always use JUPYTER_TOKEN in production
- Mount SSH keys as read-only
- Use resource limits in production
- Regular security updates

### Git Usage
- Use SSH keys for repository access
- Configure Git credentials properly
- Regular commits and pushes
- Use .gitignore for sensitive data

### Resource Management
- Monitor container resource usage
- Set appropriate CPU and memory limits
- Use healthcheck for stability
- Regular container updates

## 🔄 Updates and Maintenance

### Updating the Container
```bash
# Pull latest version
docker pull bhumukulrajds/datasci-cpu:latest

# Remove old containers
docker ps -a | grep datasci-cpu | awk '{print $1}' | xargs docker rm

# Remove old images
docker images | grep datasci-cpu | awk '{print $3}' | xargs docker rmi
```

### Health Monitoring
```bash
# Check container health
docker inspect --format='{{.State.Health.Status}}' container_name

# View container logs
docker logs container_name
```

## 🤝 Contributing
Feel free to open issues or submit pull requests on the GitHub repository.

## 📜 License
MIT License - feel free to use for personal or commercial projects. 