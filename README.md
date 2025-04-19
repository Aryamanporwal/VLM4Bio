# 🧬 VLM4Bio Species Classification - Replication Project

This repository contains a partial replication of the NeurIPS 2024 paper:

> **[VLM4Bio: A Benchmark Dataset to Evaluate Pretrained Vision-Language Models for Trait Discovery from Biological Images](https://proceedings.neurips.cc/paper_files/paper/2024/file/eced4a5fbc776e81b45e2f72447f0164-Paper-Datasets_and_Benchmarks_Track.pdf)**

## 📌 Project Overview

This project focuses **only on the Species Classification** task from the original paper using various open-source Vision-Language Models (VLMs). We aim to evaluate the zero-shot performance of these models on biological images from fish, birds, and butterflies.

## 🧠 Models Used

We used the following pre-trained VLMs for inference:

- `Salesforce/blip2-flan-t5-xxl`
- `Salesforce/blip-vqa-base`
- `Qwen/Qwen2-VL-7B-Instruct`
- `llava-hf/llava-1.5-7b-hf`
- `Qwen/Qwen2-VL-2B-Instruct`
- `Salesforce/blip-vqa-capfilt-large`

## 🖼️ Dataset

A custom dataset inspired by the VLM4Bio format was created and is publicly available on Kaggle:

- 📷 [Images (10K)](https://www.kaggle.com/datasets/aryamanporwal12/vlm4bio-10k-images)
- 📑 [CSV (questions, options, ground truths)](https://www.kaggle.com/datasets/aryamanporwal12/vlm4bio-csv)

The dataset contains:
- Images of fish, birds, and butterflies
- Open-ended and Multiple Choice (MC) questions
- Difficulty levels: Easy, Medium, Hard

## 🧪 Tasks Performed

All species classification experiments and evaluations are documented in this report:

- 📄 [`species classification.pdf`](https://github.com/Aryamanporwal/VLM4Bio/blob/main/species%20classification.pdf)

Tasks include:

- Zero-shot species classification with VLMs
- Prompt engineering: Contextual, Dense Captioning, and Chain-of-Thought (CoT)
- Difficulty-based evaluation (easy/medium/hard)
- Reasoning robustness tests: False Confidence Test (FCT) and None of the Above (NOTA)

## 🎞️ Project Presentation

A detailed presentation including project background, goals, models, methodology, evaluation pipeline, and Gantt chart:

- 🎤 [`Project_Presentation.pdf`](https://github.com/Aryamanporwal/VLM4Bio/blob/main/Project_Presentation%20final.pdf)

## 📄 Reference

- Original Paper: [VLM4Bio - NeurIPS 2024](https://proceedings.neurips.cc/paper_files/paper/2024/file/eced4a5fbc776e81b45e2f72447f0164-Paper-Datasets_and_Benchmarks_Track.pdf)
- Authors: M. Maruf, Arka Daw, Kazi Sajeed Mehrab, et al.

## 🚀 How to Run

Clone the repository:

```bash
git clone https://github.com/your-username/vlm4bio-species-classification.git
cd vlm4bio-species-classification
# VLM4Bio_Replication
