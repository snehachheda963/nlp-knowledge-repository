# Comparative Analysis: One-Hot Encoding vs Word Embeddings

**Contributors:** Sneha & Mahek

## Overview
Both are ways of turning words into numbers so a model can process them, but they sit at opposite ends of the representation spectrum — one is simple and sparse, the other is learned and dense.

| Aspect | One-Hot Encoding | Word Embeddings |
|---|---|---|
| **Working Mechanism** | Assigns each word a unique index in the vocabulary; represents it as a vector of 0s with a single 1 at that index. | Maps each word to a dense, low-dimensional vector (typically 100–300 dimensions) learned from large amounts of text based on context. |
| **Computational Complexity** | Very low — no training required, just a direct lookup table. But vectors grow linearly with vocabulary size. | Higher — requires training on large corpora (or using pre-trained models like Word2Vec, GloVe, FastText), though inference afterward is fast. |
| **Strengths** | Extremely simple to implement and understand; works fine for small, fixed vocabularies. | Captures semantic similarity between words; dense vectors are computationally efficient to store and use in models. |
| **Weaknesses** | Produces huge, sparse vectors for large vocabularies (50,000 words = 50,000 dimensions); cannot capture any relationship between words. | Requires substantial training data and compute to produce good embeddings; a single word gets only one fixed vector regardless of context. |
| **Suitable Applications** | Small-scale categorical/text classification tasks; teaching examples before introducing embeddings. | Sentiment analysis, search, recommendation systems, machine translation — anything where word meaning and similarity matter. |

## Example
Vocabulary: `["bank", "loan", "approved", "rejected"]`

- **One-Hot:** "bank" → `[1, 0, 0, 0]`, "loan" → `[0, 1, 0, 0]` — completely unrelated vectors, equal distance between any two words.
- **Word Embeddings:** "bank" and "loan" would end up with vectors that are relatively close together in vector space, since they frequently appear in similar banking/financial contexts — while "bank" and, say, "weather" would be far apart.

## Why this matters for banking and financial NLP
A grievance-routing system that only sees one-hot vectors would treat "loan rejected" and "loan denied" as two completely unrelated inputs, even though they mean the same thing to a customer. Word embeddings let a model recognize that "rejected" and "denied" are semantically close, which matters a lot when customer complaints are phrased in dozens of different ways.

## Conclusion
One-Hot Encoding is a reasonable starting point for small, simple tasks, but it doesn't scale well and captures no meaning. Word Embeddings solve both problems at the cost of needing more data and compute — which is why almost every modern NLP system uses some form of embedding rather than one-hot vectors as its base representation.
