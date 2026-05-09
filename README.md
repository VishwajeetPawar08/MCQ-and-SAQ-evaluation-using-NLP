# MCQ-and-SAQ-evaluation-using-NLP
NLP-MTU: Evaluating LLM generated solutions with ground reality using Mistral 7b model taken from hugging face on google colab.
The evaluation uses Multiple Choice Questions (MCQ) and Short Answer Questions (SAQ) focused on local nuances in China, Ethiopia, Mexico, and the UK.

# Overview
The primary goal is to assess how well a quantized version of the Mistral model understands regional context, traditions, and local facts. 
* **Baseline Inference:** Standard zero-shot prompting.
* **Improved Inference:** Enhanced prompting or processing to better capture cultural nuances.

# Setup and Requirements
The notebook is designed to run in a Google Colab environment, it ran on A100.

# Dependencies
* Transformers
* scikit-learn
* pandas
* numpy
* bitsandbytes
* huggingface_hub
* torch
* accelerate

# Dataset Information
The evaluation utilizes a dataset containing cultural questions:
File: mc_questions_file-1.csv taken from BLEnD.
Locales: China, Ethiopia, Mexico, and the UK.
Sampling: 
  * 300 samples are taken from each locale (1,200 rows total) for MCQ
  * 500 samples are taken from each locale (2000 rows total) for SAQ

# Project Workflow
  * Authentication of Huggingface for model
  * Data Loading
  * Model Initiallization(Mistral) using quantization
  * Baseline implementaion
  * Improvements beyond baseline (only for MCQ because of time constraint)
  * Result analysis
