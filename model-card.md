Model Card — BERT Sentiment Classification Model

1. Model Overview

Model name: BERT Sentiment Classifier (IMDB)  
Base model: BERT (Bidirectional Encoder Representations from Transformers), transformer encoder  
Task: Text classification (sentiment analysis)  
Labels: Positive, Negative  

This model is a fine‑tuned version of BERT for binary sentiment classification on movie reviews.

2. Intended Use

Primary use case:  
- Classify movie reviews as positive or negative sentiment.

Intended users:
- ML engineers
- Researchers
- AI governance and risk professionals

Appropriate use:  
- Benchmarking sentiment models
- Demonstrations of AI governance
- Educational and research purposes

Out‑of‑scope use:  
- Employment decisions
- Credit scoring
- Medical diagnosis
- Legal or compliance decision‑making


3. Training Data

Dataset: IMDB Movie Review Dataset (50,000 labeled reviews)  
Split:**
- 25,000 training  
- 25,000 test  

Data characteristics:  
- User‑generated movie reviews  
- Binary labels: positive / negative
- English language only


Known limitations:  
- Cultural bias in sentiment expression  
- Presence of offensive or toxic language  
- Not representative of all domains or languages


4. Model Architecture

- Base: BERT‑Base (12 layers, 768 hidden size, 12 attention heads)  
- Tokenization: WordPiece tokenizer  
- Classification head:
  - Dense layer on top of [CLS] embedding
  - Softmax over 2 classes (positive, negative)


5. Performance
Example metrics only:

- Accuracy (test set): ~0.93  
- F1 score (macro): ~0.93  
- Balanced performance across classes (due to balanced dataset)

Important: 
Performance is measured only on IMDB movie reviews and does not generalize to other domains (e.g., product reviews, social media, legal text).


6. Ethical & Governance Considerations

6.1 Fairness

- Sentiment may vary across cultures and language styles.
- Offensive content in training data may influence model behavior.
- Not evaluated for demographic fairness (no demographic labels in dataset).

Mitigations:

- Document dataset limitations.
- Avoid deployment in high‑stakes domains.
- Use for low‑risk, educational, or research purposes only.

6.2 Transparency

- Model decisions are not inherently interpretable.
- Explainability tools (e.g., SHAP, attention visualization) can be used to inspect token importance.

6.3 Privacy

- IMDB dataset does not contain personal identifiable information (PII).
- No direct privacy risk from training data.

---

7. Risks & Limitations

Key risks:

- Misinterpretation of sentiment in edge cases (sarcasm, irony).
- Cultural bias in sentiment expression.
- Over‑reliance on model outputs in inappropriate domains.

Limitations:

- English‑only.
- Movie‑review domain only.
- Binary sentiment only (no neutral or mixed labels).


8. Recommended Use Guidelines

- Use in low‑risk contexts (education, demos, research).
- Do not use for:
  - Hiring
  - Lending
  - Healthcare
  - Legal decisions

- Combine with:
  - Human review
  - Clear documentation
  - Governance controls


9. Contact & Maintenance

Maintainer:  
- This model card is part of the `bert-governance` repository for AI Governance portfolio work.

Updates:  
- Performance and governance documentation should be updated if:
  - The dataset changes
  - The model is fine‑tuned on new data
  - The use case shifts to a higher‑risk domain
