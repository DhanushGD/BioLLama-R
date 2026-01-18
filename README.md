# 📒 BioLLama‑R: Agentic Healthcare AI  
**Domain‑Adaptive Pretraining (DAPT) + Supervised Fine‑Tuning (SFT) + RLHF with Direct Preference Optimization (DPO)**

---

## 🔑 Project Overview
BioLLama‑R is the continuation of our earlier **BioLLama** project, which focused on biomedical language modeling with **DAPT** (Domain‑Adaptive Pretraining) and **SFT** (Supervised Fine‑Tuning).  

In this new project, we extend BioLLama with **RLHF (Reinforcement Learning from Human Feedback)** using **Direct Preference Optimization (DPO)**. The result is a model that combines:
- **Domain understanding** (via DAPT on biomedical corpora)  
- **Task answering ability** (via SFT on curated instruction datasets)  
- **Human preference alignment** (via DPO for safer, clearer, and more useful responses)  

We then integrate this fine‑tuned model into a simple **agentic orchestration pipeline** for healthcare AI tasks.

---

## 🧩 Key Components

### 1. Model Training
- **BioLLama (previous project)**  
  - DAPT: Adapted TinyLlama to biomedical text (PubMed, MedQuAD, etc.)  
  - SFT: Fine‑tuned on medical QA and instruction datasets  

- **BioLLama‑R (this project)**  
  - DPO: Applied RLHF with preference pairs to align outputs with human expectations on **EliasHossain/dpo-medical-o1-synth** dataset
  - Final merged checkpoint: `tinyllama-dpo-merged-final`

### 2. Agentic Orchestration
We demonstrate how BioLLama‑R can act as the **reasoning core** in a multi‑agent workflow:
- **Clinical Intake Agent (Groq LLM)** → Classifies queries as *medical* or *non‑medical*  
- **Medical Reasoning Agent (BioLLama‑R)** → Provides domain‑aware, preference‑aligned reasoning  
- **Safety Agent (Groq LLM)** → Validates and sanitizes outputs for compliance and safety  

This orchestration shows how a fine‑tuned local model can be embedded into autonomous pipelines alongside external LLMs.

## 🚀 Demo Workflow
- **User Query** → “Patient reports chest pain and shortness of breath.”
- **Intake Agent (Groq)** → Classifies as medical
- **Reasoning Agent (BioLLama‑R)** → Generates structured medical reasoning
- **Safety Agent (Groq)** → Rewrites into safe, compliant output
Final output is structured, medically coherent, and aligned with safety guidelines.

## ✨ Highlights
- **RLHF with DPO** → Aligns outputs with human preferences
- **DAPT + SFT foundation** → Strong biomedical domain knowledge and task following
- **Agentic orchestration** → Demonstrates autonomous pipelines with local + external LLMs
- **Safe inference** → Outputs are validated and sanitized before presentation
