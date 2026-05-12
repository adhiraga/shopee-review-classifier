# Shopee Review Classifier

> Analisis Sentimen Ulasan Pelanggan Shopee Menggunakan TF-IDF dan Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

## Deskripsi

Sistem klasifikasi sentimen otomatis untuk menganalisis ulasan pelanggan dari Google Play Store pada aplikasi Shopee. Sistem mengklasifikasikan teks ulasan ke dalam tiga kelas: **Positif**, **Netral**, dan **Negatif**.

## Tujuan

1. Scraping ulasan aplikasi Shopee dari Google Play Store menggunakan `google-play-scraper`
2. Preprocessing teks bahasa Indonesia (case folding, filter emoji, stopword removal, stemming dengan PySastrawi)
3. Ekstraksi fitur teks menggunakan TF-IDF dengan `max_features=3000`
4. Melatih dan membandingkan dua model: Multinomial Naive Bayes dan Logistic Regression
5. Evaluasi model menggunakan Accuracy, Precision, Recall, dan F1-Score
6. Visualisasi distribusi sentimen, WordCloud per kelas, dan perbandingan akurasi model

## Struktur Repo

```
shopee-review-classifier/
├── notebook/
│   └── shopee_sentiment_analysis.ipynb
├── data/
│   └── .gitkeep
├── output/
│   └── .gitkeep
├── index.html
├── requirements.txt
└── README.md
```

## Dataset

- **Sumber**: Google Play Store, Aplikasi Shopee Indonesia
- **Scraping**: `google-play-scraper` dengan parameter `lang='id'`, `country='id'`
- **Jumlah target**: minimal 2.000 ulasan
- **Labeling otomatis** berdasarkan rating:
  - ⭐⭐⭐⭐⭐ (4-5) -> **Positif**
  - ⭐⭐⭐ (3) -> **Netral**
  - ⭐⭐ (1-2) -> **Negatif**

## Tech Stack

| Kategori | Library |
|---|---|
| Scraping | `google-play-scraper` |
| Preprocessing | `PySastrawi`, `nltk`, `emoji`, `re` |
| Modeling | `scikit-learn` (TF-IDF, Naive Bayes, Logistic Regression) |
| Visualisasi | `matplotlib`, `seaborn`, `wordcloud` |
| Notebook | Google Colab |
| Opsional | IndoBERT via HuggingFace |

## Pipeline Notebook

0. Install dependencies
1. Import Library
2. Scraping ulasan Shopee dari Google Play Store
3. Eksplorasi data (EDA)
4. Preprocessing teks
5. Labeling otomatis berdasarkan rating
6. TF-IDF Vectorization
7. Split data (80% train, 20% test, stratify)
8. Model 1 - Multinomial Naive Bayes
9. Model 2 - Logistic Regression
10. Perbandingan akurasi dua model (bar chart)
11. WordCloud per kelas sentimen
12. Analisis kata dominan per kelas (TF-IDF score)
13. Kesimpulan dan insight

## Target Evaluasi

| Model | Target Akurasi |
|---|---|
| Multinomial Naive Bayes | >= 75% |
| Logistic Regression | >= 80% |

F1-Score kelas minoritas tidak di bawah **0.50**.

## Output yang Diharapkan

- Classification report dan confusion matrix untuk dua model
- Bar chart perbandingan akurasi Naive Bayes vs Logistic Regression
- WordCloud untuk kelas Positif, Netral, dan Negatif
- Insight naratif: kata dominan per kelas, model terbaik, pola keluhan dan pujian pengguna

## Halaman Project

Tersedia sebagai GitHub Pages di `index.html`. Aktifkan di Settings > Pages > Branch: main, folder: / (root).

---

Dibuat oleh [Ida Bagus Adhiraga Yudhistira](https://github.com/adhiraga)
