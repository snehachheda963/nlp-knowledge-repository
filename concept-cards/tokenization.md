# Concept Card: Tokenization

**Contributor:** Sneha [Your Roll No: 12]

## 1. Definition
Tokenization is the process of breaking down a continuous stream of text into smaller units called *tokens* — which can be words, subwords, or even characters — so that a machine can process them individually.

## 2. Purpose
Raw text is just a sequence of characters to a computer. Before any NLP model can analyze meaning, grammar, or sentiment, the text must be split into discrete, countable units. Tokenization is the entry point of almost every NLP pipeline.

## 3. Working Principle
- The text is scanned and split based on defined rules or a trained model.
- **Word Tokenization**: Splits text at spaces/punctuation (e.g., using whitespace or regex rules).
- **Subword Tokenization**: Breaks rare/unknown words into smaller known pieces (used in models like BERT — e.g., Byte-Pair Encoding, WordPiece).
- **Sentence Tokenization**: Splits paragraphs into sentences, usually as a pre-step before word tokenization.
- Libraries like NLTK, spaCy, or Hugging Face's `tokenizers` implement these using rule-based or statistical/ML-based methods.

## 4. Example
**Input:** `"RBI mandates banks to resolve complaints within 30 days."`

**Word Tokens:**
`["RBI", "mandates", "banks", "to", "resolve", "complaints", "within", "30", "days", "."]`

## 5. Advantages
- Essential first step — without it, no further NLP processing is possible.
- Enables consistent, structured input for downstream tasks (vectorization, tagging, etc.).
- Subword tokenization handles out-of-vocabulary (OOV) words gracefully.

## 6. Limitations
- Ambiguous punctuation (e.g., "Mr." or "₹30,000") can cause incorrect splits.
- Language-specific challenges: languages like Hindi/Marathi don't always have clear word boundaries (no consistent whitespace rules for compound words), making tokenization harder than in English.
- Naive tokenizers may split contractions or domain-specific terms (like "TF-IDF") incorrectly.

## 7. Applications
- Search engines (breaking queries into searchable terms)
- Machine translation (splitting source text before translation)
- Chatbots (parsing user input before intent detection)
- Sentiment analysis (isolating words to analyze polarity)
- Banking/financial grievance systems (splitting complaint text before language detection and routing — relevant to bilingual grievance translators)
