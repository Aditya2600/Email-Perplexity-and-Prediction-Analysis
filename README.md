# **Email Perplexity and Prediction Analysis**

## **Overview**

This project analyzes a dataset of email messages to perform text preprocessing, build n-gram language models (bigram and trigram), and compute perplexity scores. It also includes functionalities for predicting the next word and completing sentences based on n-gram models.

---

## **Features**

- Text preprocessing (cleaning and tokenization of email data).
- Histogram visualization of text lengths.
- Word cloud generation for frequent word visualization.
- Bigram and trigram language model building.
- Sentence completion using n-gram models.
- Perplexity score computation for bigram and trigram models.
- Identification of frequent words in the corpus.

---

## **Prerequisites**

Ensure you have the following installed:

- Python 3.7+
- Required libraries:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `nltk`
  - `tqdm`
  - `email`
  - `wordcloud`

---

## **Installation**

1. Clone the repository:

   ```bash
   git clone <repository-link>
   cd <repository-directory>
   ```

2. Install required libraries:

   ```bash
   pip install -r requirements.txt
   ```

3. Download the required NLTK data:

   ```python
   import nltk
   nltk.download('punkt')
   ```

---

## **Dataset**

The dataset (`emails.csv`) must be available in the project directory. Ensure the file contains the following columns:

- **`message`**: The raw email text.

---

## **Usage**

### **1. Preprocessing**

The script preprocesses email content to:

- Remove special characters.
- Convert text to lowercase.
- Strip unwanted spaces.

```python
df['content'] = body(df['message'])
df['content'] = df['content'].str.replace("\n", " ").str.lower().str.strip()
```

### **2. Visualizations**

- **Histogram:** View the distribution of text lengths.
- **Word Cloud:** Visualize frequently occurring words in the dataset.

### **3. N-gram Model Creation**

- **Bigram Model:**
  ```python
  bigram_model = build_bigram_model(df)
  ```
- **Trigram Model:**
  ```python
  trigram_model = build_trigram_model(df)
  ```

### **4. Perplexity Computation**

Evaluate the perplexity of bigram and trigram models for given sentences:

```python
perplexity(2, "your input sentence here")
perplexity(3, "your input sentence here")
```

### **5. Next Word Prediction**

Predict the next word based on bigram or trigram models:

```python
get_next_word(bigram_model, "your input string here")
complete_sentence(trigram_model, "your input string here", count=5)
```

---

## **Output**

- **Perplexity Scores:**
  Bigram and trigram scores for input sentences are saved in a DataFrame:
  ```python
  df2 = pd.DataFrame(perplexity_dict)
  ```
- **Visualizations:**
  - Histogram for text lengths.
  - Word cloud for most frequent words.

---

## **Example**

```python
# Compute perplexity for a sample sentence
bigram_score = perplexity(2, "this is a test sentence")
trigram_score = perplexity(3, "this is a test sentence")
print(f"Bigram Score: {bigram_score}, Trigram Score: {trigram_score}")
```

---

## **Author**

Aditya, National Institute of Technology Raipur.

---

## **License**

This project is licensed under the MIT License.



