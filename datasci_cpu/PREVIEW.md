# Data Science CPU Environment

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A lightweight Docker environment for data science and machine learning tasks, optimized for CPU usage.

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:latest

# Run the container
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu
```

## 📦 What's Included

### Base Image
- Python 3.9 (slim version)
- Essential system utilities (wget, git)

### Python Packages
- **Data Processing**: 
  - NumPy
  - Pandas
  - Scikit-learn
- **Visualization**: 
  - Matplotlib
  - Seaborn
- **Development Environment**: 
  - JupyterLab
  - IPython Widgets

## 💻 Usage Examples

### Basic Usage
```bash
# Run with current directory mounted
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu

# Run with custom port
docker run -it -p 9999:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu

# Run with specific name
docker run -it --name my-ds-env -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu
```

### Accessing JupyterLab
1. Open your browser
2. Navigate to `http://localhost:8888`
3. Start coding!

## 📊 Example Code

```python
# Data Science imports
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split

# Create sample data
X = np.random.randn(100, 2)
y = np.random.randint(0, 2, 100)

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create visualization
plt.figure(figsize=(10, 6))
plt.scatter(X[:, 0], X[:, 1], c=y)
plt.title('Sample Data Visualization')
plt.show()
```

## 🔧 Customization

### Adding New Packages
```bash
# Enter the container
docker exec -it container_name bash

# Install new package
pip install package_name
```

### Persistent Storage
- All files in `/workspace` directory are persisted to the mounted volume
- Save notebooks and data in this directory for persistence

## 🛠️ Technical Details

### Container Specifications
- Base Image: python:3.9-slim
- Working Directory: /workspace
- Exposed Port: 8888
- Default Command: JupyterLab

### Resource Usage
- Minimal installation size
- Optimized for CPU-based computations
- Low memory footprint

## 📝 Notes
- No password/token required for JupyterLab (development use only)
- All packages are installed via pip for minimal size
- Workspace directory is mounted for persistent storage

## 🔄 Updates
Check for updates regularly:
```bash
docker pull bhumukulrajds/datasci-cpu:latest
```

## 🤝 Contributing
Feel free to open issues or submit pull requests on the GitHub repository.

## 📜 License
MIT License - feel free to use for personal or commercial projects. 