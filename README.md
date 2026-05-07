# CENG 467 — Natural Language Understanding and Generation
## Take-Home Midterm

This repository contains five independent NLP experiments covering core areas of natural language processing. Each question has a dedicated notebook under `notebooks/` and output CSV files under `results/`.

---

## Project Structure

```
├── notebooks/
│   ├── q1_representation_learning.ipynb
│   ├── q2_Named_Entity_Recognition.ipynb
│   ├── q3_Text_Summarization.ipynb
│   ├── q4_Machine_Translation.ipynb
│   └── q5_Language_Modeling.ipynb
├── results/
│   ├── q1/   # Validation/test metrics, misclassified examples
│   ├── q2/   # NER evaluation results, error CSVs
│   ├── q3/   # Summarization metrics, generated summaries
│   ├── q4/   # Translation metrics, generated translations
│   └── q5/   # Perplexity results, generated text samples
└── report/
    └── CENG_467_Natural_Language_Understanding_and_Generation_Take_Home_Midterm_Report.pdf
```

---

## Experiments

| # | Task | Dataset | Models |
|---|---|---|---|
| Q1 | Sentiment Classification | IMDb | TF-IDF + LR, BiLSTM, DistilBERT |
| Q2 | Named Entity Recognition | CoNLL-2003 | CRF, DistilBERT (cased) |
| Q3 | Text Summarization | CNN/DailyMail | TextRank, BART (`facebook/bart-large-cnn`) |
| Q4 | Machine Translation (EN→DE) | Multi30k | Seq2Seq + Attention, MarianMT (`Helsinki-NLP/opus-mt-en-de`) |
| Q5 | Language Modeling | WikiText-2 | LSTM (from scratch), GPT-2 |

---

## Requirements

All notebooks install their own dependencies via `!pip install` in the first cell. The core requirements are:

```
datasets
transformers
accelerate
evaluate
torch
scikit-learn
seqeval
sklearn-crfsuite
rouge_score
sacrebleu
bert-score
nltk
networkx
sentencepiece
```

Python 3.9+ and PyTorch 2.0+ are recommended. Experiments run on CPU but benefit significantly from a GPU (CUDA).

---

## Reproducibility

All experiments use a fixed random seed of **42** applied to Python, NumPy, and PyTorch. Dataset subsets are created with the same seed. Running each notebook top-to-bottom in a clean environment reproduces all reported results.
