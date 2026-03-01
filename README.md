# Transformer and Vision Transformer Architectures

### Urdu Machine Translation & CIFAR-10 Classification

**Author:** Abdul Moiz

---

## 📌 Project Overview

This project implements and evaluates two assignments:

1. **English → Urdu Machine Translation**

   * Models: Transformer and Seq2Seq LSTM + Bahdanau Attention
   * Dataset: UMC005 English–Urdu Parallel Corpus
   * Tokenization: SentencePiece BPE (vocab size = 8,200)

2. **CIFAR-10 Image Classification**

   * Models: Vision Transformer (ViT), Hybrid CNN+MLP, and Transfer-Learning ResNet-18
   * Dataset: CIFAR-10
   * Preprocessing: RandomCrop, RandomHorizontalFlip, and normalization

Evaluation covers metrics like **BLEU, ROUGE, perplexity, accuracy, F1-score**, and visualizations such as **loss curves, confusion matrices, and attention maps**.

---

## ⚙️ Setup & Running

Open the notebook in **Jupyter, Colab, or Kaggle** (with T4 GPU enabled):

```bash
jupyter notebook main.ipynb
```

Run all cells sequentially to preprocess data, train models, and view results.

### Streamlit + ngrok Demo

The notebook includes a **Streamlit + ngrok cell** for each task for interactive demos (replace `abc` with your actual ngrok auth token):
```bash
!ngrok authtoken <your_auth_token>
```

---

## 📊 Results Summary

### 📝 Machine Translation (UMC005 Corpus)

| Model            | BLEU  | Perplexity |
| ---------------- | ----- | ---------- |
| Transformer      | 0.929 | 86.9       |
| LSTM + Attention | —     | 156.8      |

* **Transformer** converged faster and produced higher BLEU.
* **LSTM** reduced loss steadily but required more compute (≈230s/epoch).

### 🖼️ Image Classification (CIFAR-10)

| Model              | Test Accuracy | F1-Score |
| ------------------ | ------------- | -------- |
| Vision Transformer | 0.745         | 0.765    |
| CNN + MLP Hybrid   | 0.813         | 0.815    |
| ResNet-18 (TL)     | 0.397         | 0.408    |

* **Hybrid CNN+MLP** performed best on CIFAR-10.
* **ViT** showed promise but required more data.
* **ResNet TL** struggled due to domain mismatch with ImageNet.

---

## 📂 Datasets Used

* **UMC005 English-Urdu Parallel Corpus** (Quran translation corpus)
  👉 [UMC005 Dataset Link](https://ufal.mff.cuni.cz/umc/005-en-ur/)

* **CIFAR-10 Dataset**
  👉 [CIFAR-10 Dataset Link](https://www.cs.toronto.edu/~kriz/cifar.html)

---

## 🔑 Key Insights

* Attention maps clearly showed alignment between English tokens and Urdu translations.
* Transformer outperformed LSTM on translation both in accuracy and inference speed.
* For image classification, convolutions (CNN+MLP) were more data-efficient than ViTs for small datasets.
* Transfer learning worked poorly without proper domain adaptation.

---

## 📖 References

1. Vaswani et al., *Attention is All You Need*, NeurIPS 2017.
2. Bahdanau et al., *Neural Machine Translation by Jointly Learning to Align and Translate*, 2014.
3. Dosovitskiy et al., *An Image is Worth 16×16 Words*, ICLR 2021.

---
