# Comparative Analysis: Word2Vec vs FastText

**Contributor:** Mahek

## Overview
Both Word2Vec and FastText are popular methods for generating word embeddings, but they differ in how they treat the internal structure of words, which has major implications for handling rare and unseen words.

| Aspect | Word2Vec | FastText |
|---|---|---|
| **Working Mechanism** | Learns a single dense vector for each whole word based on its surrounding context, using either the Skip-gram or CBOW (Continuous Bag of Words) architecture. | Extends Word2Vec by representing each word as a collection of character n-grams (subword units), then sums those n-gram vectors to form the final word vector. |
| **Computational Complexity** | Relatively efficient; training scales with vocabulary size and corpus size. | Higher — training involves generating and processing multiple character n-grams per word, increasing memory and computation needs. |
| **Strengths** | Fast to train, well-established, produces strong results for languages with simpler morphology (like English). | Handles out-of-vocabulary (OOV) and rare words far better, since it can construct a reasonable vector even for words never seen during training, using shared subword patterns. |
| **Weaknesses** | Cannot generate a vector for a word it has never seen before — treats unseen words as completely unknown. | Larger model size due to storing n-gram vectors; slightly slower to train and use compared to Word2Vec. |
| **Suitable Applications** | General-purpose NLP tasks in resource-rich, morphologically simpler languages (e.g., English sentiment analysis, topic modeling). | Morphologically rich languages with many word variations (e.g., Hindi, Marathi, Finnish, Turkish), and grievance/complaint text full of misspellings, abbreviations, or rare terms. |

## Example
For the banking term "chargeback":
- Word2Vec treats it as one single unit and needs to have seen this exact word during training to have a vector for it — if a complaint uses a rarer term like "chargeback" that barely appeared in training data, Word2Vec may have no usable vector at all.
- FastText breaks it into character n-grams (e.g., "char", "charge", "back", "ck") and can construct a reasonable vector even if "chargeback" itself was rare in training, since it recognizes shared sub-parts from related words like "charge" or "billback."

## Why this matters for Indian languages
Languages like Hindi and Marathi have rich morphology, where a single root word can take on many different forms depending on gender, tense, and case. This creates a large number of word variations that a whole-word model like Word2Vec would treat as entirely separate, unrelated words. FastText's subword approach handles this far more gracefully, which is why it is frequently used in Indic NLP resources such as the IndicFT embeddings — directly relevant to a bilingual banking grievance system processing English, Hindi, and Marathi complaints.

## Conclusion
Word2Vec is a solid choice for simpler, resource-rich languages where vocabulary is relatively stable. FastText is generally the safer choice for morphologically complex languages or noisy, real-world text like customer complaints, since its subword-based approach handles rare, misspelled, and unseen banking terms far more effectively.
