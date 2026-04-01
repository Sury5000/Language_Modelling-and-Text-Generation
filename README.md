# Character-Level Language Modeling and Text Generation using GRU

---

# Objective

* Learn how raw text is converted into numerical format
* Build a character-level sequence model
* Train a GRU network for next-character prediction
* Generate new text using probabilistic sampling

---

# Dataset

* Shakespeare text corpus
* Downloaded programmatically
* Converted to lowercase
* Unique characters extracted as vocabulary

---

# Text Encoding

* Created mappings:

  * Character → Index
  * Index → Character
* Encoded text into integer sequences
* Decoded predictions back to readable text

---

# Dataset Creation

* Implemented custom PyTorch Dataset
* Used sliding window approach

Input → sequence of characters
Target → same sequence shifted by one step

---

# Data Loading

* Used DataLoader for batching
* Training, validation, and test splits created
* Shuffling applied during training

---

# Embedding Layer

* Used nn.Embedding
* Converts character IDs into dense vectors
* Same character maps to same embedding

---

# Model Architecture

* Embedding layer
* GRU (multi-layer)
* Linear output layer

Flow:
Input → Embedding → GRU → Linear → Predictions

---

# Loss Function

* CrossEntropyLoss used
* Suitable for multi-class character prediction

---

# Training Strategy

* Optimizer: NAdam
* Metric: Accuracy
* Learning rate scheduling applied
* Validation performed after each epoch

---

# Text Prediction

* Model predicts probability distribution for next character
* Highest probability or sampled character selected

---

# Sampling

* Used torch.multinomial
* Allows probabilistic selection instead of fixed output
* Produces more natural text

---

# Temperature Control

* Applied during softmax

Low temperature:

* More deterministic
* Repetitive output

High temperature:

* More random
* Less meaningful

---

# Text Generation

* next_char() predicts next character
* extend_text() generates full sequence
* Iteratively builds text

---

# Key Learnings

* Text must be encoded numerically for modeling
* Sliding window enables sequence learning
* Embeddings improve representation
* GRU captures sequential dependencies
* Sampling introduces diversity in output
* Temperature controls randomness

---

# Conclusion

This project builds a strong foundation in character-level NLP by implementing text encoding, sequence modeling, and text generation using a GRU network. It demonstrates how neural networks can learn language patterns and generate new text based on learned distributions.

---
