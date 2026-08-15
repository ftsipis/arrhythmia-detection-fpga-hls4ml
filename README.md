# On the Implementation of Low-Cost Neural-Network Models for Cardiac Arrhythmia Detection

## Project Overview

This repository includes the full codebase from my diploma thesis and the related publication, **On the Implementation of Low-Cost Neural-Network Models for Cardiac Arrhythmia Detection**.

- The repository includes several CNN implementations, including the **POOL_v2** model, which was tested experimentally but **not included in the final paper results**.  
- The **MIT-BIH Arrhythmia Dataset** was preprocessed using an open-source script available on GitHub (https://github.com/csaguiar/arrhythmia-detection.git) however, **all model architectures, quantization experiments, and training workflows were independently developed**.  
- Three main quantization approaches were evaluated:
  1. **Post-training quantization (PTQ)** using *hls4ml*:
     - (a) quantizing weights and biases  
     - (b) quantizing weights, biases, and activations  
  2. **Quantization-aware training (QAT)** using *QKeras*, to integrate quantization effects directly during model training.

These experiments aimed to identify the trade-offs between model accuracy, bit precision, and FPGA resource utilization when deploying compact CNN architectures on embedded hardware.


### Key Features

- **Comprehensive implementation** of CNN models for arrhythmia detection using the MIT-BIH Arrhythmia Dataset  
- Includes the **POOL_v2** model, tested experimentally but not included in the final publication  
- Evaluation of three quantization strategies:
  - **Post-Training Quantization (PTQ)** using *hls4ml*  
    - (a) quantization of weights and biases  (The file is just the model name and the bits, POOL_12bits.ipynb)
    - (b) quantization of weights, biases, and activations  (The file starts with f then the name and then the bits, f_POOL_12bits.ipynb)
  - **Quantization-Aware Training (QAT)** using *QKeras*  (The file starts with QKeras then the name and then the bits, QKeras_PLAT_12bits.ipynb)
- The names of the folders where the trained models are saved doesn't much the name of the models
- Analysis of **accuracy vs. hardware efficiency** trade-offs for FPGA deployment  
- Export-ready *hls4ml* configurations for synthesis in **Xilinx Vivado / Vitis HLS**


---

## How to Use

Follow the steps below to set up the environment, prepare the dataset, and run the models.

---

### 1. Clone the repository
```bash
git clone git@github.com:ftsipis/arrhythmia-detection-fpga-hls4ml.git
cd arrhythmia-detection-fpga-hls4ml
```

### 2. Set up the environment
Using Conda (recommended):
```bash
conda env create -f environment.yml
conda activate arrhythmia
```

or using pip:
```bash
pip install -r requirements.txt
```

### 3. Make a folder named hls4ml
This folder is used to save the hls4ml ganerated files.
```bash
mkdir hls4ml
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook
```

### 5. Execute
Open the desired notebook and execute all cells in order.

## Paper

**On the Implementation of Low-Cost Neural Network Models for Cardiac Arrhythmia Detection** — *2026 IEEE International Symposium on Circuits and Systems (ISCAS)*

DOI: 
