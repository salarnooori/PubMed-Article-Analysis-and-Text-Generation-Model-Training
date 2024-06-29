# Persian PubMed Article Analysis and Text Generation Model Training

## Overview
This Jupyter Notebook fetches, processes, and analyzes Persian abstracts from PubMed to create a training dataset. It includes steps for text preprocessing, TF-IDF vectorization, finding related articles, and training a text generation model (tiny-efficient5-t) with evaluation metrics like BLEU, ROUGE, and BERTScore.

## Notebook Structure
1. Fetch PubMed Articles: Uses articles_pubmed_fetch function to search and retrieve abstracts from PubMed.
2. Text Processing: Cleans abstracts by removing unnecessary information with text_process.
3. Read Questions and Answers: Loads Q&A pairs from a JSONL file.
4. Preprocess Text: Prepares text using text_preprocess for tasks like lowercasing, removing extra spaces, punctuation, and stopwords.
5. Vectorize Texts: Converts preprocessed texts to TF-IDF vectors.
6. Find Related Articles: Identifies related articles using docs_related_get function.
7. Generate Data: Combines questions, answers, and related articles into a dataframe.
8. Model Training and Evaluation:
   - Loads the tiny-efficient5-t model.
   - Prepares dataset using PromptAnswerDataset class.
   - Splits data into training and evaluation sets.
   - Loads evaluation metrics: BLEU, ROUGE, and BERTScore.
   - Defines a metrics_compute function to calculate evaluation metrics.
   - Configures and runs model training and evaluation using Trainer.

## Requirements
- pandas
- scikit-learn
- transformers
- torch
- nltk
- Bio.Entrez

Install the required libraries using:
```bash
pip install pandas scikit-learn transformers torch nltk biopython

