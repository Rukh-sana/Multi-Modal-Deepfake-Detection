# Multi-Modal-Deepfake-Detection
A multi-modal deepfake detection framework fusing lip-sync errors and frame artifacts. Uses Vision Temporal Transformers (VTT) and cross-attention for robust detection.
# Multi-Modal Deepfake Detection

A deepfake detection framework that identifies manipulated videos by analyzing **lip-sync inconsistencies** and **frame-level artifacts** using Vision Temporal Transformers (VTT) and multi-head cross-attention.

![Demo](media/image3.png) *(Add a screenshot if available)*

## Features
- Detects lip-sync deepfakes via **spatiotemporal inconsistencies**.
- Uses **RGB + delta frames** for local/global temporal analysis.
- Trained on `LipSyncTIMIT`, `FakeAVCeleb`, and `KODF` datasets.
- Achieves **0.99 AUC** on in-domain tests.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Rukh-sana/Multi-Modal-Deepfake-D.git
