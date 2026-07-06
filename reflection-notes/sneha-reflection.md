# Reflection Note

**Contributor:** Sneha 

## What I Learned
Working on this activity gave me a much clearer picture of how raw text actually becomes usable input for an NLP model. Before this, I understood these techniques as separate, disconnected topics — but building the concept cards and workflow diagram helped me see them as a connected pipeline, where each step depends on the one before it.

Researching stemming vs lemmatization in particular was useful, since I had always assumed they were roughly interchangeable. Comparing them side by side made it clear that the choice between the two actually changes downstream results, especially for languages with complex word structures like Hindi and Marathi.

## Challenges Faced
The hardest part was resisting the urge to just define terms and instead explain *why* each technique exists and *when* it should be used. Writing the TF-IDF concept card also pushed me to actually work through a small example by hand rather than just quoting the formula, which made the concept click much better than reading about it.

## How I'll Apply This
This activity connects directly to work I'm doing separately, where text preprocessing and feature engineering choices (like stemming vs lemmatization) will directly affect how well a bilingual system understands and processes real sentences. Having a clear mental model of this pipeline — from raw text to cleaned tokens to feature vectors — will make it much easier to debug and improve that kind of system going forward.

## Key Takeaway
NLP preprocessing isn't just a preliminary step to "get through" before the interesting modeling work begins — the quality of these early decisions (tokenization method, stopword handling, stemming vs lemmatization) has a direct impact on how well any downstream model performs.
