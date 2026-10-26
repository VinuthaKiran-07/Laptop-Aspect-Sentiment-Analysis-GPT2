# Aspect-Level Sentiment Analysis for Laptop Reviews Using GPT-2

## Project Overview

This project implements aspect-level sentiment analysis using a fine-tuned GPT-2 Small (124M) language model. It identifies customer sentiment toward individual laptop features such as battery life, screen quality, and keyboard performance.

Unlike traditional sentiment analysis, the model predicts the sentiment of a specific aspect within a review, classifying it as Positive, Negative, or Neutral.

## Dataset

- Dataset: SemEval-2014 Task 4 — Laptop Reviews
- Training samples: 1,995
- Validation samples: 318
- Test samples: 638
- Maximum sequence length: 128 tokens

## Technologies Used

Python, PyTorch, GPT-2 Small (124M), tiktoken, pandas, scikit-learn, Matplotlib, and Gradio.

## Model Implementation

The project uses a custom GPTModel architecture initialized with pretrained GPT-2 weights. Its original output head was replaced with a three-class classification head.

The final transformer block, final normalization layer, and classification head were fine-tuned using cross-entropy loss and the AdamW optimizer.

## Experimental Results

| Metric | Result |
|---|---|
| Baseline Validation Accuracy | 12.89% |
| Fine-Tuned Validation Accuracy | 79.56% |
| Final Test Accuracy | 72.41% |
| Final Test Macro-F1 | 66.75% |
| Training Epochs | 3 |

## Application

An interactive Gradio application accepts a laptop review and a selected aspect, then predicts its sentiment.

**Example:**

Review: "The screen is excellent, but the battery life is terrible."

- Aspect: screen → Positive
- Aspect: battery → Negative

## How to Run

1. Open the project notebook in Kaggle with GPU acceleration and Internet access enabled.
2. Install the dependencies listed in `requirements.txt`.
3. Execute the preprocessing and GPT-2 model setup cells.
4. Fine-tune the classifier to generate a checkpoint, or load a compatible checkpoint saved from a previous training run.
5. Execute the inference and Gradio cells to launch the application.

**Note:** Model weight files are excluded from the repository in accordance with the course submission instructions.

## Project Category

MP-C — Classification Fine-Tuning

**Course:** Large Language Models (ISE23704C)

**Institution:** Global Academy of Technology, Bengaluru

**Academic Year:** 2026–27

## Sustainable Development Goals

- SDG 9 — Industry, Innovation and Infrastructure
- SDG 12 — Responsible Consumption and Production

## AI Assistance Declaration

AI assistance was used for coding guidance, debugging, documentation preparation, and report drafting. Model training, evaluation, and application testing were carried out in the Kaggle environment.
