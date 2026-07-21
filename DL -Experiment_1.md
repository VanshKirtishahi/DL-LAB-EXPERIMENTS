# EXPERIMENT 1: Installing Anaconda/Miniconda & Setting Up TensorFlow & Keras

## Objectives
- Install and configure Anaconda/Miniconda package manager
- Set up Python environment for deep learning
- Install TensorFlow and Keras
- Verify installation and run basic test

## Prerequisites
- Windows/Linux/macOS machine
- Internet connection
- 5+ GB disk space

## Implementation Steps

### Step 1: Download and Install Anaconda/Miniconda

```bash
# For Miniconda (lightweight, recommended)
# Download from: https://docs.conda.io/en/latest/miniconda.html

# On Linux/macOS:
bash Miniconda3-latest-Linux-x86_64.sh

# On Windows:
# Run the .exe installer
```

### Step 2: Create a Virtual Environment

```bash
# Create environment named 'dl_env'
conda create -n dl_env python=3.10

# Activate environment
conda activate dl_env
```

### Step 3: Install TensorFlow and Keras

```bash
# Install TensorFlow (includes Keras)
pip install tensorflow tensorflow-gpu

# Verify TensorFlow installation
python -c "import tensorflow as tf; print(tf.__version__)"
```

### Step 4: Install Additional Libraries

```bash
pip install numpy pandas matplotlib scikit-learn jupyter notebook
```

### Step 5: Verification Script

```python
import tensorflow as tf
import keras
import numpy as np

print(f"TensorFlow Version: {tf.__version__}")
print(f"Keras Version: {keras.__version__}")
print(f"GPU Available: {tf.config.list_physical_devices('GPU')}")

# Test basic operation
a = tf.constant([[1., 2.], [3., 4.]])
print(f"Matrix multiplication: {tf.matmul(a, a)}")
```

## Expected Outcomes
- Successfully installed Anaconda/Miniconda
- Virtual environment created and activated
- TensorFlow and Keras running without errors
- GPU detected (if available)

## Common Issues & Solutions

| Issue | Solution |
|---|---|
| CUDA not found | Reinstall tensorflow-gpu or use CPU version |
| Python version mismatch | Use Python 3.8-3.10 |
| Permission denied | Use `sudo` or conda for installation |
