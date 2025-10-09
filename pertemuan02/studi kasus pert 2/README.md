## 1. Studi Kasus: Keputusan Energi AC Cerdas

Studi kasus ini berfokus pada pengembangan sistem cerdas yang dapat **merekomendasikan tindakan terbaik** untuk perangkat AC atau pemanas, bukan sekadar mengikuti suhu yang diatur secara manual.

### Tujuan Utama
Untuk menciptakan sistem yang dapat meniru penalaran manusia dalam memutuskan kapan harus mendinginkan, memanaskan, atau membiarkan suhu stabil, dengan mempertimbangkan **efisiensi energi** dan **kenyamanan penghuni**.

### Data Input yang Digunakan
1.  **Suhu Luar (Suhu Lingkungan):** Faktor eksternal yang paling jelas.
2.  **Aktivitas Rumah (Variabel *Insight* Baru):** Menggantikan input terpisah seperti "Kebiasaan Penghuni" dan "Kondisi Perangkat" menjadi satu indeks numerik (1 = Sangat Rendah hingga 4 = Sangat Tinggi) untuk mewakili keberadaan dan penggunaan perangkat di rumah.

---

## 2. Fungsi Logika Fuzzy (Fungsi Keanggotaan & Aturan)

Logika Fuzzy berfungsi sebagai "otak" yang menerjemahkan data input yang kabur (misalnya, seberapa "panas" suhu 28°C itu) menjadi keputusan output yang jelas (Skor Aksi AC).

### A. Fungsi Keanggotaan (*Membership Functions*)
Fungsi ini menerjemahkan nilai numerik menjadi istilah linguistik (fuzzy set):

| Variabel | Numerik | Menjadi Istilah Linguistik |
| :--- | :--- | :--- |
| **Suhu Luar** | 18°C, 26°C, 30°C | **Dingin**, **Sedang**, **Panas** |
| **Aktivitas Rumah** | 1, 4, dll. | **Rendah**, **Tinggi** |
| **Aksi AC** | Skor 0 - 10 | **Pemanasan**, **Stabil**, **Pendinginan** |

**Fungsinya:** Memungkinkan sistem untuk mengatakan, "Suhu 23°C memiliki derajat keanggotaan 0.7 dalam set 'Dingin' dan 0.3 dalam set 'Sedang'."

### B. Aturan Fuzzy (*Fuzzy Rules*)
Aturan adalah blok bangunan pengambilan keputusan, dirumuskan dalam format **IF-THEN** berdasarkan pengetahuan ahli (atau data historis):

| Contoh Aturan (R6) | Penjelasan |
| :--- | :--- |
| **JIKA** Suhu Luar **Panas** **DAN** Aktivitas Rumah **Tinggi** **MAKA** Aksi AC **Pendinginan** | Logika: Jika di luar sangat panas dan ada banyak orang/perangkat aktif di dalam, prioritaskan pendinginan. |

**Fungsinya:** Menghubungkan semua kombinasi input fuzzy untuk menentukan tindakan output fuzzy.

---

## 3. Cara Membaca dan Menginterpretasikan Hasil

Output dari sistem ini adalah **Aksi AC Score**, sebuah nilai tunggal yang dihasilkan melalui proses **Defuzzifikasi** (mengubah output fuzzy kembali menjadi nilai numerik yang tajam).

### A. Aksi AC Score (Skor 0 - 10)
Ini adalah skor akhir yang direkomendasikan sistem:

* **Skor Rendah (≈ 0 - 3.5):** Mendorong **Pemanasan**. (Misalnya, Suhu Luar Dingin dan Aktivitas Rendah).
* **Skor Tengah (≈ 3.5 - 6.5):** Mendorong **Stabil**. (Misalnya, Suhu Luar Sedang atau Suhu Luar Panas tapi Aktivitas Rendah untuk menghemat energi).
* **Skor Tinggi (≈ 6.5 - 10):** Mendorong **Pendinginan**. (Misalnya, Suhu Luar Panas dan Aktivitas Tinggi).

### B. Aksi AC Category
Skor numerik tersebut kemudian diklasifikasikan kembali menjadi label yang dapat dimengerti:

| Kategori | Aksi Perangkat |
| :--- | :--- |
| **Pemanasan** | Perangkat harus menyalakan pemanas atau mode pemanas. |
| **Stabil** | Perangkat harus menjaga suhu, mati, atau beroperasi pada mode hemat energi. |
| **Pendinginan** | Perangkat harus menurunkan suhu AC atau menyalakan mode pendingin. |

**Kesimpulan Bacaan:** Jika kita lihat baris data dengan **Suhu Luar 30°C** dan **Aktivitas Rumah 4**,maka **Aksi AC Score** mendekati 10, yang akan menghasilkan kategori **Pendinginan**. Ini menunjukkan bahwa sistem telah berhasil menangkap hubungan logis bahwa cuaca panas ditambah aktivitas tinggi membutuhkan pendinginan maksimum.
