# Concept Card: TF-IDF (Term Frequency – Inverse Document Frequency)

**Contributor:** Sneha

## 1. Definition
TF-IDF is a statistical measure used to evaluate how important a word is to a specific document within a larger collection of documents (called a corpus). It combines two metrics — Term Frequency (TF) and Inverse Document Frequency (IDF) — into a single score.

## 2. Purpose
Not all words are equally meaningful. Common words like "the" or "is" appear everywhere and carry little useful information, while rarer, topic-specific words are far more informative. In a batch of customer complaints, TF-IDF helps a model automatically identify which words actually matter for distinguishing one complaint from another — instead of getting distracted by words every complaint shares.

## 3. Working Principle
- **Term Frequency (TF)**: How often a word appears in a document, relative to the total number of words in that document.
  `TF = (number of times word appears in document) / (total words in document)`
- **Inverse Document Frequency (IDF)**: Measures how rare or common a word is across all documents in the corpus. Words appearing in many documents get a lower score; rare words get a higher score.
  `IDF = log(total number of documents / number of documents containing the word)`
- **TF-IDF Score**: `TF-IDF = TF × IDF`
- A high TF-IDF score means the word appears frequently in one document but rarely elsewhere — making it a strong keyword for that document.

## 4. Example
Corpus of 3 customer grievance complaints:
1. "The refund was delayed yesterday"
2. "The account is frozen today"
3. "The customer complained about a delayed refund today"

The word **"refund"** appears in complaints 1 and 3, not 2 — giving it a moderate IDF score, since it's specific to refund-related grievances but not universal. The word **"the"** appears in all three complaints — very common, so it gets a low IDF score despite appearing often. This shows how TF-IDF naturally downweights generic words and surfaces the terms (like "refund" or "frozen") that actually tell a complaint apart from the rest of the batch.

## 5. Advantages
- Simple to compute and interpret.
- Automatically reduces the weight of common, uninformative words without needing a manual stop-word list.
- Works well as input features for classic machine learning models (e.g., routing a complaint to "fraud," "refund," or "account access" categories).

## 6. Limitations
- Ignores word order and context (treats "not resolved" the same as "resolved not").
- Cannot capture meaning or semantic similarity between words (e.g., "rejected" and "denied" are treated as completely unrelated, even in the same loan-complaint context).
- Performs poorly on very short documents or very large vocabularies without additional tuning — a real concern given how short many customer complaints are.

## 7. Applications
- Search engines (ranking how relevant a document is to a search query)
- Keyword extraction from articles or documents
- Document classification and clustering
- Recommendation systems based on text similarity
- Identifying the most distinctive keywords in a batch of customer grievance complaints (e.g., surfacing "unauthorized transaction" or "delayed refund" as high-signal terms)
