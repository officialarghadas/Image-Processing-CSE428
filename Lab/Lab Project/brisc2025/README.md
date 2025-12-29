# BRISC 2025 — Brain Tumor MRI Dataset

> **BRISC** (BRain tumor Image Segmentation & Classification) — a curated, expert-annotated T1 MRI dataset for multi-class brain tumor classification and pixel-wise segmentation.

[ArXiv preprint (Fateh et al., 2025)](https://arxiv.org/abs/2506.14318)

---

## 🚀 Overview

BRISC is designed to address common shortcomings in existing public brain MRI collections (e.g., class imbalance, limited tumor types, and annotation inconsistency). It provides high-quality, physician-validated pixel-level masks and a balanced multi-class classification split, suitable for benchmarking segmentation and classification algorithms as well as multi-task learning research.

**Highlights**
- 6,000 T1-weighted MRI slices (5,000 train / 1,000 test)
- Four classes: **Glioma**, **Meningioma**, **Pituitary Tumor**, **No Tumor**
- Pixel-wise segmentation masks reviewed by radiologists
- Slices from three anatomical planes: **Axial**, **Coronal**, **Sagittal**
- Clean, stratified train/test splits and aligned image–mask filenames

---

## 📦 Dataset structure

```
BRISC2025/
├─ classification_task/
│  ├─ glioma/
│  │  ├─ brisc2025_train_00001_gl_ax_t1.jpg
│  │  └─ ...
│  ├─ meningioma/
│  ├─ pituitary/
│  └─ no_tumor/
├─ segmentation_task/
│  ├─ images/
│  │  ├─ brisc2025_train_00001_gl_ax_t1.jpg
│  │  └─ ...
│  └─ masks/
│     ├─ brisc2025_train_00001_gl_ax_t1.png
│     └─ ...
├─ manifest.json
├─ manifest.csv
├─ manifest.json.sha256
├─ manifest.csv.sha256
└─ README.md
```

**Notes:**
- Classification folders contain image-level labels suitable for standard image classification pipelines.
- Segmentation folders contain paired MRI `images/` and corresponding binary `masks/`.
- Image and mask filenames are identical except for file extension (images: `.jpg`, masks: `.png`).
- All images are T1-weighted slices.

---

## 🏷 File naming convention

Filenames follow a consistent pattern to make parsing straightforward:

```
brisc2025_<split>_<index>_<tumor>_<view>_<sequence>.<ext>
```

- `prefix` — `brisc2025`
- `split` — `train` or `test`
- `index` — zero-padded image number (e.g. `00010`)
- `tumor` — `gl` (glioma), `me` (meningioma), `pi` (pituitary), `nt` (no tumor)
- `view` — `ax` (axial), `co` (coronal), `sa` (sagittal)
- `sequence` — `t1` (T1-weighted)

**Example image filename:** `brisc2025_test_00010_gl_ax_t1.jpg`  
**Corresponding mask filename:** `brisc2025_test_00010_gl_ax_t1.png` (same basename, different extension)

---

## 📊 Dataset statistics

- **Total samples:** 6,000 (5,000 train / 1,000 test)
- **Classes:** 4 (balanced distribution across train/test)
- **Planes:** Axial / Coronal / Sagittal (balanced representation)
- **Imaging modality:** T1-weighted MRI
- **Annotation quality:** Reviewed and corrected by medical experts

---

## 📄 Citation

If you use BRISC in your work, please cite:

```bibtex
@article{fateh2025brisc,
  title={Brisc: Annotated dataset for brain tumor segmentation and classification with swin-hafnet},
  author={Fateh, Amirreza and Rezvani, Yasin and Moayedi, Sara and Rezvani, Sadjad and Fateh, Fatemeh and Fateh, Mansoor and Abolghasemi, Vahid},
  journal={arXiv preprint arXiv:2506.14318},
  year={2025}
}
```

---

## 🤝 Acknowledgments

Thanks to the collaborating radiologists and physicians for expert annotation and review.

---

## 🔗 References & inspirations

This dataset drew design and organizational inspiration from widely used brain tumor imaging datasets (e.g., BraTS, Figshare datasets, Kaggle collections). See the project paper for full details and evaluation results.

---


