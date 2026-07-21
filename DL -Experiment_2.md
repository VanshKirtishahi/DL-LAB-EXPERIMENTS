# EXPERIMENT 2: Google Colab Introduction & GPU/TPU Setup

## Objectives
- Set up Google Colab environment
- Access and configure GPU/TPU accelerators
- Understand cloud-based deep learning workflow
- Compare local vs cloud computing

## Prerequisites
- Google account
- Stable internet connection

## Implementation Steps

### Step 1: Access Google Colab

1. Go to: https://colab.research.google.com
2. Click "New Notebook"
3. Sign in with Google account

### Step 2: Enable GPU Acceleration

```
Menu → Runtime → Change runtime type → Hardware accelerator: GPU
```

### Step 3: Verify GPU Setup

```python
import tensorflow as tf

# Check GPU availability
gpus = tf.config.list_physical_devices('GPU')
print(f"GPU Devices: {gpus}")

# Check detailed GPU info
!nvidia-smi
```

### Step 4: Mount Google Drive

```python
from google.colab import drive
drive.mount('/content/drive')

# Access files from Drive
import os
os.listdir('/content/drive/My Drive')
```

### Step 5: Install Custom Libraries

```python
!pip install tensorflow keras numpy pandas matplotlib
```

### Step 6: Performance Comparison

```python
import time
import tensorflow as tf

# Create large tensor
x = tf.random.normal([10000, 10000])

# Measure computation time
start = time.time()
y = tf.matmul(x, x)
end = time.time()

print(f"Computation time: {end - start:.4f} seconds")
```

## Key Colab Features

| Feature | Benefit |
|---|---|
| Free GPU/TPU | No setup cost |
| Pre-installed libraries | Quick start |
| Cloud storage integration | Easy data access |
| Shareable notebooks | Collaboration |

## Expected Outcomes
- GPU/TPU successfully detected and activated
- Able to run TensorFlow operations on GPU
- Data loaded from Google Drive
- Performance improvement vs CPU
