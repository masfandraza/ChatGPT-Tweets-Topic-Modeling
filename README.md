# ChatGPT Twitter Topic Modeling with BERTopic

This project applies **BERTopic** to uncover key discussion themes in public tweets about ChatGPT. By combining transformer embeddings, UMAP dimensionality reduction, and HDBSCAN clustering, we extracted and visualized 10 distinct topics from 3,000 cleaned English tweets.

---

## Project Overview

- **Goal**: Discover what people are saying about ChatGPT on Twitter using topic modeling.
- **Model Used**: BERTopic (with Sentence-BERT + HDBSCAN + UMAP + c-TF-IDF)
- **Dataset**: 3,000 tweets mentioning ChatGPT (sampled from 50k+)
- **Best Coherence Score**: **0.7179**

---

## Pipeline Summary

1. **Data Collection**
   - Selected 3,000 English tweets related to ChatGPT.
   - Sampled using a fixed random seed for reproducibility.

2. **Preprocessing**
   - Removed mentions, links, emojis, hashtags.
   - Standardized text (lowercase, cleaned spacing).

3. **Embeddings**
   - Used `all-MiniLM-L6-v2` transformer to create 384-dimension sentence embeddings.

4. **Topic Modeling with BERTopic**
   - UMAP for dimensionality reduction.
   - HDBSCAN for clustering.
   - c-TF-IDF for keyword generation per topic.
   - Grid search for hyperparameter tuning (min_cluster_size, neighbors, components).

5. **Evaluation**
   - Coherence score: **0.7179**
   - Qualitative review of top terms and representative tweets
   - Visualizations: UMAP scatter plot, topic heatmap, word clouds, dendrogram

---

## Extracted Topics (Examples)

| Topic | Theme                                             |
|-------|---------------------------------------------------|
| 0     | General use of generative AI in education & tools |
| 1     | Humorous or surreal ChatGPT responses             |
| 2     | Coding help & programming tutorials               |
| 4     | Academic misuse (exams, cheating)                 |
| 5     | Pricing tiers, paid/free plan reactions           |
| 6     | AI in startups & investment                       |  

*...plus themes on media coverage, university use, and access issues.*

---


## Key Insights

- ChatGPT is heavily discussed in **education**, both positively and critically.
- Users actively use it for **coding help** and productivity.
- **Pricing and access issues** are frequent talking points.
- Social media content is a rich source for **public opinion mining** using BERTopic.

---

## Files Included

- `Chatgpt_Tweets_Dataset_.ipynb` – Full pipeline notebook
- `Dataset.zip` – Full Dataset
- `Project Documentation` – Project Documentation
- `README.md` – This file

---

## Requirements

```bash
pip install bertopic sentence-transformers umap-learn hdbscan
