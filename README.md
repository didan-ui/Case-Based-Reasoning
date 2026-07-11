# Case-Based Reasoning for Indonesian Criminal Court Decisions

Sistem Case-Based Reasoning (CBR) untuk pencarian kasus hukum serupa menggunakan dokumen putusan pidana Indonesia. Proyek ini membandingkan dua metode retrieval, yaitu **TF-IDF** dan **IndoSBERT**, untuk menemukan kasus yang paling relevan berdasarkan deskripsi perkara.

## Dataset

Dataset berupa dokumen putusan pengadilan dalam format PDF yang diperoleh dari repositori GitHub.

- Domain : Putusan Pidana
- Format : PDF
- Jumlah Dokumen : 50
- Bahasa : Indonesia

## Project Structure

```
Case-Based-Reasoning/
│
├── data/
│   ├── raw/                 # PDF Putusan
│   ├── extracted_text/      # Hasil ekstraksi PDF
│   ├── processed/           # cases.csv & cases.json
│   └── results/             # Hasil retrieval & evaluasi
│
├── notebooks/
│   └── Case_Based_Reasoning.ipynb
│
├── README.md
└── requirements.txt
```

## Workflow

### 1. Case Base

- Mengambil seluruh dokumen PDF
- Ekstraksi teks menggunakan pdfplumber
- Menyimpan hasil ekstraksi ke dalam file TXT

### 2. Case Representation

Setiap dokumen direpresentasikan menjadi:

- Case ID
- Nomor Perkara
- Nama Terdakwa
- Pengadilan
- Pasal
- Amar Putusan
- Case Description
- Full Text

Selanjutnya disimpan menjadi:

- cases.csv
- cases.json

### 3. Retrieval

Dua metode retrieval digunakan.

#### TF-IDF

- Text Preprocessing
- Stopword Removal
- Stemming
- TF-IDF Vectorization
- Cosine Similarity

#### IndoSBERT

- Sentence Embedding
- Cosine Similarity
- Top-K Retrieval

### 4. Reuse

Solusi diperoleh menggunakan:

- Weighted Similarity untuk prediksi pasal
- Amar Putusan dari kasus dengan similarity tertinggi sebagai rekomendasi solusi

### 5. Evaluation

Evaluasi dilakukan menggunakan query yang dihasilkan secara otomatis dari setiap case description.

Metrik yang digunakan:

- Accuracy
- Precision
- Recall
- F1-Score

Evaluasi dilakukan pada:

- TF-IDF
- IndoSBERT

## Installation

Clone repository

```bash
git clone https://github.com/didan-ui/Case-Based-Reasoning.git
```

Masuk ke folder project

```bash
cd Case-Based-Reasoning
```

Install dependencies

```bash
pip install -r requirements.txt
```

## Required Libraries

- pandas
- numpy
- pdfplumber
- scikit-learn
- nltk
- Sastrawi
- sentence-transformers
- torch

## Output

Folder `data/results/` akan berisi:

```
tfidf_results.csv
comparison_metrics.csv
predictions.csv
```

## Retrieval Methods

| Method | Description |
|----------|------------|
| TF-IDF | Keyword-based retrieval menggunakan TF-IDF dan Cosine Similarity |
| IndoSBERT | Semantic retrieval menggunakan sentence embedding |

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-Score

## Author

Adhidhan Obiansyah
Faza Abdillah

Informatics Engineering
