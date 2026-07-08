# Concept Card: TF-IDF (Term Frequency – Inverse Document Frequency)

**Contributor:** Sneha

## 1. Definition
TF-IDF is a statistical measure used to evaluate how important a word is to a specific document within a larger collection of documents (called a corpus). It combines two metrics — Term Frequency (TF) and Inverse Document Frequency (IDF) — into a single score.

## 2. Purpose
Not all words are equally meaningful. Common words like "the" or "is" appear everywhere and carry little useful information, while rarer, topic-specific words are far more informative. TF-IDF helps a model automatically identify which words actually matter for distinguishing one document from another.

## 3. Working Principle
- **Term Frequency (TF)**: How often a word appears in a document, relative to the total number of words in that document.
  `TF = (number of times word appears in document) / (total words in document)`
- **Inverse Document Frequency (IDF)**: Measures how rare or common a word is across all documents in the corpus. Words appearing in many documents get a lower score; rare words get a higher score.
  `IDF = log(total number of documents / number of documents containing the word)`
- **TF-IDF Score**: `TF-IDF = TF × IDF`
- A high TF-IDF score means the word appears frequently in one document but rarely elsewhere — making it a strong keyword for that document.

## 4. Example
Corpus of 3 sentences:
1. "The weather was nice yesterday"
2. "The weather is cold today"
3. "I enjoyed a nice walk today"

The word **"nice"** appears in documents 1 and 3, not 2 — giving it a moderate IDF score. The word **"the"** appears in documents 1 and 2 — very common, so it gets a low IDF score despite appearing often. This shows how TF-IDF naturally downweights generic words.

## 5. Advantages
- Simple to compute and interpret.
- Automatically reduces the weight of common, uninformative words without needing a manual stop-word list.
- Works well as input features for classic machine learning models (e.g., spam detection, document classification).

## 6. Limitations
- Ignores word order and context (treats "not good" the same as "good not").
- Cannot capture meaning or semantic similarity between words (e.g., "happy" and "joyful" are treated as completely unrelated).
- Performs poorly on very short documents or very large vocabularies without additional tuning.

## 7. Applications
- Search engines (ranking how relevant a document is to a search query)
- Keyword extraction from articles or documents
- Document classification and clustering
- Recommendation systems based on text similarity
- Identifying the most distinctive keywords in a batch of customer grievance complaints (e.g., surfacing "unauthorized transaction" or "delayed refund" as high-signal terms)
