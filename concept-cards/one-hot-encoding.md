# Concept Card: One-Hot Encoding

**Contributor:** [Partner's Name]

## 1. Definition
One-Hot Encoding is a technique for representing words as binary vectors, where each word in a vocabulary is represented by a vector of 0s and a single 1, marking that word's unique position in the vocabulary.

## 2. Purpose
Before more advanced representation methods existed, NLP systems still needed a way to convert words into numbers computers could process. One-Hot Encoding provides the simplest possible numerical representation, treating each word as a distinct, independent category.

## 3. Working Principle
- First, a fixed vocabulary of all unique words in the dataset is built.
- Each word is assigned a unique index/position in this vocabulary.
- A word is represented as a vector the same length as the vocabulary, with a `1` at its assigned index and `0`s everywhere else.
- Every word's vector is equally distant from every other word's vector — there is no notion of similarity or relationship between words.

## 4. Example
Vocabulary: `["bank", "loan", "approved", "rejected"]`

- "bank" → `[1, 0, 0, 0]`
- "loan" → `[0, 1, 0, 0]`
- "approved" → `[0, 0, 1, 0]`
- "rejected" → `[0, 0, 0, 1]`

## 5. Advantages
- Extremely simple to understand and implement.
- No training required — it's a direct, rule-based mapping.
- Works well for small vocabularies or categorical data.

## 6. Limitations
- Produces very large, sparse vectors as vocabulary size grows (a vocabulary of 50,000 words means every vector has 50,000 dimensions, mostly zeros).
- Cannot capture any similarity or relationship between words — "happy" and "joyful" are just as unrelated as "happy" and "car" in this representation.
- Computationally inefficient and memory-intensive for large text datasets compared to dense embeddings.

## 7. Applications
- Basic text classification tasks with small, fixed vocabularies.
- Categorical feature encoding in traditional machine learning pipelines (not limited to text).
- Often used as a stepping stone/teaching example before introducing word embeddings.
