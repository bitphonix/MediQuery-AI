# MediQuery — Multimodal Medical X-ray Query & Analysis System

> **Author:** Tanishk
> **Version:** 2.0.1 (March 2025)

MediQuery is an advanced **Multimodal Retrieval-Augmented Generation (RAG)** system for analyzing **chest X-rays** and answering **radiology-related queries**. Built on top of the MIMIC-CXR dataset, it combines **image-text retrieval**, **attention-based anatomical analysis**, and **FLAN-T5 generation** to produce accurate, explainable medical reports.

---

## 🔮 Key Features

* ✨ **Multimodal input**: Supports both **textual queries** and **X-ray image uploads**.
* 🧠 **RAG architecture**: Combines **CheXNet** + **BioBERT** embeddings for hybrid retrieval.
* 🔎 **Visual interpretability**: Generates **heatmaps** and **region labels** from image attention.
* 🖊️ **Structured outputs**: Produces **Findings**, **Impression**, and **Confidence** levels.
* 📊 **Built-in evaluation**: Measures **precision**, **recall**, and **F1** against ground truth.
* 🤖 **Fully local**: No internet or API dependency. Runs in **Google Colab** with Drive.

---

## 📂 Project Structure

```
mediquery/
├── images/                         # Sample image assets
├── index.html                      # Simple project info page (no backend)
├── style.css                       # Styling for index.html
├── Screenshots/                    # UI + output snapshots
├── MediQuery - AI.ipynb            # Full pipeline notebook (all code here)
```

> ✅ All code, training, inference, visualization, and UI logic is inside `MediQuery - AI.ipynb`.

---

## 💡 How It Works

### 📁 Input Layer

* Accepts a **chest X-ray image** or a **free-text medical query**.
* Handles **image preprocessing**, **query analysis**, and **lazy model loading**.

### ⚙️ Processing Layer

* Extracts embeddings using **CheXNet** and **BioBERT**.
* Performs **hybrid retrieval** via **FAISS**, scoring both image and text similarity.
* Enhances relevance using **diversification** and **region-aware attention**.

### 💮 Generation Layer

* Assembles a **context window** from retrieved MIMIC-CXR cases.
* Uses **FLAN-T5** (fine-tuned) to generate findings and impression.
* Applies **visual attention analysis** and **confidence calibration**.

### 📄 Output Layer

* Presents:

  * Structured **Findings** & **Impression**
  * **Attention heatmap** overlay
  * Highlighted **anatomical regions**
  * **Confidence level** with explanation

---

## 🏛️ System Architecture

### High-level Pipeline

### Hybrid RAG Flow

### Memory Management Logic

### Web Interface Overview

---

## 🚧 Preprocessing, Training, and Paths

To preserve your privacy, all **Google Drive paths** in the code (e.g. `/content/drive/MyDrive/FinalMediQuery/...`) should be replaced with:

```python
# TODO: Replace this with your own Google Drive path
'/your/custom/drive/path/here'
```

You can use placeholders like `your_path_here` when sharing or publishing.

---

## 📊 Evaluation & Performance

* **Automatic ground truth matching** using MIMIC-CXR impressions
* Supports **differentiation queries** (e.g. pneumonia vs. atelectasis)
* Tracks **precision**, **recall**, **F1**, and **runtime** of each module

---

## 🚀 Getting Started

> **Note**: MediQuery was built for **Google Colab** with access to **Google Drive**

1. Upload the notebook: `MediQuery - AI.ipynb`
2. Mount your Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Replace all `save_dir` / `output_dir` paths with your own Drive directory
4. Run cells to preprocess, embed, fine-tune, and launch the Gradio interface

---

## 🌟 Credits

* **MIMIC-CXR** dataset by MIT Lab for Computational Physiology
* **CheXNet** by Stanford ML Group
* **BioBERT**, **FLAN-T5**, and **FAISS** by respective authors
* Developed by **Tanishk** as part of a medical AI research project

---

## 📁 License

This project is released for **educational and non-commercial research purposes only.**
Please obtain appropriate licenses for datasets like MIMIC-CXR before using this system in practice.

---

## ⚖️ Disclaimer

MediQuery is **not a medical device**. It does **not diagnose**, treat, or replace professional radiology expertise. Always consult qualified medical professionals for clinical decisions.

---

Thank you for exploring **MediQuery**! ✨
