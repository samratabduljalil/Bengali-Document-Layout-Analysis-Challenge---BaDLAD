# 📄 Multi-Domain Large Bengali Document Layout Analysis 

*Advancing AI capabilities for the 5th most spoken native language worldwide*

---

## 🔎 Project Overview

This project addresses the critical need for **automated document layout analysis in Bengali**, leveraging the groundbreaking **BaDLAD dataset**. It focuses on developing intelligent systems that can automatically **detect and segment structural components** in Bengali documents across multiple domains.

---

## 🧩 Problem Statement

Bengali documents present unique challenges for automated analysis due to:

* Complex **script characteristics** and varied layouts.
* Diverse **multi-domain sources** (newspapers, government docs, books, war records).
* Scarcity of **large annotated datasets** for Bengali document understanding.
* Mixed content requiring **accurate segmentation** (text, images, tables).

---

## 🌍 Real-World Impact

This project enables:

* **OCR Preprocessing** → Accurate layout segmentation improves text recognition.
* **Digital Archiving** → Preserving historical & liberation war documents.
* **Government Digitization** → Automating extraction from official records.
* **Educational Access** → Structured Bengali e-books & magazines.
* **Search & Accessibility** → Better indexing and retrieval of scanned Bengali documents.

---

## ✅ Solution Approach

Our solution employs **advanced computer vision techniques** to detect and segment four primary elements:

* **Paragraphs**: Main textual content blocks.
* **Text Boxes**: Specialized or highlighted text regions.
* **Images**: Embedded visual content.
* **Tables**: Structured data presentations.

---

## 📊 Dataset Analysis

We use the **BaDLAD Dataset** ([paper](https://arxiv.org/abs/2303.05325)), the first large, multi-domain Bengali document dataset.

### Training Set Distribution

| Domain                | Samples | Text-box | Paragraph | Image  | Table | Total Annotations |
| --------------------- | ------- | -------- | --------- | ------ | ----- | ----------------- |
| Historical Newspapers | 516     | 25,452   | 38,990    | 1,252  | 67    | 65,761            |
| New Newspapers        | 96      | 3,978    | 2,507     | 494    | 36    | 7,015             |
| Government Documents  | 77      | 44,017   | 2,260     | 762    | 514   | 47,553            |
| Magazines & Books     | 18,380  | 123,099  | 162,570   | 7,734  | 594   | 293,997           |
| Liberation War Docs   | 60      | 27,330   | 3,262     | 551    | 42    | 10,789            |
| **Total**             | 20,365  | 203,876  | 209,589   | 10,297 | 1,353 | 425,115           |

### Test Set Distribution

| Domain                | Samples | Total Annotations |
| --------------------- | ------- | ----------------- |
| Historical Newspapers | 345     | 43,074            |
| New Newspapers        | 65      | 5,705             |
| Government Documents  | 51      | 30,183            |
| Magazines & Books     | 11,674  | 195,996           |
| Liberation War Docs   | 40      | 7,223             |
| **Total**             | 13,000  | 282,181           |

### Domain Characteristics

* **Historical Newspapers**: Complex multi-column layouts.
* **Government Docs**: Formal structured layouts.
* **Magazines/Books**: Rich with visual + text integration.
* **Liberation War Records**: Unique preservation challenges.

---

## ⚙️ Methodology

### Model Architecture

* **Backbone**: ResNet-50 + Feature Pyramid Network (FPN).
* **Head**: **Mask R-CNN** for joint detection + segmentation.
* **Framework**: **Detectron2** for robust training/inference.

### Key Technical Strategies

* **Multi-Scale Feature Extraction** → handles varied resolutions/layouts.
* **Domain Adaptation** → robust training across domains.
* **Data Augmentation**:

  * Brightness/contrast variations
  * Rotation, flipping
  * Scale & crop

### Hyperparameter Optimization

* **Learning Rates**: 0.005 (best).
* **Warm-Up Iterations**: 500 (best).
* **Training Iterations**: 18,000 (best ).
* **Batch Size**: 8

---

## 🏆 Results

* **Best Score**: **0.88240** with Mask R-CNN (Detectron2).
* **YOLOv8** was tested but did not perform as well for polygonal segmentation.
* Augmentation + hyperparameter tuning were key for robustness.


---

## 🔧 Installation

```python
# Clone repo
!git clone https://github.com/facebookresearch/detectron2.git
%cd detectron2

# Install Detectron2
!pip install -e .

# Install other requirements
!pip install opencv-python-headless albumentations pycocotools matplotlib tqdm
```

## 📌 Resources

* **Dataset**: [Kaggle – Bengali Document Layout Analysis](https://www.kaggle.com/datasets/samratabduljalil/bengali-document-layout-analysis-dl-sprint-2-0)
* **Paper**: [BaDLAD: A Large Multi-Domain Bengali Document Layout Analysis Dataset](https://arxiv.org/abs/2303.05325)
* **Detectron2**: [GitHub](https://github.com/facebookresearch/detectron2)

---

## 📌 Citation

```bibtex
@article{shihab2023badlad,
  title={BaDLAD: A Large Multi-Domain Bengali Document Layout Analysis Dataset},
  author={Shihab, Md Istiak Hossain and Hasan, Md Rakibul and Emon, Mahfuzur Rahman and Hossen, Syed Mobassir and Ansary, Md Nazmuddoha and Ahmed, Intesur and Rakib, Fazle Rabbi and Dhruvo, Shahriar Elahi and Dip, Souhardya Saha and Pavel, Akib Hasan and others},
  journal={arXiv preprint arXiv:2303.05325},
  year={2023}
}
```

---
**Model link:** https://www.kaggle.com/datasets/samratabduljalil/bengali-document-layout-analysis-dl-sprint-2-0

---
## 👨‍💻 Author

**Samrat Abdul Jalil**

* Kaggle: [@samratabduljalil](https://www.kaggle.com/samratabduljalil)
* AI/ML Engineer Enthusiast
