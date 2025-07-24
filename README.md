# 💬 Four Horsemen Classifier — Toxic Relationship Dialogue Detection

This project is a prototype machine learning system designed to detect unhealthy communication patterns between couples, inspired by Dr. John Gottman’s *Four Horsemen of the Apocalypse* theory on relationship failure: **Criticism, Contempt, Defensiveness, and Stonewalling**.

The goal is to enable real-time or recorded analysis of conversations to promote healthier communication and reduce long-term relational conflict and potential divorce.

---

## 🧠 What It Does

Given a short dialogue between two partners, this system:

- **Analyzes** the conversation using sentence-level embeddings
- **Classifies** it into one or more of the Four Horsemen categories
- Optionally detects and labels **healthy communication**
- Returns predictions that help couples become aware of toxic patterns

---

## 📁 Dataset

The model was trained on a **synthetic dataset** of 500 examples:

- 400 labeled as one or more of the Four Horsemen categories
- 100 labeled as **healthy communication**
- Each conversation contains 1–2 back-and-forth exchanges to simulate real dialogue

### Labels:

- `criticism`
- `contempt`
- `defensiveness`
- `stonewalling`
- `healthy`

> Data was designed with diverse phrasing and realistic tone variation to simulate real couple interactions.

---

## 🔧 How It Works

### 1. Embedding Layer
Uses [**Sentence-BERT** (`all-MiniLM-L6-v2`)](https://www.sbert.net/docs/pretrained_models.html) to convert each conversation into a vector representation.

### 2. Classifier
A **Random Forest** model wrapped in `OneVsRestClassifier` is trained to support multi-label classification.

### 3. Evaluation
Achieves **>97% F1 score** across all Four Horsemen categories on the test set. Handles multiple labels per conversation (e.g., `["contempt", "defensiveness"]`).


