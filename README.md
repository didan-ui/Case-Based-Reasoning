# Sistem Case-Based Reasoning (CBR) Putusan Mahkamah Agung

Proyek ini mengimplementasikan siklus lengkap Case-Based Reasoning (Retrieve, Reuse, Revise, Retain) untuk klasifikasi dan analisis hukum pada dokumen Putusan Mahkamah Agung.

## 1. Persyaratan (Requirements)
Pastikan Anda memiliki Python 3.x dan menginstal pustaka berikut:
```bash
pip install pdfplumber pandas scikit-learn numpy requests
```

## 2. Struktur Folder
Sistem secara otomatis akan mengelola struktur folder berikut:
- `data/raw/`: Menyimpan file PDF asli.
- `data/cleaned/`: Menyimpan hasil ekstraksi teks (.txt) dan `case_base.json`.
- `data/processed/`: Menyimpan data terstruktur dalam format CSV dan JSON.
- `input_pdfs/`: Folder sementara untuk proses unduhan/unggah.

## 3. Cara Menjalankan Pipeline
1. **Tahap 1 (Acquisition):** Jalankan sel inisialisasi untuk mengunduh data dari repositori GitHub atau unggah secara manual.
2. **Tahap 2 (Representation):** Jalankan fungsi ekstraksi untuk mengubah PDF menjadi teks terstruktur.
3. **Tahap 3 (Retrieval):** Masukkan query fakta hukum pada fungsi `retrieve()` untuk mencari kasus serupa.
4. **Tahap 4 & 5 (Reuse, Evaluation, Retention):** Gunakan fungsi `predict_outcome()` untuk klasifikasi otomatis dan `retain_case()` untuk menyimpan kasus baru ke database.

## 4. Contoh Penggunaan
```python
query = "Terdakwa menyalahgunakan narkotika jenis sabu"
hasil = retrieve(query, k=1)
print(hasil)
```

## 5. Kontributor
- Nama Anggota Kelompok : Faza Abdillah (202310370311154) & Adhidhan Obiansyah (202310370311163)
- Mata Kuliah: Penalaran Komputer - C