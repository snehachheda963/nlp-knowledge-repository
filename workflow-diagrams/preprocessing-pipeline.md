# Workflow Diagram: Complete Text Preprocessing Pipeline

**Contributor:** Sneha [Your Roll No: 25]

## Diagram

````mermaid
flowchart TD
    A[Raw Text Input] --> B[Sentence Segmentation]
    B --> C[Tokenization]
    C --> D[Case Normalization]
    D --> E[Stop-word Removal]
    E --> F{Choose Method}
    F --> G[Stemming]
    F --> H[Lemmatization]
    G --> I[Noise Removal]
    H --> I[Noise Removal]
    I --> J[Cleaned Tokens Ready for Feature Engineering]
````

## Explanation of Each Stage

1. **Raw Text Input** — The original, unprocessed text (e.g., a sentence, paragraph, or document).
2. **Sentence Segmentation** — Splits a paragraph into individual sentences.
3. **Tokenization** — Breaks each sentence into individual words/tokens.
4. **Case Normalization** — Converts all text to lowercase so "Bank" and "bank" are treated identically.
5. **Stop-word Removal** — Removes common, low-information words (e.g., "the", "is", "and").
6. **Stemming / Lemmatization** — Reduces words to their root form (a project typically picks one method, not both, depending on the accuracy vs. speed tradeoff).
7. **Noise Removal** — Strips out punctuation, special characters, numbers, HTML tags, or other non-meaningful symbols.
8. **Cleaned Tokens** — The final, clean list of tokens ready to be passed into feature engineering steps like Bag of Words or TF-IDF.

## Why This Order Matters
Each step depends on the output of the previous one. For example, stop-word removal must happen *after* tokenization (you can't remove "the" from raw, unsplit text), and case normalization should ideally happen *before* stop-word removal, since stop-word lists are usually lowercase and won't match "The" otherwise.
````
````

**Important note:** When you paste this, make sure you copy everything including the outer ` ```markdown ` and ` ``` ` at the very start/end are NOT included — only copy what's between them (which itself contains a mermaid code block — that inner one you DO keep, since that's what tells GitHub to draw the diagram).

Once committed, GitHub will automatically render this as an actual flowchart with boxes and arrows when you view the file. Let me know once it's done — then it's just the **Reflection Note** left for your individual part.
