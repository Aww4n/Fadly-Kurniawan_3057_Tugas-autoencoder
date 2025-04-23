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

```python
img = load_and_resize_image(image_path, target_size=(128, 128))
noisy_img = add_salt_and_pepper_noise(img, amount=0.1)
```

### 2. Melatih Autoencoder
- Model dilatih menggunakan data noisy sebagai input dan clean sebagai target.

```python
history = autoencoder.fit(X_train_noisy, X_train_clean,
                          epochs=30, batch_size=8, validation_data=(X_val_noisy, X_val_clean))
```

### 3. Visualisasi Hasil
Menampilkan perbandingan antara gambar noisy, hasil denoising, dan gambar asli.

```python
show_results(X_val_noisy, decoded_imgs, X_val_clean)
```

### 4. Simpan Model
Model disimpan sebagai file `.h5` agar dapat digunakan kembali.

```python
autoencoder.save('autoencoder_daun.h5')
```
📊 Hasil Training
Model dilatih selama 30 epoch. Visualisasi loss training dan validasi:
![training](https://github.com/user-attachments/assets/2dd48d71-9773-4cd4-88f3-e2d1b7598c2b)

💡 Contoh Visualisasi Output
Tampilan perbandingan gambar asli (clean), yang diberi noise (noisy), dan hasil prediksi model (denoised):
![Result_autoencoder](https://github.com/user-attachments/assets/4d91cb5c-0297-4d47-a914-fed2df14c303)

