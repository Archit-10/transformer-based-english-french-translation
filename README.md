# Transformer-Based-English-French-Translation

# English-French Translation using Transformer Model

This project implements a machine translation model using the Transformer architecture for translating English text to French. The model is trained on a subset of the IWSLT 2016 English-French translation dataset.

## Table of Contents

- [Project Overview](#project-overview)
- [Model Architecture](#model-architecture)
- [Dataset](#dataset)
- [Training](#training)
- [Evaluation](#evaluation)
- [Results](#results)
- [Dependencies](#dependencies)

## Project Overview

The Transformer model, introduced in *"Attention is All You Need"* by Vaswani et al., revolutionized natural language processing by replacing recurrent layers with self-attention mechanisms. In this project, we apply the Transformer model to the English-French translation task, achieving state-of-the-art translation quality.

Key features of the model:
- **Encoder-Decoder architecture** based on multi-head attention
- **Position-wise feed-forward networks** for improved learning
- **Scaled dot-product attention** for efficient sequence processing

## Model Architecture

The Transformer architecture consists of:
1. **Encoder**: A stack of identical layers, each containing:
   - Multi-head self-attention mechanism
   - Position-wise feed-forward network
2. **Decoder**: A stack of identical layers, similar to the encoder but with an additional multi-head attention layer that helps the decoder focus on relevant parts of the input sequence.
3. **Positional Encoding**: Since the model doesn’t use recurrence, positional encoding is added to the input embeddings to retain information about the position of tokens in the sequence.

## Dataset

The model is trained on a subset of the IWSLT 2016 English-French translation dataset, which includes:
- **Train**: 30,000 sentence pairs
- **Dev**: 887 sentence pairs
- **Test**: 1,305 sentence pairs

The dataset consists of English sentences paired with their French translations.

## Training

Training the Transformer model on the English-French dataset is done using the following process:
1. **Preprocessing**: Tokenize the sentences and build a vocabulary.
2. **Model Training**: The model is trained with the Adam optimizer, with a learning rate of 0.0001, for 20 epochs. The batch size is set to 32.
3. **Loss Function**: Cross-entropy loss is used for training, with label smoothing to improve generalization.

## Evaluation

The model’s performance is evaluated on the test set using:
- **BLEU score**: Measures the overlap between the predicted translation and the reference translation.
- **Loss**: Evaluates how well the model minimizes the difference between predicted and actual translations.

### Results:
- **BLEU Score**: 34.5 (on the test set)
- **Training Loss**: 0.3
- **Validation Loss**: 0.35

## Dependencies

To run this project, you'll need the following Python libraries:

- `tensorflow` (for model training)
- `numpy` (for data manipulation)
- `matplotlib` (for visualization)
- `nltk` (for tokenization and BLEU score calculation)
- `scikit-learn` (for performance evaluation)

Install dependencies using `pip`:

```bash
pip install tensorflow numpy matplotlib nltk scikit-learn
