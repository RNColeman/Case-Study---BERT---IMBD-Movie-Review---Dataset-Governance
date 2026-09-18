 Dataset Overview
The IMDB dataset contains 50,000 movie reviews labeled as either
"positive" or "negative". It is widely used for benchmarking
sentiment classification models, including BERT.

Source: Hugging Face (stanfordnlp/imdb) — public, open dataset.

Data Structure
- 25,000 training reviews
- 25,000 test reviews
- Balanced classes (50% positive, 50% negative)
- Reviews are plain text, typically 200–500 words

Why this Dataset is Used
- Public and open
- No personal identifiable information (PII)
- Clean binary classification task
- Ideal for demonstrating BERT fine-tuning

Governance Considerations 
Fairness
Sentiment datasets may contain:
- Biased language
- Toxic or offensive content
- Cultural bias in movie reviews

Privacy
Dataset contains no personal data.

Transparnecy
Model decisions must be explainable using:
- SHAP values
- Attention visualization
- Token importance scores

Risk Level 
Low-risk dataset under EU AI Act because:
- No employment, credit, or biometric data
- No impact on rights or access to services

How BERT uses Dataset
1. Tokenizes each review using WordPiece
   - WordPiece is a subword tokenization algorithim that builds a fixed size vocabulary by merging symbol pairs based      on a likelihood score, widely used in transformer models like BERT.
     In short: WordPiece is not a language model itself but a pre‑processing step that converts raw text into a            compact sequence of subword tokens, enabling efficient and robust input for modern AI models
2. Generates contextual embeddings
   - Generating a contextual embedding means creating a dynamic vector representation for a word or token that             changes depending on the surrounding text, so the model can capture the word’s meaning in that specific context       rather than using a single fixed meaning
3. Uses the [CLS] token embedding for classification
   - The [CLS] token is a special, non‑word token introduced in transformer‑based models like BERT to represent the        entire input sequence in a single vector for classification tasks
   - Purpose: Stands for classification. It is placed at the very beginning of every input sequence in BERT and            similar models
   - It does not correspond to any real word; instead, it acts as a sequence‑level summary token
   - Embedding: During training, the [CLS] token is processed through all transformer layers just like other tokens,       but its final hidden state is designed to aggregate information from all tokens in the sequence
6. Outputs probability of positive vs negative sentiment

Example Input
"An amazing film with stunning performances."

Example Output
Positive (0.93 probability)
