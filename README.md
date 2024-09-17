# Hindi-English Transliteration

## Overview
This project focuses on building a sequence-to-sequence transliteration system for converting English words into Hindi script using an encoder-decoder model with attention. The project is implemented in PyTorch and trains on the NEWS2012 dataset. The model utilizes GRU-based RNN cells for both the encoder and decoder, with attention mechanisms to enhance the performance. 

## Table of Contents
1. [Project Structure](#project-structure)
2. [Dataset](#dataset)
3. [Model Architecture](#model-architecture)
4. [Training the Model](#training-the-model)
5. [Evaluation](#evaluation)


## Project Structure
- **TransliterationDataLoader**: Custom dataset loader for handling the XML format of the NEWS2012 dataset. It processes English and Hindi words, ensuring clean vocabulary and data alignment.
- **Model (Transliteration_EncoderDecoderAttention)**: GRU-based encoder-decoder architecture with an attention mechanism, facilitating effective transliteration from English to Hindi.
- **Training & Evaluation Scripts**: Functions for training the model, including loss calculation, backpropagation, and optimization. Evaluation scripts test accuracy on both training and test datasets.


## Model Architecture
The core model is a sequence-to-sequence (seq2seq) architecture consisting of:
- **Encoder**: A GRU-based RNN that processes input English words.
- **Attention Mechanism**: Helps the decoder focus on specific parts of the input sequence at each decoding step.
- **Decoder**: A GRU-based RNN that generates Hindi characters, one by one.


## Training the Model
Training is performed using mini-batch gradient descent with the Adam optimizer. A cross-entropy loss function (NLLLoss) is used to measure the model's performance. During training, the model is trained for a fixed number of epochs with teacher forcing enabled for early iterations to guide the model's learning.

### Hyperparameters:
- Learning Rate: 0.001
- Batch Size: 64
- Number of Batches: 4000

## Evaluation
Evaluation is performed on both the training and test datasets. The accuracy metric compares predicted Hindi characters with ground truth at each time step. The final test accuracy reached **78.28%**, while training accuracy achieved **88.34%**.

