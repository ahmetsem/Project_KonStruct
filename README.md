# Project KonStruct

**3D Scene Reconstruction of a Faculty Building using Gaussian Splatting**

## Overview

Project KonStruct is a **3D scene reconstruction project** created using the **Gaussian Splatting** method.
The goal of this project is to reconstruct a real-world faculty building into a high-quality, real-time renderable 3D scene.

This project was **completed individually** using a **local personal computer**, following the exact setup and methodology described in the original Gaussian Splatting research paper.

---

## Project Description

In this project, the entire pipeline was performed from scratch:

1. **Data Collection**

   * Captured images of the faculty building from multiple viewpoints.
   * Ensured sufficient coverage for accurate reconstruction.

2. **Data Preparation**

   * Processed the input images.
   * Generated camera parameters and initial point cloud using the required preprocessing steps.

3. **Gaussian Splatting Training**

   * Set up the environment locally.
   * Followed the official implementation and training configuration.
   * Trained the model using the collected dataset.

4. **Result Generation**

   * Produced the final 3D representation as the `output` directory.
   * The output includes:

     * Point cloud data
     * Camera parameters
     * Trained splatting model

5. **Visualization**

   * The reconstructed scene can be visualized using the **SIBR viewer binaries** included in the project.
   * This allows real-time rendering of the reconstructed building.

---

## Original Paper and Method

This project is based on the method described in:

**3D Gaussian Splatting for Real-Time Radiance Field Rendering**
Kerbl, Kopanas, Leimkühler, and Drettakis (2023)

Official repository:
[https://github.com/graphdeco-inria/gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting)

All setup steps, parameters, and training procedures were performed according to the original implementation.

---

## Project Structure

```
Project_KonStruct/
│
├── scene/              # Input scene data
├── output/             # Reconstruction results
│   ├── point_cloud/
│   ├── train/
│   ├── cameras.json
│   ├── cfg_args
│   ├── exposure.json
│   └── input.ply
│
├── SIBR_viewers/       # Visualization binaries
├── train.py            # Training script
├── render.py           # Rendering script
└── README.md
```

---

## How to Visualize the Result

1. Set up  to the `SIBR_viewers` folder. (windows binary modules can be used)
2. Run the viewer binary.
3. Load the scene from the `output` directory.

This will display the reconstructed faculty building in real time.

---

## Hardware and Setup

* Training performed on a **local personal computer**
* Environment configured according to the official Gaussian Splatting repository
* No external servers or cloud resources were used

---

## Author

**Ahmet Sem**
This project was completed **individually** as a 3D reconstruction experiment using Gaussian Splatting.

---

## Acknowledgment

This project is based on the original work:

> Kerbl et al., *3D Gaussian Splatting for Real-Time Radiance Field Rendering*, 2023.

All credit for the method and core implementation goes to the original authors.

