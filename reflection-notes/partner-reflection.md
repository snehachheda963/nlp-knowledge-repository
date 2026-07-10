# Reflection Note

**Contributor:** Mahek

## What I Learned
Working on Word Embeddings and the One-Hot Encoding card back-to-back made it much clearer why representation choice actually matters in NLP — I hadn't realized how directly the "no notion of similarity" limitation of one-hot encoding is what embeddings were built to solve. Digging into Word2Vec vs FastText also showed me that even within "embeddings," the choice of algorithm changes how well a model handles messy, real-world text like misspellings or unseen words.

## Challenges Faced
The hardest part was explaining vector similarity in plain language without leaning on heavy math, since concepts like cosine distance are easy to compute but harder to describe intuitively. Finding examples that weren't just generic textbook pairs like "king/queen" also took a few tries — I wanted something that would actually connect to the banking/financial grievance angle the rest of the repo leans in.

## How I'll Apply This
This connects directly to the classification work we're doing for the grievance text project, since choosing the right representation (embeddings over one-hot) will likely be the difference between a model that generalizes across phrasing and one that doesn't.

## Key Takeaway
The biggest realization was that representation isn't just a preprocessing step — it's a design decision that quietly determines how well everything downstream (classification, similarity, translation) will actually perform.
