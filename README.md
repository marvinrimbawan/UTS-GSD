   # UTS Graf Sains Data: Graf Interaksi E-commerce dan Rekomendasi KNN

   **Nama:** Mochamad Marvin Rimbawan
   **NIM:** 23031554147
   **Mata kuliah:** Graf Sains Data (Prodi S1 Sains Data, UNESA)

   Analisis graf interaksi e-commerce **RetailRocket** menggunakan **Neo4j** dan **Python**: persiapan data, EDA, Vector Space Modelling (VSM), perhitungan similarity, dan rekomendasi KNN dengan evaluasi Hit@5 dan NDCG@5.

   ## Isi repositori

   | File | Keterangan |
   |---|---|
   | `1.2_Driver_Neo4J.ipynb` | Tugas pendahuluan 1.2: penggunaan driver Neo4j dan jawaban checkpoint |
   | `1.3_Impor_Data.ipynb` | Tugas pendahuluan 1.3: filter periode dan impor data ke Neo4j secara batch |
   | `UTS_GSD.ipynb` | **Notebook utama:** soal 2.1 (Wrangling dan EDA) dan 2.2 (Analytics), beserta penjelasan final |
   | `data/events_train.csv` | Data training: 26 Mei – 26 Juli 2015 (1.312.675 baris) |
   | `data/events_test.csv` | Data testing: 4 – 19 Agustus 2015 (289.750 baris) |
   | `gambar/` | Screenshot dan gambar yang dipakai pada penjelasan |
   | `requirements-final.txt` | Daftar paket Python yang dipakai |

   ## Dataset
   Sumber: [RetailRocket e-commerce dataset (Roman Zykov), Kaggle](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset). Dataset mentah (`events.csv`) tidak diunggah ke repositori ini karena ukurannya besar. File di folder `data/` adalah hasil filter periode sesuai pembagian fold individu.

   ## Cara menjalankan
   1. Buat environment Python 3.10 dan install paket: `uv pip install -r requirements-final.txt`.
   2. Jalankan **Neo4j Desktop** (instance kosong, database `neo4j`) dan siapkan password.
   3. Jalankan `1.3_Impor_Data.ipynb` untuk mengimpor data training ke Neo4j.
   4. Jalankan `UTS_GSD.ipynb` dari atas ke bawah (seed acak 42, hasil dapat direproduksi). Password Neo4j akan diminta saat sel koneksi dijalankan.

   ## Ringkasan hasil

   | Tahap | Hasil |
   |---|---|
   | Graf training | 848.431 simpul (677.687 Visitor, 170.744 Item), 1.312.675 relasi |
   | Proyeksi terpilih | User–User (cakupan 93,47% vs 60,80% untuk Item–Item) |
   | KNN (k = 5), 300 user | Hit@5 = 0,0033, NDCG@5 = 0,0009 (pembanding item terpopuler: 0,0033 dan 0,0033) |

   Penjelasan lengkap ada di bagian **Penjelasan Final** pada `UTS_GSD.ipynb`.