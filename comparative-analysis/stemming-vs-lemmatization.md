# Comparative Analysis: Stemming vs Lemmatization

**Contributor:** Sneha 

## Overview
Both stemming and lemmatization reduce words to a base form, but they differ significantly in method, accuracy, and computational cost.

| Aspect | Stemming | Lemmatization |
|---|---|---|
| **Working Mechanism** | Chops off word endings using fixed rules (e.g., removing "-ing", "-ed", "-s"), without understanding grammar or meaning. | Uses a dictionary and grammatical rules (part of speech) to return the actual base/root word, called a *lemma*. |
| **Computational Complexity** | Low — simple rule-based suffix stripping. Very fast. | Higher — requires a vocabulary lookup and often POS tagging first, making it slower. |
| **Output Quality** | Can produce non-words or incorrect roots (e.g., "studies" → "studi"). | Always produces a valid dictionary word (e.g., "studies" → "study"). |
| **Strengths** | Fast, lightweight, good for large-scale text processing where speed matters more than precision. | More accurate, context-aware, better for tasks needing correct meaning. |
| **Weaknesses** | Can over-stem or under-stem, leading to loss of meaning or merging unrelated words. | Slower, requires more resources (dictionaries, POS taggers), more complex to set up. |
| **Suitable Applications** | Search engines, information retrieval, large-scale document indexing where minor errors are acceptable. | Chatbots, machine translation, sentiment analysis — tasks where correct word meaning directly affects output quality. |

## Example
**Word:** "studies"
- Stemming output: `studi` (not a real word)
- Lemmatization output: `study` (correct dictionary form)

**Word:** "better"
- Stemming output: `better` (unchanged, since stemmers work on suffixes only)
- Lemmatization output: `good` (correctly identifies "better" as the comparative form of "good")

## Why this matters for morphologically rich languages
Languages like Hindi and Marathi have far more complex word inflections than English (multiple suffixes can attach to a single root depending on gender, tense, and case). This makes naive suffix-stripping stemmers particularly unreliable for these languages, since a single wrong rule can distort many different words. Lemmatization, which relies on structured linguistic knowledge, is generally the safer choice when working with such languages — though it also requires much richer dictionaries than are readily available for many Indian languages.

## Conclusion
Stemming is preferred when speed matters more than precision (e.g., indexing millions of documents). Lemmatization is preferred when the meaning of the word must be preserved accurately, especially in tasks like translation or conversational AI.
