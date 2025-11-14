---
layout: page
title: Chronic Pancreatitis
description: CT-based Pancreas Segmentation for Chronic Pancreatitis Studies
img: assets/img/chronic pancreatitis.jpg
importance: 1
category: research
# related_publications: false
---

# CT-Based Pancreas Segmentation for Chronic Pancreatitis Studies

A deep learning and medical imaging workflow for pancreas segmentation and radiomic feature analysis.  
Completed as part of my Dual Degree at **IIT Madras**, supervised by **Prof. Ganapathy Krishnamurthi**.

---

## Overview

This project develops a workflow to segment the pancreas from CT scans and extract imaging features that can support downstream studies in **Chronic Pancreatitis (CP)**.

The pipeline includes:

- CT preprocessing using HU windowing  
- Pancreas segmentation with **SwinUNETR**  
- Baseline comparison with **MedSAM**  
- Postprocessing and 3D visualization  
- Radiomic feature extraction  

Slides and the final project report are included in this repository.

---

## Dataset

### Normal Pancreas (CT-82)
- 82 cases  
- High-quality manual pancreas annotations  

### Chronic Pancreatitis (SIMS Hospital)
- 14 labeled CT cases  
- 50 unlabeled CT cases  

![dataset](https://github.com/user-attachments/assets/3ec7081f-34ea-4c97-a41c-30a2ffb063a4)

---

## Segmentation Models

### SwinUNETR (final model)
- Hybrid Swin Transformer + UNETR design  
- Dice Score: **0.851**

![swinunetr](https://github.com/user-attachments/assets/ffaf5e86-150c-4090-8fa1-0b011bc26663)

### MedSAM (baseline)
- Dice Score: **0.79**

SwinUNETR produced better spatial consistency and was used for downstream analysis.

---

## Method Summary

### 1. Preprocessing  
- HU windowing (WW 400, WC 40)  
- Normalization and resizing  

![windowing](https://github.com/user-attachments/assets/949230af-9357-4c96-ace7-9c5c7eaf04ba)

### 2. Segmentation  
- SwinUNETR training and validation  
- Dice-based evaluation  
- Morphological cleanup and 3D visualization  

![seg3d](https://github.com/user-attachments/assets/f3d9d88c-0d76-44c6-84b8-56c5bb9e662a)

### 3. Radiomics  
Extracted intensity, texture, and shape features from the segmented pancreas for downstream clinical analysis.

---

## Key Radiomic Features

<img width="848" height="447" alt="image" src="https://github.com/user-attachments/assets/c93a87d1-f8ff-4646-812f-da53ba7c946e" />


Examples include:

- Cluster Prominence  
- Cluster Shade  
- Cluster Tendency  
- Contrast  
- Correlation  
- Entropy  
- Energy  
- Homogeneity (1 and 2)  
- IMC1 / IMC2  

---

## Results

- SwinUNETR achieved **0.851 DSC**, outperforming MedSAM  
- Postprocessed masks had clearer organ boundaries  
- Extracted a rich set of radiomic features (shape, texture, intensity)  
- Segmentation + radiomics workflow provides a solid foundation for future CP studies

---

## Future Work

- Semi-supervised training using unlabeled SIMS data  
- Larger multi-institutional dataset  
- Integration of clinical variables  
- Feature selection and dimensionality reduction  
- End-to-end multimodal models for prognostic studies  

---

## Acknowledgements

Special thanks to **Prof. Ganapathy Krishnamurthi** and **Dr. Vel Murugan** for guidance throughout this project.
