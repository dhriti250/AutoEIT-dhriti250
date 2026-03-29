# AutoEIT GSoC 2026 – Evaluation Test II

**Author:** Dhriti Singh  
Backend & AI Developer | GSoC 2026 Applicant


## 📌 Project Overview
This project implements an automated scoring system for the Elicited Imitation Task (EIT), a research tool used to evaluate language proficiency.
**Improved scoring by incorporating word-level overlap to better approximate meaning-based evaluation.**

**Scoring was refined by incorporating penalties for missing and extra words to better approximate human evaluation behavior.**

The goal is to replace manual scoring with a consistent, reproducible system that compares learner responses with target sentences and assigns scores based on similarity and linguistic accuracy.

## Dataset

The dataset used in this project is provided as part of the AutoEIT evaluation test and is not included in this repository.

---

## 🧠 Approach

This implementation prioritizes reproducibility and interpretability, aligning with research requirements for consistent scoring
The scoring pipeline follows a structured approach:

### 1. Text Preprocessing
- Convert text to lowercase
- Remove punctuation and noise
- Normalize input for fair comparison

### 2. Sentence Comparison
- Compute similarity between:
  - Target sentence (Stimulus)
  - Learner response (Transcription)
- Used `SequenceMatcher` for baseline similarity scoring

### 3. Rule-Based Scoring
Scores are assigned based on similarity thresholds:

| Similarity | Score |
|----------|------|
| > 0.90   | 5    |
| > 0.75   | 4    |
| > 0.60   | 3    |
| > 0.40   | 2    |
| ≤ 0.40   | 1    |

---

## ⚙️ Tech Stack

- Python
- Pandas
- difflib (SequenceMatcher)
- Jupyter Notebook

---

## 📂 Project Structure


│
├── data/ # Input dataset
├── notebooks/ # Jupyter notebook implementation
├── output/ # Generated scoring results
├── README.md
└── requirements.txt


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

---

## 🚀 Future Improvements

- Word-level alignment scoring
- Semantic similarity using embeddings
- Handling disfluencies like [pause], [gibberish]
- More robust rubric-based scoring

---

## 📎 Note

This project was developed as part of the GSoC 2026 evaluation process under the HumanAI AutoEIT project.

