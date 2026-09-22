# 🚨 Natural Language Processing with Disaster Tweets

[![Kaggle Competition](https://img.shields.io/badge/Kaggle-NLP_Getting_Started-blue.svg)](https://www.kaggle.com/competitions/nlp-getting-started)
[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains my solution and source code for the Kaggle Getting Started competition: **[Natural Language Processing with Disaster Tweets](https://www.kaggle.com/competitions/nlp-getting-started)**.

## 📖 Project Overview
Twitter has become an important communication channel in times of emergency. The ubiquitousness of smartphones enables people to announce an emergency they’re observing in real-time. Because of this, more agencies are interested in programmatically monitoring Twitter. 

The goal of this project is to build a machine learning model that predicts which Tweets are about real disasters and which ones are not.

## 📊 Dataset
The dataset is provided by Kaggle and contains 10,000 tweets that have been manually classified.

*   **`train.csv`** - the training set (contains text, location, keyword, and target labels).
*   **`test.csv`** - the test set (contains text, location, and keyword; no target labels).
*   **`sample_submission.csv`** - a sample submission file in the correct format.

### Data Fields
*   `id` - a unique identifier for each tweet
*   `text` - the text of the tweet
*   `location` - the location the tweet was sent from (may be blank)
*   `keyword` - a particular keyword from the tweet (may be blank)
*   `target` - in `train.csv` only, this denotes whether a tweet is about a real disaster (`1`) or not (`0`)

## 🎯 Evaluation Metric
Submissions are evaluated using the **F1 score** between the predicted and expected answers.

$$ F1 = 2 \times \frac{precision \times recall}{precision + recall} $$

## 🛠️ Project Structure
```text
├── data/                   # Directory for storing train.csv and test.csv
├── notebooks/              # Jupyter notebooks for EDA and model prototyping
├── src/                    # Source code for data preprocessing and modeling
│   ├── preprocess.py       # Text cleaning and tokenization scripts
│   ├── model.py            # Model architecture definition
│   └── train.py            # Training script
├── requirements.txt        # Required Python packages
├── README.md               # Project documentation
└── submission.csv          # Final predictions for Kaggle
```

## ⚙️ Installation & Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/<YOUR-USERNAME>/<YOUR-REPO-NAME>.git
   cd <YOUR-REPO-NAME>
   ```
2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Download the dataset from [Kaggle](https://www.kaggle.com/competitions/nlp-getting-started/data) and place the `.csv` files into the `data/` directory.

## 🧠 Modeling Approach
*Briefly describe your approach here. For example:*
*   **Data Preprocessing:** Lowercasing, removing URLs, punctuation, and stopwords. Handled missing values in the `keyword` and `location` columns.
*   **Feature Engineering:** Used TF-IDF / Word Embeddings (GloVe) / Contextual Embeddings.
*   **Model Selection:** 
    *   *Baseline:* Logistic Regression with TF-IDF.
    *   *Deep Learning:* LSTM / GRU / BERT (Hugging Face Transformers).
*   **Hyperparameter Tuning:** Used Optuna / GridSearch to optimize learning rate and batch size.

## 🚀 Results
| Model | Validation F1-Score | Kaggle Public Leaderboard F1 |
|-------|---------------------|------------------------------|
| Baseline (Logistic Regression) | 0.XX | 0.XX |
| **Fine-tuned BERT (Best)** | **0.XX** | **0.XX** |

## 🤝 Acknowledgments
*   Data provided by [Kaggle](https://kaggle.com) and [Figure Eight](https://appen.com/).
*   Pre-trained models provided by [Hugging Face](https://huggingface.co/).