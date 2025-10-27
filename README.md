# 🍲 Text Classification & Sentiment Analysis: A Recipe Reviews Study

## 🧠 Project Overview
In the modern era of e-commerce, online reviews have become powerful signals of customer experience and satisfaction.  
This project explores **text classification** and **sentiment analysis** using real-world recipe review data from the **UCI Machine Learning Repository**.  

The goal is to:
- Classify customer feedback based on their **survey ratings (1–5 stars)**
- Use Natural Language Preprocessing (NLP) techniques such as tokenization, lemmatization, stop-word removal to clean and prepare the text data.
- Generate **insights** that can help a restaurant or business improve engagement, efficiency, and overall customer satisfaction  

---

## 📂 Dataset

**Name:** Recipe Reviews and User Feedback  
**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/911/recipe+reviews+and+user+feedback+dataset)  
**Size:** 18,182 rows × 15 columns  

| Feature | Description |
|----------|-------------|
| `recipe_name` | Name of the recipe |
| `stars` | Customer rating (1–5) |
| `text` | Customer feedback (renamed to `verbatim`) |
| `thumbs_up`, `thumbs_down` | Number of upvotes/downvotes |
| `user_id`, `recipe_number` | Identifiers for user and recipe |

**Sentiment Categories:**  
- ⭐ **Positive:** 4–5 stars  
- 😐 **Neutral:** 3 stars  
- 💔 **Negative:** 1–2 stars  

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Removed missing values (`verbatim` had 2 nulls)  
- Tokenized, lemmatized, and removed stop words  
- Converted text to lowercase and rejoined into sentences  
- Vectorized text into numerical form for machine learning  
- Addressed **class imbalance** using **SMOTE (Synthetic Minority Oversampling Technique)**  

### 2. Text Classification
- **Algorithm:** Multinomial Naive Bayes (MultinomialNB)  
- **Goal:** Predict the customer’s survey rating based on their text review  
- **Rationale:** Efficient for large, sparse datasets; great for word-frequency-based predictions  

### 3. Sentiment Analysis
- **Algorithm:** VADER (Valence Aware Dictionary for Sentiment Reasoning)  
- **Goal:** Classify each review as positive, neutral, or negative  
- **Output Columns:** `neg`, `neu`, `pos`, and `compound` sentiment scores  

---

## 🧰 Tools & Libraries

| Category | Libraries |
|-----------|------------|
| Data Manipulation | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `wordcloud` |
| Machine Learning | `scikit-learn` (SMOTE, MultinomialNB) |
| NLP & Sentiment | `nltk`, `VADER` |
| Environment | Google Colab / Jupyter Notebook |

---

## 📊 Results

| Task | Model | Accuracy | Key Observations |
|------|--------|-----------|------------------|
| Text Classification | MultinomialNB | **61%** | Correctly classifies majority 5-star reviews; struggles slightly with lower ratings |
| Sentiment Analysis | VADER | – | Majority of reviews were neutral to positive |

**Insights:**
- 🍍 *Pineapple Pudding Cake* had the **most negative** reviews → potential issues with preparation or taste.  
- 🥧 *Winning Apple Crisp* had the **highest positive** reviews → customers loved it!  
- ⏰ Frequent negative keywords like “time” suggested **long preparation times** lowered satisfaction.  
- 😊 Positive keywords included “good”, “delicious”, “recipe”, “satisfied”.  

---

## 💬 Discussion
The analysis demonstrates how NLP can turn unstructured customer feedback into **actionable business insights**.  
Despite the dataset’s imbalance (more 5-star reviews), both models performed reliably:  
- **MultinomialNB** effectively categorized reviews by rating.  
- **VADER** provided meaningful sentiment polarity and highlighted patterns in word usage.

Businesses can leverage such insights to:
- Identify underperforming products
- Improve preparation time and quality
- Focus marketing on high-performing recipes  

---

## 🚀 Future Improvements
- Implement **BERT or RoBERTa** models for more nuanced sentiment detection  
- Expand dataset to include reviews across multiple restaurants  
- Deploy as an interactive **Streamlit dashboard** for real-time feedback visualization  

---

## 📈 Sample Visuals
You can include:
- 📊 Distribution of star ratings  
- ☁️ Word clouds for positive and negative reviews  
- 📉 Histograms of sentiment polarity (VADER compound scores)  

_Add screenshots or generated plots here once your notebook is ready._

---

## 🧩 Repository Structure
