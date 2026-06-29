# 📱 SMS Spam Detection with Deep Learning

## 🎯 Project Overview

This project implements multiple deep learning models for SMS spam detection using TensorFlow/Keras. The models are trained on the UCI SMS Spam Collection dataset and achieve up to **98.4% accuracy** in distinguishing between spam and legitimate (ham) messages.

## 🏆 Key Achievements

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Bi-LSTM** | **98.39%** | 94.56% | 93.29% | 93.92% |
| Dense Embedding | 97.76% | 95.59% | 87.25% | 91.23% |

## 📊 Dataset

The dataset contains **5,572** SMS messages with the following structure:

| Column | Description |
|--------|-------------|
| label | 'ham' or 'spam' |
| Text | SMS message content |

### Dataset Statistics
- **Training samples**: 4,457
- **Testing samples**: 1,115
- **Average words per message**: 16
- **Approximate vocabulary size**: 15,686

### Class Distribution
- Ham (legitimate): ~86%
- Spam: ~14%

## 🧠 Models Implemented

### 1. Dense Embedding Model
A simple but effective architecture using global average pooling.


**Performance:**
- Training Accuracy: 99.6%
- Validation Accuracy: 97.8%
- Test Accuracy: 97.76%

### 2. Bidirectional LSTM (Bi-LSTM) Model
Advanced architecture capturing contextual information from both directions.


**Performance:**
- Training Accuracy: 99.8%
- Validation Accuracy: 98.4%
- Test Accuracy: **98.39%**

## 🔧 Text Preprocessing

### TextVectorization Layer
```python
text_vec = TextVectorization(
    max_tokens=total_words_length,          # 15,686 unique words
    standardize='lower_and_strip_punctuation',
    output_mode='int',
    output_sequence_length=avg_words_len    # 16 words per sequence
)```
