**Nama : Nadhia Shafira**

**Kelas : I241E**

**Matkul : Pengolahan Citra**

**Dosen Pengampu : Dr. Muhamad Fatchan, S.Kom., M.Kom.**

---

# 📌 Praktikum Pengolahan Citra - Pertemuan 8

## 👩‍💻 Deskripsi

Program ini merupakan implementasi pengolahan citra digital menggunakan Python dengan library OpenCV dan Matplotlib. Pengolahan citra dilakukan melalui beberapa tahapan yaitu pembacaan citra, konversi warna, segmentasi citra menggunakan berbagai metode thresholding, serta deteksi tepi objek.

---

## 🎯 Tujuan

* Memahami proses dasar pengolahan citra digital
* Mengubah citra RGB menjadi grayscale
* Menerapkan metode thresholding untuk segmentasi citra
* Membandingkan hasil beberapa metode thresholding
* Mendeteksi tepi objek menggunakan metode Canny

---

## ⚙️ Tools & Library

* Python
* OpenCV (`cv2`)
* Matplotlib (`pyplot`)

---

## 🔄 Tahapan Program & Penjelasan Kode

### 1. Membaca Gambar

```python
img = cv2.imread('gambar.jpg')
```

Penjelasan:

* Fungsi `cv2.imread()` digunakan untuk membaca file gambar
* Jika gambar tidak ditemukan, program akan dihentikan

---

### 2. Konversi Warna (BGR → RGB)

```python
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

Penjelasan:

* OpenCV membaca gambar dalam format BGR
* Matplotlib menggunakan format RGB
* Oleh karena itu perlu dikonversi agar warna tampil dengan benar

---

### 3. Konversi ke Grayscale

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

Penjelasan:

* Mengubah citra menjadi satu channel intensitas (abu-abu)
* Mempermudah proses pengolahan citra selanjutnya

---

### 4. Threshold Biasa

```python
ret, thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)
```

Penjelasan:

* Menggunakan nilai ambang tetap (127)
* Piksel < 127 → hitam (0)
* Piksel ≥ 127 → putih (255)

---

### 5. Adaptive Threshold

```python
adaptive = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)
```

Penjelasan:

* Threshold ditentukan berdasarkan area sekitar piksel
* Cocok untuk citra dengan pencahayaan tidak merata

---

### 6. Otsu Threshold

```python
ret2, otsu = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)
```

Penjelasan:

* Menentukan threshold secara otomatis
* Berdasarkan distribusi intensitas piksel (histogram)

---

### 7. Edge Detection (Canny)

```python
edges = cv2.Canny(gray, 100, 200)
```

Penjelasan:

* Digunakan untuk mendeteksi tepi objek
* Parameter:

  * 100 → threshold bawah
  * 200 → threshold atas

---

## 🔁 Perkembangan Program (Step by Step)

### 🔹 Tahap 1

![foto](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/e6f34dfc72f02a02b07582271b8e765ab4ec8400/ss_uts_citra/ss1.png)

### 🔹 Tahap 2

Menambahkan konversi grayscale

![foto](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/a32c7b9ebd9d15298f440e451263876f18a5d31d/ss_uts_citra/ss2.png)

### 🔹 Tahap 3

Menambahkan thresholding (biner)

![foto](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/8888cc5fd1458aeb12120d5e027b2849837d690d/ss_uts_citra/ss3.png)

### 🔹 Tahap 4

Menambahkan:

* Adaptive Threshold
* Otsu Threshold

![foto](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/4509d5016f6a1606c7d0c2d39e6274e9df646367/ss_uts_citra/ss4.png)

### 🔹 Tahap 5 (Final)

Menambahkan:

* Edge Detection (Canny)

![foto](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/3cfa83e190b55180f9d825d769f2f864fba2bf89/ss_uts_citra/ss5.png)

---

## 📸 Dokumentasi Tambahan

### 📌 Source Code

![Code](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/fae73b6691401fcb4b712d418a5676f10e9a45e5/ss_uts_citra/codingss1.png)

![Code](https://github.com/NadhiaShafira/UTS_PENGOLAHANCITRA/blob/4db74c578ac165d865839b6e4161ca2430583aa5/ss_uts_citra/codingss2.png)

---

### 📌 Struktur Folder

📍 Letakkan di:

```
hasil/hasil3.png
```

![Struktur](hasil/hasil3.png)

---

## 🧠 Analisis Hasil

* Threshold biasa kurang optimal jika pencahayaan tidak merata
* Adaptive threshold lebih fleksibel karena menyesuaikan area lokal
* Otsu memberikan hasil optimal secara otomatis
* Edge detection membantu memperjelas batas objek

---

## 🧾 Kesimpulan

Pengolahan citra dilakukan melalui beberapa tahap penting yaitu konversi citra, segmentasi, dan deteksi tepi. Metode thresholding yang lebih adaptif seperti Otsu dan Adaptive menghasilkan segmentasi yang lebih baik dibandingkan metode threshold biasa.

---

## 🚀 Cara Menjalankan

1. Install library:

```
pip install opencv-python matplotlib
```

2. Jalankan:

```
python main.py
```

---

## 👤 Author

Nama: (Isi Nama Kamu)
NIM: (Isi NIM Kamu)
