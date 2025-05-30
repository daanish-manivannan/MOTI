# MOTI – Multilingual Open Threat Intelligence 🔐🌐

## 🚀 Project Overview

**MOTI** is a multilingual threat detection and alerting system designed to detect cyberbullying and harmful content in online communications across various languages. The project integrates:

* **Google Translate API** for language normalization
* **Natural Language Processing (NLP)** for data preprocessing
* **DistilBERT (Hugging Face Transformers)** for sentiment classification
* **SMTP and PyWhatKit** for real-time alert generation

All processes are implemented and demonstrated in the Colab notebook: `MOTI_Project_Report.ipynb`.

---

## 🔹 Problem Statement

Current AI systems struggle to identify threats in multilingual environments. Many rely solely on keyword matching, lacking the emotional and contextual understanding necessary to detect subtle cyberbullying or harassment. MOTI proposes an intelligent system that processes multilingual chat data, understands sentiment, and triggers appropriate alerts in real-time.

---

## 📊 Methodology

### 📁 1. Data Acquisition

* **Sources**: Reddit and Twitter (X) using public APIs
* **Ethical Collection**: Only publicly accessible or anonymized data
* **Tools**: Twitter API, Reddit API, and Google Translate API

### 🔄 2. Preprocessing

Performed using a combination of custom logic and standard NLP techniques:

* **Translation**: All data is translated to English using Google Translate API
* **Cleaning**: Lowercasing, punctuation removal, stopword removal, tokenization

### 🔍 3. Threat Detection with DistilBERT

* **Model**: Hugging Face's DistilBERT (lightweight BERT variant)
* **Task**: Binary classification (Cyberbullying vs Non-cyberbullying)
* **Implementation**: Fine-tuned using Hugging Face `Trainer` API
* **Metrics Captured**:

  * Accuracy: \~91-93%
  * Precision: \~90-92%
  * Recall: \~88-91%
  * F1-Score: \~89-91%
  * Confusion Matrix: Visualized in notebook

### ⚠️ 4. Alerting & Reporting

* **Triggers**: Classification of a message as "Cyberbullying"
* **Email Alerts**: Sent via SMTP with threat details
* **WhatsApp Alerts**: Triggered using PyWhatKit
* **Alert Content**: Includes username, message, timestamp, threat classification

---

## 📊 Metrics & Performance

| Component            | Metric                   | Value/Observation       |
| -------------------- | ------------------------ | ----------------------- |
| DistilBERT Accuracy  | Accuracy                 | \~91-93%                |
| Translation Accuracy | Language Dependent       | 55%-94%                 |
| Inference Speed      | Latency                  | \~150-300ms             |
| Preprocessing        | Data reduction           | \~10-15%                |
| Alerting Delay       | Real-time (near-instant) | \~2-5 seconds (typical) |

---

## 📅 Project Flow Diagram

```
Raw Multilingual Chat Data
        ⬇️
Google Translate API (to English)
        ⬇️
NLP Preprocessing
        ⬇️
DistilBERT Sentiment Classification
        ⬇️
Cyberbullying Detected?
    └── Yes ➔ Trigger SMTP / WhatsApp Alert
        └── No ➔ Log and Discard
```

---

## 📚 Repository Contents

```
MOTI/
├── data/                         # Sample multilingual datasets
├── notebooks/
│   └── MOTI_Project_Report.ipynb   # Main implementation notebook
├── src/
│   ├── preprocessing.py           # Translation and NLP utilities
│   ├── classifier.py              # DistilBERT model logic
│   ├── alert.py                   # Email and WhatsApp alerting
│   └── utils.py                   # Shared helper functions
├── requirements.txt               # Dependencies
└── README.md                   # Project overview
```

---

## 🤔 Future Scope

* Real-time streaming (Kafka, Websockets)
* Language-specific model fine-tuning
* Integration with Discord, Telegram, and WhatsApp
* Threat severity scoring and prioritization
* Visualization dashboards (Plotly/Dash)

---

## 🤝 Contributors

* **Mrs. Kavitha M.** – Mentor (Assistant Professor, Dept. of CSE)
* **Student Research Team** – Implementation and Research

---

## 📄 License

This project is licensed under the **MIT License**. See the LICENSE file for details.

---

## 💬 Questions?

Please open an issue or email the team for inquiries or collaboration.
