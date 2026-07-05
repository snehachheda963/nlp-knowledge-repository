# Workflow Diagram: Feature Engineering Pipeline

**Contributor:** [Partner's Name]

## Diagram

````mermaid
flowchart TD
    A[Cleaned Tokens from Preprocessing] --> B{Choose Representation Approach}
    B --> C[Bag of Words]
    B --> D[N-Grams]
    B --> E[TF-IDF]
    C --> F[Sparse Word Count Vectors]
    D --> G[Sparse Phrase-Level Vectors]
    E --> H[Weighted Importance Vectors]
    F --> I[Feature Vectors Ready for Model Input]
    G --> I
    H --> I
````

## Explanation of Each Stage

1. **Cleaned Tokens** — The final output of the Text Preprocessing Pipeline (tokenized, normalized, stop-words removed, stemmed/lemmatized). This is the direct input to feature engineering.
2. **Choose Representation Approach** — A design decision point: different tasks call for different feature engineering techniques.
3. **Bag of Words** — Represents each document as a count of how many times each word appears, ignoring word order.
4. **N-Grams** — Captures short sequences of adjacent words (e.g., bigrams, trigrams) to retain some local word order information that Bag of Words loses.
5. **TF-IDF** — Weighs each word by how important it is to a specific document relative to the whole corpus, rather than just raw counts.
6. **Feature Vectors** — The final numerical representation, in a format that can be directly fed into machine learning models.

## Why This Order Matters
Feature engineering always happens *after* preprocessing, since applying it to raw, unprocessed text would produce noisy and inconsistent features (e.g., counting "Bank" and "bank" as different words). The choice between Bag of Words, N-Grams, and TF-IDF depends on the specific NLP task — for example, TF-IDF is often preferred for search and document ranking, while N-Grams are useful when word order carries meaningful information (e.g., "not good" vs "good").
````
````

Once this is committed, **your partner's entire individual requirement is done too** — matching yours exactly (2 concept cards, 1 comparison, 1 workflow diagram). Only their **Reflection Note** (personal, in their own voice) is left, and that one really should come from them directly rather than being written on their behalf.

## Final repository status once this is committed
````
✅ Your individual set (5 files)
✅ Partner's concept cards + comparison + workflow (4 files)
⏳ Partner's reflection note (needs their own words)
✅ Sections D, E, Sustainability (shared, done)
⏳ Partner reviews/edits Sections D, E, Sustainability
⏳ Contribution Matrix — update with real names/roll numbers
⏳ AI & Plagiarism Report — partner's task
⏳ Enable GitHub Pages + get live link
````

Want help drafting a short reflection note template your partner can quickly personalize instead of writing from scratch?
