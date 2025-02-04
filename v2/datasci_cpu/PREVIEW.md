# Data Science CPU Environment v2.0

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-cpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-cpu/)

A lightweight Docker environment for data science and machine learning tasks, optimized for CPU usage. Version 2.0 includes enhanced security, performance optimizations, and additional ML packages.

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-cpu:2.0

# Run with basic configuration
docker run -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-cpu:2.0

# Run with security tokens (recommended)
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secret_token" \
  -e JUPYTER_PASSWORD="your_password" \
  bhumukulrajds/datasci-cpu:2.0
```

## 📦 What's Included

### Base Image & Build Optimization
- Python 3.9 (slim version)
- Multi-stage build for reduced image size
- Virtual environment for better package isolation
- Essential system utilities (wget, git)

### Core Data Science Packages
- **Data Processing**: 
  - NumPy (1.24.3)
  - Pandas (2.0.3)
  - Scikit-learn (1.3.0)

### Performance Optimization Packages
- Numba (0.57.1) - for CPU-intensive computations
- Dask (2023.7.1) - for parallel processing
- LightGBM (4.0.0) - efficient gradient boosting
- XGBoost (1.7.6) - scalable gradient boosting

### Visualization
- Matplotlib (3.7.1)
- Seaborn (0.12.2)

### Development Environment
- JupyterLab (4.0.2)
- IPython Widgets (8.0.7)

### Monitoring Tools
- Jupyter Resource Usage (0.7.2)
- psutil (5.9.5)

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

### Secure Usage
```bash
# Run with authentication
docker run -it -p 8888:8888 \
  -v $(pwd):/workspace \
  -e JUPYTER_TOKEN="your_secure_token" \
  bhumukulrajds/datasci-cpu:2.0
```

### Accessing JupyterLab
1. Open your browser
2. Navigate to `http://localhost:8888`
3. Enter token/password if configured
4. Start coding!

## 🔧 Performance Features

### Parallel Processing with Dask
```python
import dask.dataframe as dd

# Create Dask DataFrame
ddf = dd.read_csv('large_file.csv')

# Parallel computations
result = ddf.groupby('column').mean().compute()
```

### CPU Optimization with Numba
```python
from numba import jit
import numpy as np

@jit(nopython=True)
def fast_computation(x):
    return np.sum(x ** 2)

# Will run much faster than pure Python
result = fast_computation(np.array([1, 2, 3, 4, 5]))
```

### Efficient ML with LightGBM
```python
import lightgbm as lgb

# Create dataset
train_data = lgb.Dataset('train.csv')

# Train model efficiently
params = {
    'objective': 'binary',
    'metric': 'binary_logloss',
    'boosting_type': 'gbdt'
}
model = lgb.train(params, train_data)
```

## 🛠️ Technical Details

### Container Specifications
- Base Image: python:3.9-slim
- Working Directory: /workspace
- Exposed Port: 8888
- Healthcheck: Enabled (30s interval)

### Security Features
- Configurable JupyterLab authentication
- Environment variable based configuration
- Isolated Python environment

### Resource Management
- Supports CPU limiting
- Memory constraints
- Built-in resource monitoring

## 📝 Notes
- Container includes healthcheck
- All packages have pinned versions for reproducibility
- Workspace directory is mounted for persistent storage
- Resource monitoring tools included

## 🔄 Updates
Check for updates regularly:
```bash
docker pull bhumukulrajds/datasci-cpu:latest
```

## 🤝 Contributing
Feel free to open issues or submit pull requests on the GitHub repository.

## 📜 License
MIT License - feel free to use for personal or commercial projects. 