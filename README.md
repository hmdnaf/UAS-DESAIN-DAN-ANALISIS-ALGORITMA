# UAS-DESAIN-DAN-ANALISIS-ALGORITMA

# 📅 Aplikasi Penjadwalan Shift Karyawan (Backtracking Algorithm)

Implementasi sistem penjadwalan shift karyawan otomatis yang dirancang untuk menyelesaikan tantangan optimasi kombinatorial dan menghindari konflik jadwal menggunakan **Algoritma Backtracking**. 

Proyek ini dikembangkan menggunakan **Python** dengan antarmuka **Gradio** untuk memudahkan manajemen operasional dalam mendistribusikan tugas secara adil dan efisien.

---

| Nama | NIM | Kelas | Semester | Mata Kuliah |
| :--- | :--- | :--- | :--- | :--- |
| **Muh. Chaidir Rijal** | 105841107523 | 5C | 5 (Lima) | Desain dan Analisis Algoritma |
| **Hamdan Al Fattah** | 105841108323 | 5C | 5 (Lima) | Desain dan Analisis Algoritma |

**Dosen Pengampu:** Desi Anggreani, S.Kom., MT  

## 🚀 Fitur Utama

- **Otomatisasi Jadwal**: Menyusun jadwal mingguan untuk 50 karyawan dalam 105 slot shift secara instan.
- **Bebas Konflik**: Menggunakan mekanisme *constraint satisfaction* untuk mencegah jadwal ganda (satu karyawan di dua tempat) dan bentrok waktu.
- **Optimasi Beban Kerja (Bobot)**: Memastikan jumlah shift setiap karyawan tidak melebihi jatah maksimal (*Max_Shift*) untuk mencegah *burnout*.
- **Antarmuka Interaktif**: Dashboard berbasis web (Gradio) yang memungkinkan pengguna mengunggah dataset Excel dan melihat hasil secara langsung.
- **Ekspor Data Otomatis**: Hasil jadwal diekspor ke format Excel (.xlsx) dengan kolom waktu yang informatif (Pagi/Siang/Malam dikonversi ke jam operasional nyata).

---

## 🛠️ Logika Algoritma & Batasan (*Constraints*)

Algoritma divalidasi melalui fungsi `is_safe` untuk menjamin kepatuhan terhadap batasan berikut:
1. **Kesesuaian Skill**: Karyawan hanya ditempatkan pada posisi/pos yang sesuai dengan kompetensi mereka.
2. **Kapasitas Maksimal (Bobot $w$):** Menjaga agar $\sum w \leq W$ (total shift $\leq$ jatah maksimal per karyawan).
3. **Larangan Shift**: Mematuhi aturan spesifik jika karyawan tertentu dilarang masuk pada hari atau jam tertentu.
4. **Konflik Harian**: Menjamin satu karyawan maksimal hanya memiliki satu shift dalam satu hari kerja.

Sistem menggunakan teknik **Tree Pruning (Pemangkasan Pohon)** pada pohon ruang status untuk memangkas jalur yang tidak valid sedini mungkin, sehingga pencarian solusi menjadi sangat cepat.

---

## 📂 Struktur Repositori

| File | Deskripsi |
| --- | --- |
| `backtracking.ipynb` | Notebook utama berisi kode algoritma, logika backtracking, dan UI Gradio. |
| `dataset_50_karyawan_konflik_backtracking.xlsx` | File dataset input (Tabel Karyawan, Shift, dan Larangan). |
| `Hasil_Jadwal_Final_Waktu.xlsx` | Contoh output hasil jadwal yang berhasil di-generate. |
| `README.md` | Dokumentasi proyek. |

---
