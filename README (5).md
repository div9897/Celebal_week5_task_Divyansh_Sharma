# 📘 Deep Learning Text Generation Project
### Text Generation using Vanilla RNN, LSTM, and GRU
**Author:** Divyansh Sharma
**Week:** 5

---

## 📌 Project Overview

This project implements and compares three deep learning sequence models — Vanilla RNN, LSTM, and GRU — for next-word prediction and text generation. The models are trained on a football-based text corpus and evaluated on training loss, generated text quality, memory handling, and long-term dependency learning.

---

## 🧠 Problem Statement

Design and implement a deep learning model capable of learning the underlying structure, grammar, and contextual dependencies of a given text corpus to generate coherent and meaningful text sequences using:
- Vanilla RNN
- LSTM
- GRU

---

## 📁 Project Structure

```
week_5_Divyansh_Sharma_Text_Generation_RNN_LSTM_GRU_Learning_Project.ipynb
README.md
```

---

## 📥 Dataset / Corpus

A custom football-based text corpus was used consisting of **23 lines** and **105 unique vocabulary words**. Some sample lines from the corpus:

```
football is a beloved sport worldwide
billions of fans follow it passionately
two teams of eleven players compete
fifa world cup is biggest tournament
pele and maradona were football legends
```

---

## ⚙️ Model Architecture

All three models share the same base architecture:

```
Embedding Layer → Recurrent Layer (RNN / LSTM / GRU) → Dense (Softmax)
```

| Parameter | Value |
|---|---|
| Embedding Dimension | 64 |
| Hidden Units | 128 |
| Epochs | 200 |
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |

---

## 🔤 Tokenization & Sequence Creation

- Text is tokenized using Keras `Tokenizer`
- N-gram sequences are created for next-word prediction
- Sequences are padded to uniform length
- Input `X` and target `y` are split from padded sequences

---

## 📊 Results

### Generated Text (Seed: "football is", Next Words: 10)

| Model | Generated Text |
|---|---|
| RNN | football is a beloved sport worldwide exist england long ago goals just |
| LSTM | football is a beloved sport worldwide millions sport long ago ago ago |
| GRU | football is a beloved sport worldwide worldwide compete ago ago net net |

### Observations

- All three models correctly predicted **"football is a beloved sport worldwide"** — an actual line from the corpus
- **RNN** performed the best overall, generating more varied and relevant words after the initial sequence
- **LSTM** and **GRU** started repeating words like "ago ago" and "net net" due to overfitting on the small dataset

---

## 📉 Training Loss

All three models showed a **consistent decrease in loss** over 200 epochs as seen in the loss comparison graph, confirming that learning took place in all cases.

---

## 🔍 Model Comparison

| Feature | Vanilla RNN | LSTM | GRU |
|---|---|---|---|
| Gates | None | 3 (input, forget, output) | 2 (reset, update) |
| Memory | Poor | Excellent | Good |
| Speed | Fast | Slow | Medium |
| Best For | Short sequences | Long sequences | Balanced |
| Performance (small data) | ✅ Good | ⚠️ Repeats words | ⚠️ Repeats words |

---

## ✅ Conclusion

In this project, I implemented and compared three sequence models for text generation using a football-based corpus. Vanilla RNN performed the best on this small dataset, while LSTM and GRU showed word repetition due to overfitting. This does not mean LSTM and GRU are weaker — their true strength shows on larger and more complex datasets. Overall, this project gave a clear and practical understanding of how RNN, LSTM, and GRU differ in terms of architecture, memory handling, and text generation quality.

---

## 🛠️ Requirements

```
tensorflow
numpy
matplotlib
```

Install using:
```bash
pip install tensorflow numpy matplotlib
```

---

## 🚀 How to Run

1. Open the notebook in **Google Colab**
2. Run all cells from top to bottom
3. View the loss comparison graph
4. Check the generated text output at the bottom
