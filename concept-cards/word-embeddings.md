# Concept Card: Word Embeddings

**Contributor:** [Partner's Name]

## 1. Definition
Word embeddings are dense, low-dimensional numerical vector representations of words, where words with similar meanings are positioned closer together in vector space. Unlike simpler methods like one-hot encoding, embeddings capture semantic relationships between words.

## 2. Purpose
Machine learning models cannot work directly with text — they need numbers. Earlier representation methods (like one-hot encoding) treated every word as completely unrelated to every other word. Word embeddings solve this by encoding meaning: words used in similar contexts end up with similar vector representations.

## 3. Working Principle
- Each word is mapped to a fixed-length vector of real numbers (commonly 100–300 dimensions).
- These vectors are learned by training a model on large amounts of text, based on the idea that "a word is characterized by the company it keeps" (words appearing in similar contexts get similar vectors).
- Once trained, vector arithmetic captures relationships — for example, the vector for "king" minus "man" plus "woman" lands close to the vector for "queen."
- Popular embedding models include Word2Vec, GloVe, and FastText.

## 4. Example
In a well-trained embedding space:
- "happy" and "joyful" would have vectors close to each other (similar meaning).
- "happy" and "car" would have vectors far apart (unrelated meaning).

## 5. Advantages
- Captures semantic similarity between words, unlike one-hot encoding.
- Dense, low-dimensional vectors are computationally efficient compared to large sparse vectors.
- Pre-trained embeddings can be reused across different NLP tasks without retraining from scratch.

## 6. Limitations
- A single word gets only one fixed vector, so it cannot capture different meanings in different contexts (e.g., "bank" as a financial institution vs. a riverbank).
- Requires large amounts of training text to produce good-quality embeddings.
- Struggles with rare words or words not seen during training (out-of-vocabulary problem).

## 7. Applications
- Sentiment analysis (grouping emotionally similar words)
- Recommendation systems (finding similar items/content based on text descriptions)
- Search engines (matching queries to documents based on meaning, not just exact keywords)
- Machine translation (mapping words with similar meaning across languages)
