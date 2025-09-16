# LIPINC-V2: Detecting Lip-Syncing Deepfakes  
*Vision Temporal Transformer for Analyzing Mouth Inconsistencies*  

Soumyya Kanti Datta, Shan Jia, Siwei Lyu  

[![Python](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/) 
[![License: CC BY-NC](https://img.shields.io/badge/License-CC%20BY--NC-green.svg)](./LICENSE)
[![arXiv](https://img.shields.io/badge/arXiv-2504.01470-b31b1b.svg)](https://arxiv.org/abs/2504.01470)

---

## 📌 Table of Contents
- [Abstract](#-abstract)
- [LipSyncTIMIT Dataset](#-lipsynctimit-dataset)
- [Installation](#-installation)
- [Inference](#-inference-detect-lip-sync-deepfakes)
- [Results](#-results)
- [Citation](#-citation)
- [References](#-references)

---

## 📝 Abstract
Deepfakes are AI-generated media in which the original content is digitally altered to create convincing but manipulated images, videos, or audio. Among the various types of deepfakes, lip-syncing deepfakes are one of the most challenging to detect. In these videos, a person's lip movements are synthesized to match altered or entirely new audio using AI models.  

Unlike other deepfakes, artifacts in lip-syncing videos are confined to the **mouth region**, making them subtle and harder to spot. We propose **LIPINC-V2**, a detection framework that leverages a **vision temporal transformer with multihead cross-attention** to identify spatiotemporal inconsistencies across frames. Our model captures both short-term and long-term variations in mouth movement.  

Additionally, we introduce **LipSyncTIMIT**, a new dataset generated using five state-of-the-art lip-syncing models. Experiments on LipSyncTIMIT and benchmark datasets demonstrate that LIPINC-V2 achieves **state-of-the-art performance**.  

<div align="center">
  <img src="./Images/LIPINCV2.png" width="800" alt="LIPINC-V2 Framework"/>
</div>

---

## 🎬 LipSyncTIMIT Dataset
LipSyncTIMIT includes **202 real videos** from the VidTIMIT dataset and **9,090 lip-sync deepfake videos**, plus compressed versions.  

- Real audio samples: **LRS2 dataset**  
- AI-generated audio samples: **LibriSeVoc dataset**  
- Forged with **5 lip-sync methods**: Diff2Lip, Video Retalking, Wav2Lip, Wav2Lip-GAN, IP-LAP  
- Compressed versions with **CRF=23** and **CRF=40**  

<div align="center">
  <img src="./Images/LipSyncTIMIT1.png" width="800" alt="LipSyncTIMIT Dataset"/>
</div>

📥 **[Request Dataset Access](https://docs.google.com/forms/d/e/1FAIpQLSeKn-OAlJKcOZTU1k6GXVZZjkIuHbGs3am9ScvqkKE7M35psA/viewform?usp=sharing)**  

<details>
<summary>Dataset Structure (click to expand)</summary>

```text
LipSyncTimit Dataset
├── Original Size (3,232 videos)
│   ├── RealVideo (202)
│   ├── FakeVideo-OriginalAudio (1010)
│   │   ├── Diff2Lip
│   │   ├── Video_Retalking
│   │   ├── Wav2lip
│   │   ├── Wav2lip_GAN
│   │   └── IP_LAP
│   ├── FakeVideo-RealAudio (1010)
│   └── FakeVideo-FakeAudio (1010)
├── LipSyncTimit_compression23 (3,232 videos)
└── LipSyncTimit_compression40 (3,232 videos)
````

</details>

🔒 **License & Usage Terms**
LipSyncTIMIT is for **non-commercial research purposes only**.
All original sources: VidTIMIT (videos), LRS2 (real audio), LibriSeVoc (fake audio).

---

## ⚙️ Installation

```bash
git clone https://github.com/Rukh-sana/Multi-Modal-Deepfake-Detection.git
cd Multi-Modal-Deepfake-Detection
pip install -r requirements.txt
```

Download **dlib’s pre-trained facial landmark detector**:
👉 [Google Drive Link](https://drive.google.com/file/d/1-Uc2rH1tiKZEh9NwmgmBFZT_6xDvGBSD/view?usp=sharing)
Place it in the same folder as `demo.py`.

---

## 🚀 Inference: Detect Lip-Sync Deepfakes

Run detection with the pre-trained model:

```bash
python demo.py --input_path path/to/video.mp4 --output_path results/
```

* Input must be **.mp4 format**
* The video should contain **only one subject**
* Each frame should contain **a single face**
* Output is saved as: `video_demo.mp4`

---

## 📊 Results

| Dataset      | Method    | Accuracy (%) |
| ------------ | --------- | ------------ |
| LipSyncTIMIT | LIPINC-V2 | **XX.X**     |
| Benchmark-1  | Baseline  | YY.Y         |
| Benchmark-2  | Baseline  | ZZ.Z         |

*(Replace with your experimental results table.)*

---

## 📜 Citation

If you use **LIPINC-V2** or **LipSyncTIMIT**, please cite:

```bibtex
@article{datta2025detecting,
  title={Detecting Lip-Syncing Deepfakes: Vision Temporal Transformer for Analyzing Mouth Inconsistencies},
  author={Datta, Soumyya Kanti and Jia, Shan and Lyu, Siwei},
  journal={arXiv preprint arXiv:2504.01470},
  year={2025}
}
```

---

## 📚 References

<details>
<summary>Click to expand</summary>

* Datta, Jia, and Lyu, *Exposing lip-syncing deepfakes from mouth inconsistencies*, ICME 2024.
* Sanderson & Lovell, *VidTIMIT Dataset*, 2009.
* Afouras et al., *Deep audio-visual speech recognition*, IEEE TPAMI 2018.
* Sun et al., *AI-synthesized voice detection using neural vocoder artifacts*, CVPR 2023.
* Mukhopadhyay et al., *Diff2Lip: Audio conditioned diffusion models for lip-synchronization*, WACV 2024.
* Cheng et al., *VideoRetalking: Audio-based lip synchronization*, SIGGRAPH Asia 2022.
* Prajwal et al., *Wav2Lip: A lip sync expert is all you need*, ACM MM 2020.
* Zhong et al., *Identity-preserving talking face generation*, CVPR 2023.

</details>
```


Do you also want me to **add GitHub Actions CI workflow** (for auto testing, linting, badges) so it looks like a polished open-source repo?
