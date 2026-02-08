# Project KonStruct

**3D Scene Reconstruction of a Faculty Building using Gaussian Splatting**

## Overview

Project KonStruct is a **3D scene reconstruction project** created using the **Gaussian Splatting** method.
The goal of this project is to reconstruct a real-world **faculty building** into a high-quality, real-time renderable 3D scene.

This project was completed **individually** (solo work) using my **local personal computer**, while following the setup and methodology described in the original Gaussian Splatting paper and its official implementation.

---

## Project Description

This project covers the full pipeline end-to-end:

1. **Data Collection**

   * Captured images of the faculty building from multiple viewpoints.
   * Ensured broad coverage to allow stable camera registration and reconstruction.

2. **Data Preparation**

   * Prepared the dataset in the expected structure for Gaussian Splatting.
   * Generated and processed camera parameters and metadata.

3. **Gaussian Splatting Training**

   * Installed and configured the training environment locally.
   * Followed the official repository workflow and parameters.
   * Trained the scene using the collected dataset.

4. **Result Generation**

   * Produced the final reconstruction outputs inside the `output/` directory.
   * Output includes point cloud data, camera parameters, and trained Gaussian splats.

5. **Visualization**

   * The reconstructed scene can be viewed using the **SIBR viewer binaries**.
   * These allow interactive, real-time visualization of the reconstructed building.

---

## Original Paper & Official Implementation

This project is based on the method described in:

**3D Gaussian Splatting for Real-Time Radiance Field Rendering**
Kerbl, Kopanas, Leimkühler, and Drettakis (2023)

* Official repository:
  [https://github.com/graphdeco-inria/gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting)

All core steps were performed according to the official implementation and workflow.

---

## Hardware & Operating System

* **GPU:** NVIDIA RTX 5070 Ti
* **OS:** Windows 11
* **Training environment:** Local personal computer

Because RTX 50-series GPUs and Windows setups may cause compatibility issues (CUDA, PyTorch, viewer builds, etc.), several errors were encountered during the installation and training process.

### Setup Solution

To resolve these issues, the environment was configured using the following guide from the original repository:

**Stable Training & Visualization Setup for RTX 50-Series (CUDA 12.8, WSL2 + Windows) #1313**
Ubuntu Linux is recommended because it feels much more stable and predictable when working with modern GPU based frameworks, especially with very new hardware like RTX 50XX series GPUs. On Windows, I often ran into issues caused by mismatches between CUDA, drivers, MSVC, and PyTorch, which led to build errors or unstable behavior. Ubuntu, on the other hand, provides a cleaner and more consistent environment where CUDA, compilers, and PyTorch work together more smoothly. In practice, this resulted in fewer unexpected errors, easier debugging, and a setup that was easier to reproduce, allowing me to focus more on training, rendering, and experimentation instead of troubleshooting system issues.

OS: Ubuntu 22.04 via WSL2

GPU: RTX 50 series

CUDA: 12.8+

PyTorch: CUDA 12.8 build

Build tools: CMake + Ninja

## Conda setup. 

conda create -n gaussian-splatting python=3.10

conda activate gaussian-splatting

## Cuda Pytorch

pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128

## Github Repo

git clone --recursive https://github.com/graphdeco-inria/gaussian-splatting.git

cd gaussian-splatting

## Builds

pip install cmake ninja

set DISTUTILS_USE_SDK=1

pip install diff-gaussian-rasterization --no-build-isolation

pip install simple-knn --no-build-isolation

pip install fused-ssim --no-build-isolation

## Training

python train.py

-s <COLMAP_DATASET_PATH>

-m output/scene_name

## Render
python render.py -m output/scene_name

This step-by-step issue guide was used to achieve a stable setup for both training and visualization.

---

## Repository Structure

```
Project_KonStruct/
│
├── scene/              # Input scene data (prepared dataset)
├── output/             # Reconstruction results
│   ├── point_cloud/
│   ├── train/
│   ├── cameras.json
│   ├── cfg_args
│   ├── exposure.json
│   └── input.ply
│
```

---

## Outputs

The final reconstruction results are stored in the `output/` folder.
These represent the reconstructed 3D scene of the faculty building.

Key files:

* `output/point_cloud/` — Gaussian splat representation
* `output/cameras.json` — camera parameters
* `output/cfg_args` — training configuration
* `output/exposure.json` — exposure metadata
* `output/input.ply` — exported point cloud
* `output/train/...` — training iteration results

---

## Visualization with SIBR Viewer

To visualize the reconstructed scene:

1. Setup to the `SIBR_viewers/` prebuild https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/binaries/viewers.zip
2. Run the appropriate viewer binary.
3. Load the scene from the `output/` directory.

This enables interactive real-time viewing of the reconstructed faculty building.

---

## Author

**ahmetsem - Ahmet Sefa Emre**
This project was completed **individually** as a solo 3D reconstruction experiment using Gaussian Splatting.

---

## Acknowledgments

This project uses the method and implementation from:

> Kerbl et al., *3D Gaussian Splatting for Real-Time Radiance Field Rendering*, 2023.

All credit for the method and core implementation goes to the original authors.
