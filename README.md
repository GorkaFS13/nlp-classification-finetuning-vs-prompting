# NLP Text Classification: Fine-tuning vs Prompting

Comparative study of supervised fine-tuning vs generative prompting for multi-class text classification.

---

## 🧠 Overview

This project explores two different paradigms for text classification:

- **Fine-tuning (DistilBERT)** → supervised learning  
- **Prompting (LLMs)** → generative approach  

The goal is to evaluate whether large language models can replace task-specific training.

---

## 📊 Task

Classify news articles into 5 categories:

- business  
- entertainment  
- politics  
- sport  
- tech  

Dataset: **BBC News**

---

## ⚙️ Approaches

### 🔹 Fine-tuning (DistilBERT)

- Pretrained transformer model  
- Supervised training  
- Classification head  
- Loss: cross-entropy  

---

### 🔹 Prompting (LLMs)

Models used:
- Qwen-1.5B-Instruct  
- LLaMA-3.1-8B-Instruct  

Approach:
- Task framed as text generation  
- Prompt design with class instructions  
- Model outputs predicted label  

---

### 🔹 Data Augmentation

- Automatic paraphrase generation  
- Dataset expansion  
- Retraining  

---

## 📈 Results

| Model     | Approach     | Accuracy | F1    |
|----------|--------------|----------|------|
| DistilBERT | Fine-tuning | ~0.97    | ~0.97 |
| Qwen      | Prompting   | ~0.18    | ~0.05 |
| LLaMA     | Prompting   | ~0.26    | ~0.11 |

---

## 🔍 Key Insights

- Fine-tuning clearly outperforms prompting in classification tasks  
- LLMs tend to collapse to majority class (bias exploitation)  
- Prompting lacks learning signal and adaptation  
- Data augmentation improves robustness but not significantly performance  

---

## 📁 Project Structure

notebooks/
data/sample/
results/
report/

---

## ▶️ How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/nlp_experiments.ipynb

📄 Report

Detailed analysis available in:
report/nlp_report.pdf

🧠 Key Takeaway

Fine-tuning remains superior to prompting for structured classification tasks when labeled data is available.
