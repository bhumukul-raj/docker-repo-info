# Personal Data Science Environment v4.0

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A lightweight Docker environment for personal data science and machine learning tasks, optimized for CPU usage. Version 4.0 includes security updates, improved extension management, and enhanced development tools.

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:4.0

# Basic run
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

Access JupyterLab at: http://127.0.0.1:8888

## 📦 What's Included

### Base Image & Tools
- Python 3.9 (slim version)
- Multi-stage build for reduced image size
- Virtual environment for package isolation
- Git with automatic repository recognition
- Node.js 18.x for extension support
- System tools:
  - vim for text editing
  - htop for system monitoring
  - wget and unzip for file operations
  - tree for directory visualization
  - bash-completion for better CLI experience

### Core Data Science Packages
- **Data Processing**: 
  - NumPy (1.24.3)
  - Pandas (2.0.3)
  - Scikit-learn (1.4.2) - Security patched
  - SciPy (1.11.3)
  - Statsmodels (0.14.1)

### Visualization
- Matplotlib (3.7.1)
- Seaborn (0.12.2)
- Plotly (5.18.0) - Interactive plots

### Development Environment
- JupyterLab (4.1.1) - Security patched
- IPython (8.18.1) - Enhanced Python shell
- IPython Widgets (8.0.7)
- Black (24.1.1) - Code formatting
- isort (5.13.2) - Import sorting
- System Monitoring (psutil 5.9.5)

### Performance Optimization
- Numba (0.57.1) - for CPU-intensive computations
- Dask (2023.7.1) - for parallel processing

### JupyterLab Extensions
- Execute Time - Show cell execution time
- Spellchecker - Markdown spell checking
- Git integration
- And more in recommended_extensions.txt

## 🔧 Enhanced Features

### Terminal Enhancements
- Color support for better readability
- Git branch in prompt
- Useful aliases for common commands:
  ```bash
  ll        # List files in detail
  gs        # Git status
  black     # Format Python code
  isort     # Sort imports
  ```
- Bash completion for commands
- Custom welcome message with available tools

### Development Tools
- Automatic code formatting with Black
- Import sorting with isort
- Enhanced IPython shell
- Git integration with visual feedback
- Spell checking in markdown
- Cell execution time display

### System Configuration
- UTC timezone by default
- Automatic Git safe directory setup
- Persistent workspace volume
- Resource monitoring tools

## 💻 Usage Examples

### Basic Usage
```bash
# Run with current directory mounted
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0

# Run with custom port
docker run -it -p 9999:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0

# Run with resource limits
docker run -it --cpus=4 --memory=8g -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:4.0
```

### Development Tools Usage
```bash
# Format Python code
black your_file.py

# Sort imports
isort your_file.py

# View directory structure
tree

# Monitor system resources
htop

# Edit files in terminal
vim your_file.py
```

## 🛠️ Technical Details

### Container Specifications
- Base Image: python:3.9-slim
- Working Directory: /workspace
- Exposed Port: 8888
- Git: Latest version with safe directory configuration
- Node.js: 18.x LTS
- Default Timezone: UTC

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

### Security Updates in v4.0
- Updated JupyterLab to 4.1.1 to fix HTML injection vulnerability
- Updated Scikit-learn to 1.4.2 to fix data leakage vulnerability
- Enhanced security in extension management
- Added system monitoring tools

### Recommended Additional Packages
Consider installing these useful packages based on your needs:
- **Data Processing**: scipy, statsmodels, openpyxl
- **Visualization**: plotly
- **Development**: pytest, black, isort
- **Machine Learning**: tensorflow, pytorch, xgboost

## 📝 Tips and Tricks

1. **Terminal Usage**
   - Use `htop` to monitor system resources
   - Use `tree` to visualize directory structure
   - Use vim or install your preferred editor
   - Utilize bash aliases for common commands

2. **Code Quality**
   - Use `black` for consistent code formatting
   - Use `isort` for organized imports
   - Enable spellcheck for markdown
   - Monitor cell execution times

3. **Resource Management**
   - Monitor system resources in JupyterLab
   - Use resource limits for better control
   - Clean unused kernels regularly
   - Use `htop` for detailed system monitoring

## 📜 License
MIT License - feel free to use for personal or commercial projects.

## 🤝 Support
For issues and feature requests, please visit the [GitHub repository](https://github.com/bhumukulraj/docker-repo-info). 