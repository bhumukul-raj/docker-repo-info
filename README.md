# Data Science Docker Environments

This repository contains Docker environments for data science work, optimized for both CPU and GPU usage.

## 📂 Repository Structure

```
.
├── datasci_cpu/
│   ├── Dockerfile.cpu
│   └── PREVIEW.md
├── datasci_gpu/
│   ├── Dockerfile.gpu
│   └── PREVIEW_GPU.md
└── README.md
```

## 🚀 Quick Start

### CPU Version (Minimal ~2GB)
```bash
# Build CPU image
docker build -f datasci_cpu/Dockerfile.cpu -t datasci-cpu .

# Run CPU container
docker run -it -p 8888:8888 -v $(pwd):/workspace datasci-cpu
```

### GPU Version (CUDA-enabled ~6.5GB)
```bash
# Build GPU image
docker build -f datasci_gpu/Dockerfile.gpu -t datasci-gpu .

# Run GPU container
docker run --gpus all -it -p 8888:8888 -v $(pwd):/workspace datasci-gpu
```

## 🛠️ Building Images

### Basic Build
```bash
# CPU Version
docker build -f datasci_cpu/Dockerfile.cpu -t datasci-cpu .

# GPU Version
docker build -f datasci_gpu/Dockerfile.gpu -t datasci-gpu .
```

### Version Tagging
```bash
# CPU Version
docker build -f datasci_cpu/Dockerfile.cpu -t datasci-cpu:1.0 .
docker tag datasci-cpu:1.0 datasci-cpu:latest

# GPU Version
docker build -f datasci_gpu/Dockerfile.gpu -t datasci-gpu:1.0 .
docker tag datasci-gpu:1.0 datasci-gpu:latest
```

## 📤 Uploading to Docker Hub

1. **Login to Docker Hub**
```bash
docker login
```

2. **Tag Images with Your Username**
```bash
# CPU Version
docker tag datasci-cpu YOUR_USERNAME/datasci-cpu:latest
docker tag datasci-cpu YOUR_USERNAME/datasci-cpu:1.0

# GPU Version
docker tag datasci-gpu YOUR_USERNAME/datasci-gpu:latest
docker tag datasci-gpu YOUR_USERNAME/datasci-gpu:1.0
```

3. **Push Images**
```bash
# CPU Version
docker push YOUR_USERNAME/datasci-cpu:latest
docker push YOUR_USERNAME/datasci-cpu:1.0

# GPU Version
docker push YOUR_USERNAME/datasci-gpu:latest
docker push YOUR_USERNAME/datasci-gpu:1.0
```

## 📥 Pulling Images

```bash
# CPU Version
docker pull YOUR_USERNAME/datasci-cpu:latest

# GPU Version
docker pull YOUR_USERNAME/datasci-gpu:latest
```

## 🔄 Version Management

### Tagging Conventions
- `latest`: Most recent stable version
- `x.y`: Major.Minor version (e.g., 1.0, 1.1)
- `x.y.z`: Major.Minor.Patch version (e.g., 1.0.1)

### Creating New Versions
```bash
# Create new version
docker build -f Dockerfile.cpu -t YOUR_USERNAME/datasci-cpu:1.1 .
docker tag YOUR_USERNAME/datasci-cpu:1.1 YOUR_USERNAME/datasci-cpu:latest
docker push YOUR_USERNAME/datasci-cpu:1.1
docker push YOUR_USERNAME/datasci-cpu:latest
```

## 🔧 Common Operations

### Container Management
```bash
# List running containers
docker ps

# Stop container
docker stop CONTAINER_ID

# Remove container
docker rm CONTAINER_ID
```

### Image Management
```bash
# List images
docker images

# Remove image
docker rmi IMAGE_ID

# Clean unused images
docker image prune
```

### Data Persistence
```bash
# Mount current directory
docker run -v $(pwd):/workspace ...

# Mount specific directory
docker run -v /path/to/data:/workspace/data ...
```

## ⚠️ Important Notes

1. **GPU Requirements**
   - NVIDIA GPU
   - NVIDIA Driver installed
   - NVIDIA Container Toolkit (nvidia-docker2)
   - Docker 19.03+

2. **Port Usage**
   - Default JupyterLab port: 8888
   - Change with: `-p NEW_PORT:8888`

3. **Memory Management**
   - CPU: Set with `--memory=4g`
   - GPU: Monitor with `nvidia-smi`

## 🔍 Troubleshooting

1. **Port Already in Use**
```bash
# Use different port
docker run -p 8889:8888 ...
```

2. **GPU Not Detected**
```bash
# Check NVIDIA drivers
nvidia-smi

# Verify docker GPU support
docker run --gpus all nvidia/cuda:11.8.0-base-ubuntu20.04 nvidia-smi
```

3. **Permission Issues**
```bash
# Run with sudo
sudo docker ...

# Or add user to docker group
sudo usermod -aG docker $USER
```

## 📚 Additional Resources

- [Docker Documentation](https://docs.docker.com/)
- [NVIDIA Container Toolkit](https://github.com/NVIDIA/nvidia-docker)
- [Docker Hub](https://hub.docker.com/)
- [JupyterLab Documentation](https://jupyterlab.readthedocs.io/)

## 📝 License

MIT License - Feel free to use and modify for your needs. 