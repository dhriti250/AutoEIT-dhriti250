# AutoEIT GSoC 2026 – Evaluation Test II

**Author:** Dhriti Singh  
Backend & AI Developer | GSoC 2026 Applicant  

---

## 📌 Project Overview

This project implements an automated scoring system for the **Elicited Imitation Task (EIT)**, a research tool used to evaluate language proficiency.

The goal is to replace manual scoring with a **consistent, reproducible, and interpretable system** that compares learner responses with target sentences and assigns scores based on similarity and linguistic accuracy.

The scoring approach combines:
- Sequence-based similarity (structure awareness)
- Penalty-based adjustments (handling missing and extra words)

---

## 📂 Dataset

The dataset used in this project is provided as part of the AutoEIT evaluation test and is **not included in this repository**.

---

## 🧠 Approach

This implementation prioritizes **reproducibility and interpretability**, aligning with research requirements for consistent evaluation.

### 1. Text Preprocessing
- Convert text to lowercase  
- Remove punctuation and noise  
- Normalize inputs for fair comparison  

### 2. Sentence Comparison
- Compare:
  - Target sentence (*Stimulus*)
  - Learner response (*Transcription*)
- Use `SequenceMatcher` to capture structural similarity  

### 3. Rule-Based Scoring

Scores are assigned based on similarity thresholds:

| Similarity | Score |
|----------|------|
| > 0.90   | 5    |
| > 0.75   | 4    |
| > 0.60   | 3    |
| > 0.40   | 2    |
| ≤ 0.40   | 1    |

Additionally:
- Penalties are applied for **missing and extra words**
- This improves alignment with **human scoring behavior**

---

## ⚙️ Tech Stack

- Python  
- Pandas  
- difflib (`SequenceMatcher`)  
- Jupyter Notebook  

---

## ▶️ How to Run

1. Place dataset in `data/`
2. Open `notebooks/autoeit_test.ipynb`
3. Run all cells  
4. Output file will be saved in `output/`

---

## 📊 Output

- Generates an Excel file with sentence-level scores  
- Supports multiple participants (multiple sheets)  
- Produces varied score distributions across participants  

---

## 🚀 Future Improvements

- Word-level alignment scoring  
- Semantic similarity using embeddings  
- Handling disfluencies (e.g., `[pause]`, `[gibberish]`)  
- More robust rubric-based scoring  

---
