# 📱 SMS Spam Detection with Deep Learning

A deep learning project for automatically classifying SMS messages as **spam** or **ham (legitimate)** using TensorFlow/Keras. The project compares a Dense Embedding model with a Bidirectional LSTM (Bi-LSTM), achieving up to **98.39% test accuracy**.

---

## 🎯 Project Overview

SMS spam is a common form of unwanted communication that can contain advertisements, scams, phishing attempts, or other malicious content. This project explores how natural language processing and deep learning can automatically identify spam messages from their text.

The main objective is to build and evaluate neural network models that learn linguistic patterns from SMS messages and classify each message into one of two categories:

- **Ham** — legitimate SMS
- **Spam** — unwanted or potentially harmful SMS

The complete implementation and experiments are available in [`SMS_spam_detection.ipynb`](SMS_spam_detection.ipynb).

---

## 🏆 Key Results

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| **Bi-LSTM** | **98.39%** | **94.56%** | **93.29%** | **93.92%** |
| Dense Embedding | 97.76% | 95.59% | 87.25% | 91.23% |

The **Bi-LSTM model** achieved the best overall test accuracy and F1-score, making it the strongest model evaluated in this project.

---

## 📊 Dataset

The project uses the **UCI SMS Spam Collection** dataset, containing **5,572 SMS messages**.

| Attribute | Description |
|---|---|
| `label` | `ham` or `spam` |
| `Text` | SMS message content |

### Dataset Statistics

- Total messages: **5,572**
- Training samples: **4,457**
- Testing samples: **1,115**
- Average words per message: **16**
- Approximate vocabulary size: **15,686**
- Ham messages: approximately **86%**
- Spam messages: approximately **14%**

The dataset is naturally imbalanced, with legitimate messages significantly outnumbering spam messages.

---

## 🧠 Models Implemented

### 1. Dense Embedding Model

The first model uses a text vectorization layer followed by an embedding representation and global average pooling. It provides a lightweight baseline for learning semantic patterns from SMS text.

**Performance:**

- Training accuracy: **99.6%**
- Validation accuracy: **97.8%**
- Test accuracy: **97.76%**

### 2. Bidirectional LSTM (Bi-LSTM)

The Bi-LSTM model processes text in both forward and backward directions, allowing it to capture contextual relationships between words more effectively.

**Performance:**

- Training accuracy: **99.8%**
- Validation accuracy: **98.4%**
- Test accuracy: **98.39%**

---

## 🔧 Text Preprocessing

The project uses TensorFlow/Keras `TextVectorization` for converting raw SMS text into numerical sequences.

The preprocessing includes:

1. Converting text to lowercase
2. Removing punctuation
3. Tokenizing text
4. Building a vocabulary
5. Converting tokens to integer IDs
6. Padding/truncating sequences to a fixed length

Example configuration:

```python
text_vec = TextVectorization(
    max_tokens=total_words_length,
    standardize='lower_and_strip_punctuation',
    output_mode='int',
    output_sequence_length=avg_words_len
)
```

---

## 🏗️ Deep Learning Workflow

```text
                 SMS Message
                      │
                      ▼
              Text Preprocessing
                      │
                      ▼
             TextVectorization
                      │
                      ▼
               Token Sequences
                      │
             ┌────────┴────────┐
             ▼                 ▼
      Dense Embedding       Bi-LSTM
             │                 │
             ▼                 ▼
        Classification     Classification
             │                 │
             └────────┬────────┘
                      ▼
              Spam / Ham Output
```

---

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab
- NLP
- Deep Learning

---

## 📁 Repository Structure

```text
SMS-spam-detection/
├── README.md
└── SMS_spam_detection.ipynb
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Tauhid-Topu-007/SMS-spam-detection.git
cd SMS-spam-detection
```

### 2. Install dependencies

```bash
pip install tensorflow pandas numpy matplotlib scikit-learn
```

### 3. Run the notebook

Open:

```text
SMS_spam_detection.ipynb
```

You can run the notebook using **Jupyter Notebook, JupyterLab, or Google Colab**.

---

## 📈 Evaluation

The models are evaluated using several classification metrics:

- **Accuracy** — overall percentage of correctly classified messages
- **Precision** — proportion of predicted spam messages that are actually spam
- **Recall** — proportion of actual spam messages successfully detected
- **F1-score** — harmonic mean of precision and recall

For spam detection, precision and recall are particularly important because both false positives and missed spam messages can affect the usefulness of the system.

---

## 🔍 Key Findings

- Deep learning can effectively learn patterns from short SMS text.
- The Dense Embedding model provides a strong lightweight baseline.
- The Bi-LSTM model performs better overall by capturing contextual information in both directions.
- The best model achieved **98.39% test accuracy**.
- The Bi-LSTM achieved an **F1-score of 93.92%**, demonstrating a strong balance between spam precision and recall.
- Accuracy alone should not be used to evaluate spam detection because the dataset is imbalanced.

---

## ⚠️ Limitations

- The dataset is relatively small compared with modern large-scale NLP datasets.
- SMS language and spam patterns can change over time.
- Performance may decrease on messages from different languages, regions, or communication platforms.
- The model may struggle with highly obfuscated spam or newly emerging spam patterns.
- The current project focuses on classification rather than real-time deployment.

---

## 🚀 Future Improvements

Potential extensions include:

- Deploying the model as a REST API using FastAPI or Flask
- Building a real-time SMS spam detection web application
- Experimenting with CNN-LSTM architectures
- Using pretrained transformer models such as BERT
- Applying class-weighting or advanced imbalance techniques
- Adding explainable AI to show why a message was classified as spam
- Evaluating the model on newer and multilingual SMS datasets
- Containerizing the application with Docker

---

## 👨‍💻 Author

**Tauhid Topu**

CSE Student | Machine Learning & Deep Learning Enthusiast

- GitHub: https://github.com/Tauhid-Topu-007
- Portfolio: https://portfolio-frontend-rust-six.vercel.app/

---

## 📄 License

This project is intended for educational and research purposes. Please refer to the original dataset's terms and attribution requirements when redistributing or using the dataset.

---

⭐ If you find this project useful, consider giving the repository a star!

© 2026 Tauhid Topu · SMS Spam Detection with Deep Learning
