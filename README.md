# Denoising Autoencoder untuk Gambar Daun dengan Noise Salt and Pepper

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk membangun model **Denoising Autoencoder** menggunakan **TensorFlow** untuk memulihkan gambar daun yang terkontaminasi oleh **noise salt and pepper**. Dataset terdiri dari gambar daun yang disimpan secara lokal dan diolah dalam berbagai tahap mulai dari preprocessing, penambahan noise, pelatihan model, hingga visualisasi hasil.

---

## 🧱 Arsitektur Model
Model menggunakan **Convolutional Autoencoder**:
- Encoder: Conv2D + MaxPooling
- Decoder: Conv2D + UpSampling
- Aktivasi akhir: Sigmoid
- Loss function: MSE

## 🧱 Dataset
Dataset berupa gambar daun dengan format .jpg berwarna berukuran 128x128 piksel yang disimpan di folder:
# Contoh :
![contoh](https://github.com/user-attachments/assets/d9436862-e410-445d-a4e9-89d97c34e4e3)

## 🔄 Alur Proses

### 1. Preprocessing Dataset
- Gambar diresize ke 128x128 piksel.
- Normalisasi ke rentang [0, 1].
- Diberi salt and pepper noise.


### 2. Melatih Autoencoder
- Model dilatih menggunakan data noisy sebagai input dan clean sebagai target.


### 3. Visualisasi Hasil
Menampilkan perbandingan antara gambar noisy, hasil denoising, dan gambar asli.


### 4. Simpan Model
Model disimpan sebagai file `.h5` agar dapat digunakan kembali.


📊 Hasil Training
Model dilatih selama 30 epoch. Visualisasi loss training dan validasi:
![training](https://github.com/user-attachments/assets/2dd48d71-9773-4cd4-88f3-e2d1b7598c2b)

💡 Contoh Visualisasi Output
Tampilan perbandingan gambar asli (clean), yang diberi noise (noisy), dan hasil prediksi model (denoised):
![Result_autoencoder](https://github.com/user-attachments/assets/4d91cb5c-0297-4d47-a914-fed2df14c303)

