# Mesh Processing & Reconstruction – Mixar Tasks

This repository contains implementations for **Mixar Task 1**, **Task 2**, **Task 3**, and a **Bonus Task**.  
Everything was executed in **Google Colab** using **trimesh**, **NumPy**, and **Matplotlib**.  
No Google Drive mounting and no Open3D were used — all mesh files were uploaded directly into the Colab session.

---

## Repository Structure

```
├── 8 Samples/ # Provided OBJ mesh files
├── Outputs/ # Saved figures, reconstructions, exported PLY files
├── Mixar_Task1.ipynb # Task 1 - Mesh loading & normalization
├── Mixar_Task2.ipynb # Task 2 - Quantization & dequantization
├── Mixar_Task3.ipynb # Task 3 - Full reconstruction + error analysis
├── Bonus_Task.ipynb # Additional seam/quantization experiments
└── README.md # This documentation
```

---

## Task Overview

### Task 1 — Mesh Loading & Normalization
- Load `.obj` meshes using `trimesh.load()`
- Extract vertices and faces
- Apply min–max normalization to fit mesh within [0, 1]
- Visualize normalized mesh
- Save processed outputs in `Outputs/`

---

### Task 2 — Quantization & Dequantization
- Perform **uniform quantization** at different bit depths (8, 12, 16 bit)
- Map normalized floats → integer bins → back to float
- Compute **per-axis MSE / MAE**
- Plot reconstruction error for x, y, and z axes

---

### Task 3 — Full Reconstruction Pipeline
- Load mesh → normalize → quantize → dequantize → denormalize  
- Compare original vs. reconstructed vertices
- Visualize both meshes
- Export reconstruction results
- Generate error graphs and store them in `Outputs/`

---

### Bonus Task — Seam Tokenization Prototype
- Additional tests on mesh seams
- Extra quantization error experiments
- Implemented in its own notebook

---

## How to Run the Notebooks

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
### 2. Open any notebook in Google Colab
### 3. Install dependencies (Colab cell)
```python
!pip install trimesh numpy matplotlib
```
### 4. Load sample meshes
```python
import trimesh, numpy as np

mesh = trimesh.load("8 Samples/sample.obj", process=False)
v = np.array(mesh.vertices)
f = np.array(mesh.faces)
```

No other Dependecies are required
