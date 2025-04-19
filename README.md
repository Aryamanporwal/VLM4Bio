# VLM4Bio: Species Classification Replication Project

A partial replication of the NeurIPS 2024 paper [VLM4Bio: A Benchmark Dataset to Evaluate Pretrained Vision-Language Models for Trait Discovery from Biological Images](https://proceedings.neurips.cc/paper/2024/file/...). This repository focuses on the **Species Classification** task, assessing the zero-shot performance of various open‑source Vision‑Language Models (VLMs) on fish, bird, and butterfly images.

## 📋 Table of Contents

- [🔍 Introduction](#-introduction)
- [✨ Features](#-features)
- [📊 Dataset](#-dataset)
- [🧠 Models](#-models)
- [📁 Project Structure](#-project-structure)
- [⚙️ Installation](#️-installation)
- [🚀 Usage](#-usage)
- [🧪 Experiments](#-experiments)
- [📈 Results](#-results)
- [📊 Presentation Summary](#-presentation-summary)
- [🛠 Contributing](#-contributing)
- [✉️ Contact](#-contact)

---

## 🔍 Introduction

Vision‑Language Models (VLMs) have shown remarkable zero‑shot capabilities on generic vision tasks. **VLM4Bio** introduces a benchmark to evaluate these models on trait discovery within biological images. This replication project zeroes in on the Species Classification task, measuring how well pretrained VLMs can identify species across three taxonomic groups without any fine‑tuning.

## ✨ Features

- **Zero‑Shot Evaluation**: Test pretrained models directly on unseen biological images.
- **Difficulty Tiers**: Split images into *Easy*, *Medium*, and *Hard* subsets to analyze performance across levels of visual challenge.
- **Prompt Engineering**: Compare different prompting strategies, including contextual prompts, dense captions, and Chain‑of‑Thought (CoT).
- **Robustness Checks**: Perform False‑Confidence Test (FCT) and "None of the Above" (NOTA) experiments to gauge model reliability.

## 📊 Dataset

Images and metadata are hosted on Kaggle:

- 📁 [Image Dataset (10k images)](https://www.kaggle.com/datasets/aryamanporwal12/vlm4bio-10k-images)
- 🧾 [Metadata & CSV Files](https://www.kaggle.com/datasets/aryamanporwal12/vlm4bio-csv)

CSV files include:

- `fish.csv` — Ground‑truth labels and image paths for fish species.
- `bird.csv` — Metadata for bird species classification.
- `butterfly.csv` — Metadata for butterfly species classification.

The CSVs contain the following columns:

| Column      | Description                                   |
|-------------|-----------------------------------------------|
| `image_path`| Local path to the image file                  |
| `question`  | Classification prompt/question                |
| `options`   | List of candidate species (for MC tasks)      |
| `answer`    | Ground‑truth species label (zero‑shot target) |

## 🧠 Models

We evaluated the following pretrained VLMs (from Hugging Face):

| Model Alias                       | HF Model ID                         |
|-----------------------------------|-------------------------------------|
| BLIP2-Flan-T5                     | `Salesforce/blip2-flan-t5-xxl`      |
| BLIP-VQA-Base                     | `Salesforce/blip-vqa-base`          |
| Qwen2-VL-7B-Instruct              | `Qwen/Qwen2-VL-7B-Instruct`         |
| LLaVA-1.5-7B                      | `llava-hf/llava-1.5-7b-hf`          |
| Qwen2-VL-2B-Instruct              | `Qwen/Qwen2-VL-2B-Instruct`         |
| BLIP-VQA-CapFilt-Large            | `Salesforce/blip-vqa-capfilt-large` |

*Feel free to add or swap models by updating the `--model_name` argument.*

## 📁 Project Structure

```text
VLM4Bio/
├── data_for_easy_med_hard/       # Split images by difficulty
│   ├── easy/
│   ├── medium/
│   └── hard/
├── bird.csv                      # Bird metadata
├── butterfly.csv                 # Butterfly metadata
├── fish.csv                      # Fish metadata
├── main.py                       # Run experiments on easy/medium
├── main_for_hard_data.py         # Run experiments on hard data
├── merging_data.py               # Utilities to merge/preprocess CSVs
├── results/                      # Output logs and metrics for exp1
├── results_exp2/                 # Output logs and metrics for exp2
├── species classification.pdf    # Detailed experiment report
├── Project_Presentation final.pdf# Slide deck overview
└── README.md                     # ← You are here
```
## ⚙️ Installation
```bash
#clone the repo
git clone https://github.com/Aryamanporwal/VLM4Bio.git
cd VLM4Bio

# create & activate venv
python3 -m venv .venv
source .venv/bin/activate

# install deps
pip install torch torchvision transformers pandas numpy scikit-learn matplotlib
```
(If a requirements.txt is available, you can instead run pip install -r requirements.txt.)

##🚀 Usage
```bash
#Species Classification (Easy/Medium)
python main.py \
  --model_name Salesforce/blip2-flan-t5-xxl \
  --dataset easy
#--model_name: HF model identifier
#--dataset: easy, medium
#Species Classification (Hard)
python main_for_hard_data.py \
  --model_name llava-hf/llava-1.5-7b-hf
```
## 🧪 Experiments

- **Zero‑Shot Accuracy**: Measures standard classification accuracy.
- **Prompt Ablation**: Compares contextual vs. CoT prompts.
- **Robustness Tests**: FCT and NOTA to test model confidence and out‑of‑domain handling.

*Detailed methodologies are described in [species classification.pdf](species%20classification.pdf).*

## 📈 Results

- Raw logs and metric summaries are available under `results/` and `results_exp2/`.
- **Key findings**:
  - BLIP2-Flan-T5 achieved highest zero‑shot accuracy on *easy* images.
  - Performance degrades significantly on *hard* subset without CoT prompts.

## 📊 Presentation Summary

The **Project Presentation** (PDF) offers a visual and conceptual overview of the goals, methodologies, and key findings of the replication effort. It outlines:

- Motivation and relevance of biological trait discovery
- Description of the datasets and taxonomy splits
- Challenges in fine-grained species classification
- VLM architectures explored and their comparative performance
- Observations from experiments on difficulty tiers and prompt types

## 🛠 Contributing

Contributions are welcome! To add new models or evaluation protocols:

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/your-change`)  
3. Implement changes and update documentation  
4. Submit a Pull Request

Please follow the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/).

## ✉️ Contact

Maintainer: Aryaman Porwal  
Email: [aryamanlucknow@gmail.com](mailto:aryamanlucknow@gmail.com)

