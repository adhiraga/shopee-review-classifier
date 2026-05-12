# Shopee Review Classifier

> Klasifikasi sentimen ulasan pelanggan Shopee pakai TF-IDF dan machine learning

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

## Tentang project ini

Project ini bertujuan mengklasifikasikan ulasan pengguna Shopee dari Google Play Store ke dalam tiga kelas sentimen: **Positif**, **Netral**, dan **Negatif**. Semuanya dikerjakan dari nol, mulai dari scraping data sampai evaluasi model.

## Yang dikerjakan

1. Scraping ulasan Shopee dari Google Play Store pakai `google-play-scraper`
2. Preprocessing teks bahasa Indonesia: case folding, hapus emoji, stopword removal, stemming (PySastrawi)
3. Ekstraksi fitur pakai TF-IDF dengan `max_features=3000`
4. Latih dan bandingkan dua model: Multinomial Naive Bayes dan Logistic Regression
5. Evaluasi dengan Accuracy, Precision, Recall, dan F1-Score
6. Visualisasi: distribusi sentimen, WordCloud per kelas, perbandingan akurasi

## Struktur folder

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

- **Sumber**: Google Play Store, aplikasi Shopee Indonesia
- **Library**: `google-play-scraper` dengan `lang='id'`, `country='id'`
- **Target**: minimal 2.000 ulasan
- **Labeling** berdasarkan rating bintang:
  - (4-5 bintang) -> **Positif**
  - (3 bintang) -> **Netral**
  - (1-2 bintang) -> **Negatif**

## Tech stack

| Kategori | Library |
|---|---|
| Scraping | `google-play-scraper` |
| Preprocessing | `PySastrawi`, `nltk`, `emoji`, `re` |
| Modeling | `scikit-learn` (TF-IDF, Naive Bayes, Logistic Regression) |
| Visualisasi | `matplotlib`, `seaborn`, `wordcloud` |
| Notebook | Google Colab |
| Opsional | IndoBERT via HuggingFace |

## Alur notebook

0. Install dependencies
1. Import library
2. Scraping ulasan
3. Eksplorasi data (EDA)
4. Preprocessing teks
5. Labeling otomatis
6. TF-IDF vectorization
7. Split data (80/20, stratify)
8. Model 1 - Multinomial Naive Bayes
9. Model 2 - Logistic Regression
10. Perbandingan akurasi
11. WordCloud per kelas
12. Kata dominan per kelas (TF-IDF score)
13. Kesimpulan

## Target evaluasi

| Model | Target Akurasi |
|---|---|
| Multinomial Naive Bayes | >= 75% |
| Logistic Regression | >= 80% |

F1-Score kelas minoritas minimal **0.50**.

## Output

- Classification report dan confusion matrix tiap model
- Bar chart perbandingan akurasi
- WordCloud untuk tiap kelas sentimen
- Insight: kata dominan per kelas, model terbaik, pola keluhan dan pujian pengguna

## Halaman project

Ada versi visual di `index.html`. Bisa diaktifkan lewat GitHub Pages: Settings > Pages > Branch: main, folder: / (root).

---

Dibuat oleh [Ida Bagus Adhiraga Yudhistira](https://github.com/adhiraga)
