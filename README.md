=============================================
  README - Sentiment Classifier Behind Words
  Deep Learning Mini Project | 3-Week Sprint
=============================================

PROJECT TITLE   : Sentiment Classifier Behind Words
TEAM MEMBERS    : [Gazy Abbas] | [2025RCP9521]
                  [Rahul Yadav] | [2025RCP9546]
                 
COURSE          : Deep Learning
SUBMISSION DATE : [19-04-2026]

---------------------------------------------------------
  PROJECT OVERVIEW
---------------------------------------------------------

This project builds a binary sentiment classifier (Positive / Negative)
on the IMDB Movie Reviews dataset using DistilBERT - a lightweight
Transformer model. The key idea is to go "behind words" and understand
the contextual sentiment using attention-based deep learning, rather than
simple keyword matching.

Dataset   : IMDB (50,000 reviews) via HuggingFace Datasets
Model     : distilbert-base-uncased (fine-tuned)
Task      : Binary Text Classification
Framework : PyTorch + HuggingFace Transformers

--------------------------------------------------------------------------
  RESULTS SUMMARY
--------------------------------------------------------------------------

  Metric        | Score
  --------------|--------
  Accuracy      | 91.8%
  F1-Score      | 0.918
  Precision     | 0.923
  Recall        | 0.913

--------------------------------------------------------------------------
  REPOSITORY STRUCTURE
--------------------------------------------------------------------------

sentiment-classifier-dl/
│
├── sentiment_classifier.ipynb   ← Main Colab notebook (all code here)
├── README.txt                   ← This file
├── report.txt                   ← Full project report (6-8 pages)
│
└── LLM_Prompts/                 ← All AI tool prompts used
    ├── prompt_model_architecture.txt
    ├── prompt_preprocessing_tokenization.txt
    └── prompt_evaluation_and_report.txt

--------------------------------------------------------------------------
  HOW TO RUN (Google Colab - Free Tier)
--------------------------------------------------------------------------

STEP 1 → Open Google Colab
         Go to: https://colab.research.google.com

STEP 2 → Upload the notebook
         File → Upload Notebook → select sentiment_classifier.ipynb
         OR open directly from GitHub via File → Open Notebook → GitHub tab

STEP 3 → Enable GPU
         Runtime → Change Runtime Type → Hardware Accelerator → T4 GPU

STEP 4 → Run all cells in order (Runtime → Run All)
         Total estimated time: ~45-60 minutes on free T4 GPU

STEP 5 → Check outputs
         - Training logs printed after each epoch
         - Confusion matrix plot displayed inline
         - Classification report printed in output
         - Test your own sentences in the last cell

--------------------------------------------------------------------------
  DEPENDENCIES (auto-installed in notebook Cell 1)
--------------------------------------------------------------------------

  transformers==4.x
  datasets==2.x
  scikit-learn
  matplotlib
  seaborn
  torch (pre-installed in Colab)

No manual installation needed - Cell 1 handles everything with:
  !pip install transformers datasets scikit-learn matplotlib seaborn

--------------------------------------------------------------------------
  KEY DESIGN DECISIONS
--------------------------------------------------------------------------

1. WHY DistilBERT?
   - 40% smaller than BERT, 60% faster, retains 97% performance
   - Fits within free Colab 12GB GPU RAM
   - Pre-trained knowledge transfers well to sentiment tasks

2. WHY max_length=256?
   - 95% of IMDB reviews are under 256 tokens
   - Halves memory vs max_length=512
   - Enables larger batch size (16) for stable training

3. WHY 5000 training samples?
   - Prevents Colab free tier session timeout (~90 min limit)
   - Still achieves >91% accuracy due to DistilBERT pre-training
   - Full 25K samples recommended with Colab Pro

--------------------------------------------------------------------------
  LLM TOOLS USED
--------------------------------------------------------------------------

  Tool         | Purpose
  -------------|--------------------------------------------------
  Claude        | Architecture selection, evaluation code, report
  ChatGPT (4o) | Preprocessing pipeline, tokenization strategy
  GitHub Copilot| Inline code suggestions during notebook writing

  All prompts saved in: LLM_Prompts/ folder

--------------------------------------------------------------------------
  REFERENCES
--------------------------------------------------------------------------

[1] Sanh et al. (2019) - DistilBERT, a distilled version of BERT
    https://arxiv.org/abs/1910.01108

[2] HuggingFace IMDB Dataset
    https://huggingface.co/datasets/imdb

[3] HuggingFace Transformers Documentation
    https://huggingface.co/docs/transformers

[4] Maas et al. (2011) - Learning Word Vectors for Sentiment Analysis
    ACL 2011 (original IMDB dataset paper)

==========================================================================
