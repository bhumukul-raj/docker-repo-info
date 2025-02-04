# Data Science GPU Environment

[![Docker Pulls](https://img.shields.io/docker/pulls/bhumukulrajds/datasci-gpu.svg)](https://hub.docker.com/r/bhumukulrajds/datasci-gpu/)

A powerful GPU-enabled Docker environment for deep learning and data science, built on NVIDIA CUDA 11.8.

## 🎯 Image Specifications
- **Size**: 6.53GB (Optimized)
- **Base**: nvidia/cuda:11.8.0-base-ubuntu20.04
- **Python**: 3.10
- **CUDA**: 11.8
- **PyTorch**: Latest with CUDA support

## 🚀 Quick Start

```bash
# Pull the image
docker pull bhumukulrajds/datasci-gpu:latest

# Run with GPU support
docker run --gpus all -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-gpu
```

## 💻 Requirements
- NVIDIA GPU
- NVIDIA Driver (recommended: 450.80.02 or higher)
- NVIDIA Container Toolkit (nvidia-docker2)
- Docker 19.03 or higher

## 📦 Included Packages

### Deep Learning
- PyTorch with CUDA support
- torchvision
- torchaudio

### Data Science
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn

### Development
- JupyterLab
- IPython Widgets
- Git
- Essential build tools

## 🔧 Usage Examples

### Basic GPU Container
```bash
docker run --gpus all -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-gpu
```

### Custom Resource Allocation
```bash
# Specify GPU memory limit
docker run --gpus 'device=0,memory=4gb' -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-gpu

# Use specific GPU
docker run --gpus device=1 -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-gpu

# Multiple GPUs
docker run --gpus 2 -it -p 8888:8888 -v $(pwd):/workspace bhumukulrajds/datasci-gpu
```

## 🧪 Verify GPU Setup

```python
# Test GPU availability
import torch

print("CUDA Available:", torch.cuda.is_available())
print("GPU Device Name:", torch.cuda.get_device_name(0))
print("Number of GPUs:", torch.cuda.device_count())

# GPU Memory Usage
print("\nGPU Memory Usage:")
print(f"Allocated: {torch.cuda.memory_allocated(0)/1024**3:.1f} GB")
print(f"Cached:    {torch.cuda.memory_reserved(0)/1024**3:.1f} GB")

# Simple GPU Operation Test
x = torch.randn(1000, 1000).cuda()
y = torch.randn(1000, 1000).cuda()
z = torch.matmul(x, y)  # Test GPU computation
```

## 📊 Performance Examples

### Deep Learning Example
```python
import torch
import torch.nn as nn

# Create a simple CNN
class SimpleCNN(nn.Module):
    def __init__(self):
        super(SimpleCNN, self).__init__()
        self.conv1 = nn.Conv2d(3, 16, 3)
        self.pool = nn.MaxPool2d(2, 2)
        self.fc1 = nn.Linear(16 * 14 * 14, 10)

    def forward(self, x):
        x = self.pool(torch.relu(self.conv1(x)))
        x = x.view(-1, 16 * 14 * 14)
        x = self.fc1(x)
        return x

# Move model to GPU
model = SimpleCNN().cuda()
```

## 🛠️ Resource Management

### Monitor GPU Usage
```bash
# Inside container
nvidia-smi

# Real-time monitoring
watch -n 1 nvidia-smi
```

### Memory Management
```python
# Clear GPU cache if needed
import torch
torch.cuda.empty_cache()

# Get memory info
def print_gpu_memory():
    print(f"Allocated: {torch.cuda.memory_allocated()/1024**3:.1f}GB")
    print(f"Cached:    {torch.cuda.memory_reserved()/1024**3:.1f}GB")
```

## 📝 Best Practices

1. **Memory Management**
   - Clear GPU memory when not in use
   - Use appropriate batch sizes
   - Monitor memory usage with `nvidia-smi`

2. **Performance Optimization**
   - Use `torch.cuda.amp` for mixed precision training
   - Implement proper data loading with `torch.utils.data.DataLoader`
   - Utilize GPU memory efficiently

3. **Development Workflow**
   - Save checkpoints regularly
   - Use version control for code
   - Keep track of experiments

## 🔍 Size Optimization (6.53GB)

### Size Breakdown
- CUDA Base (~2.5GB)
  - NVIDIA CUDA 11.8 runtime
  - Ubuntu 20.04 base system
  
- Python & Libraries (~3GB)
  - Python 3.10
  - PyTorch with CUDA
  - Scientific computing packages
  
- Additional Tools (~1GB)
  - Development utilities
  - JupyterLab
  - System packages

## 🔄 Updates & Maintenance

```bash
# Pull latest version
docker pull bhumukulrajds/datasci-gpu:latest

# Remove old images
docker image prune -f
```

## ⚠️ Troubleshooting

1. **CUDA Not Available**
   - Check NVIDIA drivers
   - Verify nvidia-docker installation
   - Ensure --gpus flag is used

2. **Memory Issues**
   - Monitor with nvidia-smi
   - Clear GPU cache
   - Adjust batch sizes

3. **Performance Issues**
   - Check GPU utilization
   - Monitor thermal throttling
   - Verify CUDA version compatibility

## 📚 References
- [NVIDIA Container Toolkit Documentation](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/overview.html)
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [Docker GPU Documentation](https://docs.docker.com/config/containers/resource_constraints/#gpu) 