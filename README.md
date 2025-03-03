# Vito_Gunawan_2306149_Latihan_Workflow_AI
## Deskripsi Proyek  
Proyek ini bertujuan untuk mengimplementasikan konsep kecerdasan buatan (AI) dalam analisis dan prediksi penjualan produk. Dalam proyek ini, dilakukan beberapa tahap utama:  

1. **Pembuatan Dataset**  
   - Membuat dataset penjualan dalam format CSV dengan informasi produk, jumlah terjual, stok, dan harga satuan.  

2. **Pembersihan dan Pengolahan Data**  
   - Memproses dataset untuk memastikan data bersih, lengkap, dan siap digunakan dalam model AI.  
   - Menambahkan kolom baru seperti *Total Penjualan* dan *Keuntungan*.  

3. **Pelatihan Model AI**  
   - Menggunakan *Decision Tree Classifier* untuk memprediksi apakah suatu produk perlu restock berdasarkan data penjualan.  

4. **Prediksi dan Visualisasi**  
   - Menggunakan model yang telah dilatih untuk melakukan prediksi apakah produk perlu restock.  
   - Membuat visualisasi *scatter plot* hubungan antara **Jumlah Terjual**, **Stok**, dan **Keuntungan**.


##Instruksi Cara Menjalankan Kode di Google Colab  
### 1️. Buka Google Colab  
- Kunjungi [Google Colab](https://colab.research.google.com/).  
- Pilih **"Unggah"** dan unggah file `praktikum_ai.ipynb`.  
- Setelah diunggah.  

### 2️. Unggah Dataset (Jika Ada)  
Jika menggunakan dataset dalam file CSV, unggah dengan cara:  
- Klik ikon 📎 (**Upload**) di sebelah kiri.  
- Pilih file CSV yang ingin digunakan.  
- Gunakan kode berikut untuk membaca dataset:  

```python
import pandas as pd  
df = pd.read_csv("praktikum_ai.ipynb")
df.head()
```

### 3️.Jalankan Sel Satu Per Satu  
- Klik ▶ (**Run**) pada setiap sel kode dari atas ke bawah.  
- Pastikan tidak ada error sebelum menjalankan sel berikutnya.  

### 4️. Install Dependensi (Jika Diperlukan)  
Jika paket yang dibutuhkan belum terinstal, jalankan perintah berikut dalam sel kode:  

```python
!pip install pandas scikit-learn matplotlib  
```

### 5️. Menghubungkan Google Drive (Opsional, Jika Dataset Ada di Drive)  
Jika dataset atau model disimpan di Google Drive, hubungkan dengan:  

```python
from google.colab import drive  
drive.mount('/content/drive')  
```

### 6️. Menjalankan Model & Prediksi  
Setelah dataset siap dan model dilatih, jalankan prediksi dengan model:  

```python
produk_baru = [[8, 3]]  # Contoh input  
prediksi = model.predict(produk_baru)  

if prediksi[0] == 1:  
    print("Produk perlu di-restock!")  
else:  
    print("Stok masih cukup.")  
```

### 7️. Membuat Visualisasi  
Jalankan sel visualisasi untuk melihat hubungan jumlah terjual, stok, dan keuntungan:  

```python
import matplotlib.pyplot as plt  

plt.scatter(df["Jumlah Terjual"], df["Stok"], c=df["Keuntungan"], cmap="coolwarm")  
plt.xlabel("Jumlah Terjual")  
plt.ylabel("Stok")  
plt.title("Analisis Penjualan dan Stok")  
plt.colorbar(label="Keuntungan")  
plt.show()
