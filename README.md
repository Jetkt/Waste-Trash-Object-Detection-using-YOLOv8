# 🗑️ Waste & Trash Object Detection using YOLOv8

Proyek *Computer Vision* untuk mendeteksi dan mengklasifikasikan jenis sampah (seperti *plastic* dan *paper*) pada gambar statis menggunakan arsitektur **YOLOv8**. Proyek ini bertujuan untuk membantu sistem pengelolaan sampah otomatis dengan mengenali objek sampah secara *real-time* dan akurat.

---

## 📌 Deskripsi Proyek

Model *Machine Learning* ini dilatih untuk mengenali objek sampah yang berserakan di jalan atau lingkungan sekitar. Pelatihan model ( *training* ) dilakukan menggunakan **YOLOv8 Nano (yolov8n)** untuk mendapatkan keseimbangan yang baik antara kecepatan komputasi dan akurasi deteksi. Model ini memproses masukan berupa gambar (*image detection*) dan menghasilkan *bounding box* beserta tingkat kepercayaan (*confidence score*) dari jenis sampah yang terdeteksi.

---

## 📈 Evaluasi Model & Metrik (Folder `runs/`)

Seluruh metrik hasil pelatihan (*training*) dan validasi model secara otomatis disimpan oleh sistem YOLOv8 di dalam direktori `runs/`. Folder ini berisi bukti performa model dalam mendeteksi objek sampah. 

Beberapa hasil evaluasi utama yang dapat dilihat di dalam folder ini meliputi:

*   **Confusion Matrix (`confusion_matrix.png`):** Menunjukkan tingkat akurasi model dalam mengklasifikasikan kelas `plastic` dan `paper`, serta melihat seberapa sering model keliru (misalnya salah mengenali latar belakang sebagai objek).
*   **PR-Curve & F1-Curve:** Menampilkan tingkat keseimbangan antara *Precision* (ketepatan deteksi) dan *Recall* (kemampuan menemukan semua objek). Grafik ini membuktikan seberapa andal model saat digunakan di kondisi nyata.
*   **Grafik Loss (`results.png`):** Visualisasi penurunan tingkat *Loss* (kesalahan) dari *epoch* pertama hingga akhir, yang membuktikan bahwa model telah "belajar" dengan baik dan tidak mengalami *overfitting*.
*   **Visualisasi Validasi (`val_batch_pred.jpg`):** Gambar sampel dari *dataset* yang sudah diberi *bounding box* prediksi oleh model, yang bisa dibandingkan langsung dengan label aslinya (*ground truth*).

---

## 📁 Struktur Repositori

Dataset dan anotasi pada proyek ini bersumber/diekspor dari **Roboflow**.

```text
├── runs/                # Output otomatis dari YOLOv8 (Matriks konfusi, F1-Curve, PR-Curve, dan visualisasi validasi)
├── tes/ & test/         # Folder berisi data gambar untuk pengujian (Testing)
├── train/               # Folder berisi dataset gambar dan label untuk pelatihan
├── valid/               # Folder berisi dataset untuk validasi selama proses training
├── data.yaml            # File konfigurasi dataset (Path kelas dan direktori)
├── README.dataset       # Informasi detail dataset asli
├── README.roboflow      # Log ekskpor dari platform Roboflow
├── test.ipynb           # Jupyter Notebook untuk menguji (inference) model pada gambar baru
├── trainingmodel.ipynb  # Jupyter Notebook yang berisi script pelatihan (Training) YOLOv8
└── yolov8n.pt           # Pre-trained weights YOLOv8 Nano yang digunakan sebagai dasar
