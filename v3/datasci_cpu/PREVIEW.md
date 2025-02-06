# Personal Data Science Environment v3.0

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A lightweight Docker environment for personal data science and machine learning tasks, optimized for CPU usage. Version 3.0 focuses on simplicity and flexibility with on-demand extension installation.

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:3.0

# Basic run
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0
```

Access JupyterLab at: http://127.0.0.1:8888

## 📦 What's Included

### Base Image
- Python 3.9 (slim version)
- Multi-stage build for reduced image size
- Virtual environment for package isolation
- Git with automatic repository recognition
- Node.js 18.x for extension support

### Core Data Science Packages
- **Data Processing**: 
  - NumPy (1.24.3)
  - Pandas (2.0.3)
  - Scikit-learn (1.4.1.post1)

### Visualization
- Matplotlib (3.7.1)
- Seaborn (0.12.2)

### Performance Optimization
- Numba (0.57.1) - for CPU-intensive computations
- Dask (2023.7.1) - for parallel processing

### Development Environment
- JupyterLab (4.0.11)
- IPython Widgets (8.0.7)
- System Monitoring (psutil 5.9.5)

## 🔧 Extension Management

The environment comes with a list of recommended extensions that you can install on-demand:

### Available Extensions
Check `/opt/recommended_extensions.txt` for the full list, including:
- Jupyter Widgets Manager
- Git Integration
- Table of Contents
- Interactive Plots (Plotly)
- DrawIO Integration
- Python Debugger
- Code Formatter
- Google Drive Integration
- System Monitor

To install extensions:
1. Open JupyterLab
2. Go to Extension Manager (puzzle piece icon)
3. Search and install desired extensions
4. Refresh the page when prompted

## 💻 Usage Examples

### Basic Usage
```bash
# Run with current directory mounted
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0

# Run with custom port
docker run -it -p 9999:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0

# Run with resource limits
docker run -it --cpus=4 --memory=8g -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:3.0
```

## 🛠️ Technical Details

### Container Specifications
- Base Image: python:3.9-slim
- Working Directory: /workspace
- Exposed Port: 8888
- Git: Latest version with safe directory configuration
- Node.js: 18.x LTS

### Volume Mounts
```bash
/workspace              # Your working directory
```

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

### Installing Additional Packages
You can install additional packages as needed using pip within JupyterLab:
```bash
# In a JupyterLab terminal
pip install package_name
```

### Recommended Additional Packages
Consider installing these useful packages based on your needs:
- **Data Processing**: scipy, statsmodels, openpyxl
- **Visualization**: plotly
- **Development**: pytest, black, isort
- **Machine Learning**: tensorflow, pytorch, xgboost

## 📝 Tips and Tricks

1. **Git Integration**
   - Repository is automatically recognized
   - No need for manual safe directory configuration
   - Use Git extension for visual Git operations

2. **Extension Management**
   - Install extensions as needed
   - Extensions persist across container restarts
   - Check recommended_extensions.txt for curated list

3. **Resource Management**
   - Monitor system resources in JupyterLab
   - Use resource limits for better control
   - Clean unused kernels regularly

## 📜 License
MIT License - feel free to use for personal or commercial projects.

## 🤝 Support
For issues and feature requests, please visit the [GitHub repository](https://github.com/bhumukulraj/docker-repo-info). 