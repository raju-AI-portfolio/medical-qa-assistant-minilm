
# 🏥 Medical Q&A Assistant  
Lightweight Medical Q&A Assistant built by fine-tuning MiniLM on curated MedQuAD dataset with AutoTrain.

---

## 📌 Project Overview

This project demonstrates the fine-tuning of a lightweight language model, **sentence-transformers/all-MiniLM-L6-v2**, for domain-specific **Medical Question Answering (Q&A)** using Hugging Face AutoTrain.

The goal is to build a **domain-specialized medical Q&A assistant** capable of generating reliable, context-aware responses to healthcare-related queries.

The final solution includes:
- Dataset preparation
- Model fine-tuning using AutoTrain
- Deployment via Gradio interface
- Model publishing to Hugging Face Hub

---

## 🎯 Objectives

- Fine-tune MiniLM on a curated medical Q&A dataset
- Ensure balanced learning across 40 medical focus areas
- Develop a lightweight medical assistant prototype
- Deploy and test using a Gradio web interface
- Compare fine-tuned vs. base model performance

---

## 🧠 Problem Statement

Medical question-answering systems must handle diverse conditions, complex terminology, and sensitive health-related queries.

Large language models without domain adaptation may generate:
- Generic responses
- Inaccurate medical advice
- Poor contextual grounding

This project addresses this challenge by fine-tuning MiniLM on a curated subset of the **MedQuAD dataset**, improving domain-specific accuracy and reliability.

---

## 📊 Dataset Description

**Dataset Name:** `clean_MedQuAD_autotrain_ready.csv`  
**Source:** Curated subset of MedQuAD  
**Total Samples:** 520 rows  

### Structure
- **40 medical focus categories**
- **13 Q&A pairs per category**
- Balanced sampling across conditions

### Columns
- `Question` – User-style medical queries  
- `Answer` – Curated medical responses  

### Example Focus Areas
- Alzheimer’s Disease
- Breast Cancer
- Diabetes
- Heart Disease
- Asthma
- Stroke
- Prostate Cancer

The balanced sampling ensures uniform representation across medical domains.

---

## 🛠️ Model Details

| Component | Value |
|-----------|--------|
| Task | Sentence Transformer Question Answering |
| Base Model | sentence-transformers/all-MiniLM-L6-v2 |
| Training Platform | Hugging Face AutoTrain |
| Hardware | CPU (Hugging Face Space) |
| Parameter Mode | Basic |

### Hyperparameters Used

```json
{
  "optimizer": "adamw_torch",
  "scheduler": "linear",
  "batch_size": "8",
  "epochs": "3",
  "gradient_accumulation": "1",
  "lr": "0.00005",
  "max_seq_length": "128"
}
```

---

## 🚀 Implementation Steps

### Step 1: Setup AutoTrain
- Created new project in Hugging Face AutoTrain
- Duplicated space with CPU Basic hardware
- Authorized access to Hugging Face account

### Step 2: Configure Project
- Task: ST Question Answering
- Base Model: `all-MiniLM-L6-v2`
- Parameter Mode: Basic

### Step 3: Upload Dataset
- Dataset source: Local
- Column mapping:
  - `sentence1` → Question
  - `sentence2` → Answer

### Step 4: Fine-Tuning
- Started AutoTrain job
- Monitored logs
- Training completed successfully
- Model pushed to Hugging Face Hub

### Step 5: Model Deployment
- Accessed fine-tuned model via Hugging Face Model Hub
- Integrated model into Gradio interface

---

## 🖥️ Gradio Interface

A simple Gradio web application was created to test the fine-tuned model.

Users can input medical queries such as:

- "What are the early warning signs of Alzheimer’s disease?"
- "What foods should a person with diabetes avoid?"
- "Is there treatment available for stroke recovery?"

The assistant returns medically relevant responses grounded in the fine-tuned dataset.

---

## 👤 User Scenario

Imagine a caregiver supporting a family member diagnosed with Alzheimer’s disease.

Instead of searching multiple websites, they can ask:

> “How can families support someone living with Alzheimer’s?”

The assistant provides concise, trusted, knowledge-based responses, improving accessibility to healthcare information.

---

## 📈 Key Learnings

- Domain adaptation significantly improves model relevance
- Balanced datasets enhance generalization
- Mini language models can be efficient for healthcare applications
- AutoTrain simplifies end-to-end fine-tuning workflows
- Lightweight models are suitable for CPU-based deployment

---

## 🔮 Future Improvements

- Expand dataset size
- Integrate Retrieval-Augmented Generation (RAG)
- Add evaluation metrics (Precision@K, cosine similarity benchmarking)
- Deploy as a public Hugging Face Space
- Add disclaimer for medical advisory limitations

---
## 🔮 Click the link below for Live Demo

https://bdfb03ba6b8fa07bea.gradio.live

---
## ⚠️ Disclaimer

This model is built for educational purposes and should not be used as a substitute for professional medical advice.

---

## 📬 Author

**Raju Kumar**  
AI & Transformation Professional  
Focused on AI-driven healthcare and domain-specific LLM applications

---

## 📌 License

This project is created for academic and demonstration purposes.

