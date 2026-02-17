# medical-qa-assistant-minilm
Lightweight Medical Q&amp;A Assistant built by fine-tuning MiniLM on curated MedQuAD dataset with AutoTrain.
🧠 Medical Q&A Assistant
Fine-Tuning all-MiniLM-L6-v2 Using Hugging Face AutoTrain
📌 Project Overview

This project demonstrates fine-tuning a lightweight sentence transformer model (all-MiniLM-L6-v2) on a curated Medical Question Answering dataset (MedQuAD subset) using Hugging Face AutoTrain.

The goal is to build a domain-specialized medical Q&A assistant capable of generating context-aware, medically relevant responses across 40 different medical focus areas.

The final solution is deployed via a Gradio interface in Google Colab for interactive testing.

🎯 Objectives

Fine-tune a Mini Language Model for domain-specific medical Q&A

Ensure balanced performance across 40 medical categories

Build a lightweight, deployable medical assistant prototype

Demonstrate end-to-end workflow:

Data preparation

Model fine-tuning

Model deployment

Functional testing via Gradio

🚩 Problem Statement

General-purpose LLMs may generate generic or inaccurate responses when dealing with medical queries. Healthcare applications require:

Domain adaptation

Balanced topic coverage

Controlled fine-tuning

Reliable answer mapping

This project fine-tunes a MiniLM model using a curated MedQuAD subset to improve accuracy and contextual reliability for healthcare-related questions.

📊 Dataset Description

Dataset Name: clean_MedQuAD_autotrain_ready.csv
Source: Curated subset of MedQuAD
Type: Extractive Question Answering
Size: 520 rows
Structure:

40 medical focus categories

13 Q&A pairs per category (balanced sampling)

Columns
Column	Description
Question	User-style medical query
Answer	Concise curated medical response
Sample Focus Areas

Alzheimer’s Disease

Breast Cancer

Diabetes

Heart Disease

Asthma

Stroke

Prostate Cancer

Balanced sampling ensures uniform representation across topics.

👤 User Scenario

A caregiver supporting a family member diagnosed with Alzheimer’s disease may ask:

“What are the early warning signs of Alzheimer’s?”

“Is there treatment to slow progression?”

“How can families provide support?”

The fine-tuned assistant retrieves medically relevant responses grounded in trusted Q&A pairs.

Similarly, users can ask:

“What foods should a person with diabetes avoid?”

The system provides concise, context-aware medical guidance.

🏗 Model & Training Details

Base Model:
sentence-transformers/all-MiniLM-L6-v2

Task Type:
Semantic Textual Question Answering

Training Platform:
Hugging Face AutoTrain (CPU Basic Space)

⚙️ Fine-Tuning Configuration
Column Mapping

sentence1 → Question

sentence2 → Answer

Hyperparameters
{
  "optimizer": "adamw_torch",
  "scheduler": "linear",
  "batch_size": "8",
  "epochs": "3",
  "gradient_accumulation": "1",
  "lr": "0.00005",
  "max_seq_length": "128"
}

🚀 Training Workflow
1️⃣ Setup AutoTrain Space

Create new project

Select CPU Basic hardware

Authorize Hugging Face account

2️⃣ Configure Project

Task: ST Question Answering

Parameter Mode: Basic

Select base model

Name project

3️⃣ Upload Dataset

Upload CSV file

Map columns correctly

Adjust hyperparameters

4️⃣ Start Training

Monitor logs:

Setting up training arguments

Starting training

Finished training

Pushing model to hub

📦 Model Deployment

After training:

Model is automatically pushed to Hugging Face Model Hub

Search using your username

Model can be accessed via model ID

🌐 Gradio Interface

A simple Gradio web interface is created in Google Colab to:

Load fine-tuned model

Accept user medical queries

Display generated answers

Compare fine-tuned vs base model performance

📈 Expected Outcomes

Improved domain relevance

Better semantic alignment between questions and answers

Balanced performance across medical topics

Lightweight deployable healthcare assistant

🔐 Governance & Ethical Considerations

Intended for educational purposes

Not a replacement for professional medical advice

Designed using curated and trusted medical Q&A sources

Demonstrates domain adaptation methodology

🛠 Tech Stack

Hugging Face AutoTrain

sentence-transformers

MiniLM

Gradio

Google Colab

Python

🔮 Future Enhancements

Expand dataset size

Add evaluation metrics (F1, accuracy, recall)

Integrate RAG architecture

Deploy as API endpoint

Add monitoring & model governance layer

Explore MLOps pipeline integration

👤 Author

Raju Kumar
AI/ML | Generative AI | Pharma Digital Transformation
Hyderabad, India
