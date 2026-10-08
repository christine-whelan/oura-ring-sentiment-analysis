# Oura Ring 4 Review Sentiment Analysis

## Overview

This project analyzes customer reviews of the Oura Ring 4 using natural language processing and machine learning techniques.

The goal was to transform large volumes of customer feedback into actionable product insights that could help guide the development of a next-generation Oura Ring 5 concept.

The analysis uses 4,240 customer reviews collected from:

- Best Buy
- Amazon
- Target

The project applies text preprocessing, TF-IDF feature representation, sentiment classification, topic modeling, and aspect-based sentiment analysis.

---

## Business Goal

Customer reviews contain valuable information about product strengths, weaknesses, and areas for improvement.

However, manually reviewing thousands of comments is time-consuming and difficult to scale.

This project explores how NLP and machine learning can be used to:

- Classify customer sentiment
- Identify recurring themes in customer feedback
- Evaluate sentiment toward specific product features
- Prioritize improvement areas
- Translate review data into recommendations for a next-generation product

---

## Dataset

The dataset contains 4,240 Oura Ring 4 customer reviews collected from Best Buy, Amazon, and Target.

The review data includes both unstructured customer text and structured metadata such as:

- Star ratings
- Retail platform
- Verified purchase status
- Helpful vote counts
- Review dates

The preprocessed dataset used for modeling is included in:

`oura_ring4_all_reviews_preprocessed.csv`

---

## Project Workflow

The analysis follows this general pipeline:

```text
Raw Customer Reviews
        ↓
Text Preprocessing
        ↓
TF-IDF Feature Representation
        ↓
Sentiment Classification
        ↓
Topic Modeling
        ↓
Aspect-Based Sentiment Analysis
        ↓
Product Improvement Recommendations
```

---

## Text Preprocessing

Customer review text was cleaned and standardized before modeling.

The preprocessing process included:

- Converting text to lowercase
- Removing punctuation
- Removing numbers
- Removing extra whitespace
- Removing common stopwords
- Preserving important negation terms such as:
  - `not`
  - `no`
  - `never`
  - `should`
  - `need`

Three-star reviews were excluded from the sentiment classification dataset because they were treated as neutral.

The remaining reviews were labeled:

- 1–2 stars → Negative
- 4–5 stars → Positive

---

## Feature Representation

TF-IDF was used to convert the cleaned review text into numerical features.

The vectorizer included:

- Up to 5,000 features
- Unigrams
- Bigrams
- Frequency thresholds to reduce very rare or overly common terms

This allows machine learning models to identify which words and phrases are most useful for predicting sentiment.

---

## Sentiment Classification

Four machine learning models were trained and evaluated:

- Naive Bayes
- Logistic Regression
- Linear SVM
- Random Forest

The models were compared using:

- Accuracy
- Precision
- Recall
- F1 score

Linear SVM achieved the highest F1 score at approximately `0.96`.

Logistic Regression was selected as the final model because it achieved comparable performance while providing greater interpretability.

This made it easier to understand which words and phrases contributed to positive and negative sentiment predictions.

---

## Topic Modeling

Latent Dirichlet Allocation (LDA) was used to identify recurring themes within the customer reviews.

The analysis identified topics related to areas such as:

- Sleep and health tracking
- App experience and subscription
- Sizing and gifting
- Battery life
- Daily insights
- Competitor comparisons

---

## Aspect-Based Sentiment Analysis

Customer sentiment was also analyzed across specific product features.

The primary aspects evaluated were:

- Battery life
- Sleep tracking
- App experience
- Comfort
- Durability

Each aspect was evaluated using sentiment scores and mention volume.

These values were combined into a priority score to identify product areas that may need the most attention.

---

## Key Findings

The analysis showed that overall customer sentiment toward the Oura Ring 4 was largely positive.

However, sentiment varied significantly by product feature.

### Highest Improvement Priority

**Durability**

Durability received the lowest sentiment score and emerged as the most important area for improvement.

### Secondary Improvement Area

**Battery Life**

Battery performance received more mixed customer feedback and was identified as an area that should continue to be monitored and refined.

### Product Strengths

The strongest customer sentiment appeared around:

- Sleep tracking
- Comfort
- App experience

These features received high sentiment scores and strong mention volume.

---

## Model Evaluation

The project compared four sentiment classification models.

Approximate results included:

| Model | F1 Score |
|---|---:|
| Linear SVM | 0.96 |
| Logistic Regression | 0.95 |
| Naive Bayes | 0.95 |
| Random Forest | 0.96 |

Although Linear SVM produced the highest overall F1 score, Logistic Regression was selected because it offered strong performance and better interpretability.

---

## Oura Ring 5 Concept

The project findings were translated into an Oura Ring 5 product concept.

The product demo focuses on three main recommendations:

- Improve durability
- Refine battery performance
- Preserve strengths in sleep tracking, comfort, and app experience

The interactive concept is included in:

`oura_ring5_product_demo.html`

---

## Technologies Used

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- NLTK
- TF-IDF
- Logistic Regression
- Linear SVM
- Random Forest
- Naive Bayes
- LDA Topic Modeling
- Sentiment Analysis
- HTML / CSS

---

## Project Files

- `OuraRingPreprocessing.ipynb` — text preprocessing and dataset preparation
- `OuraRing_Sentiment Analysis.ipynb` — machine learning, topic modeling, and sentiment analysis
- `oura_ring4_all_reviews_preprocessed.csv` — cleaned review dataset used for analysis
- `oura_ring5_product_demo.html` — Oura Ring 5 product concept based on analysis findings
- `Oura Ring Project Report.docx` — complete written project report
- `README.md` — project documentation

---

## Limitations

- Customer reviews are heavily skewed toward positive ratings.
- Neutral three-star reviews were excluded from the sentiment classification model.
- Traditional machine learning models may struggle with sarcasm or complex contextual meaning.
- Aspect-based sentiment relies on predefined feature keywords.
- The dataset reflects reviews from a limited set of retail platforms.

For example, a sarcastic statement such as:

`Great, my ring stopped working after a week`

could potentially be interpreted incorrectly by a traditional sentiment classifier.

---

## Future Improvements

Potential improvements include:

- Adding transformer-based NLP models
- Including neutral sentiment as a third classification category
- Improving contextual sentiment detection
- Expanding the review dataset to additional platforms
- Building a dashboard for interactive sentiment exploration
- Automating product recommendation generation from aspect-level sentiment

---

## Project Outcome

This project demonstrates how NLP and machine learning can transform thousands of unstructured customer reviews into structured business insights.

The final analysis identified:

- Durability as the highest-priority improvement area
- Battery performance as an area for refinement
- Sleep tracking, comfort, and app experience as major product strengths

These findings were used to develop a recommendation framework for a next-generation Oura Ring 5 concept.
