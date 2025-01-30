🆔 Pendeteksi ID Card Event Menggunakan Roboflow & Google Colab
📌 Overview
Proyek ini bertujuan untuk mengembangkan sistem pendeteksi ID card event secara otomatis menggunakan platform Roboflow dan Google Colab. Sistem ini menggunakan teknologi Computer Vision dan Machine Learning, khususnya algoritma YOLO (You Only Look Once), untuk mendeteksi dan memverifikasi ID card peserta acara dengan akurasi tinggi.

📂 Dataset lengkap dapat diakses di sini: Pendeteksi ID Card Dataset (Tambahkan link dataset jika tersedia)

👨‍💻 Disusun Oleh
Raden Aryo Abadi (17220334)
Muhammad Nur Fauzan (17220815)
Maher Ismail Sungkar (19225269)
Lindra Mahesa Putra (17220415)
Anggoro Adhi Febriansyah (17210506)
📧 Email:

17220334@bsi.ac.id
17220815@bsi.ac.id
19225269@bsi.ac.id
17220415@bsi.ac.id
17210506@bsi.ac.id
🎯 Tujuan Proyek
Mendeteksi ID Card secara otomatis dengan menggunakan model YOLOv5.
Mengurangi kesalahan verifikasi manual dalam penyelenggaraan event.
Meningkatkan efisiensi dan akurasi proses identifikasi peserta.
📁 Dataset Information
Dataset yang digunakan dalam proyek ini mencakup gambar ID card yang dikumpulkan dari berbagai sumber, termasuk:
✅ ID Card ICEF & ICC → Diambil menggunakan kamera handphone dan dipindahkan ke laptop.
✅ Random ID Cards → Dikumpulkan dari berbagai sumber di internet.
✅ Jumlah Data Awal: 173 gambar yang diperbanyak menjadi 332 gambar menggunakan augmentasi di Roboflow.

🔹 Pembagian Dataset (Data Split)
Training Set: 50%
Validation Set: 25%
Test Set: 25%
🛠 Tech Stack
Python (OpenCV, Pandas, NumPy, Matplotlib)
Google Colab (Training & Model Deployment)
Roboflow (Data Augmentation & Preprocessing)
YOLOv5 (Object Detection)
📊 Metode Penelitian
Tahapan utama dalam penelitian ini:
1️⃣ Pengumpulan Dataset – Mengambil gambar ID card dari berbagai sumber.
2️⃣ Preprocessing Data – Labeling & augmentasi menggunakan Roboflow.
3️⃣ Training Model – Menggunakan Google Colab untuk melatih model YOLOv5.
4️⃣ Evaluasi Model – Menggunakan Precision, Recall, mAP (Mean Average Precision).
5️⃣ Implementasi & Pengujian – Menjalankan model untuk mendeteksi ID card secara real-time.

🚀 Implementasi Model
1️⃣ Setup Lingkungan di Google Colab
Clone YOLOv5 repository:

bash
Salin
Edit
!git clone https://github.com/ultralytics/yolov5.git
cd yolov5
!pip install -r requirements.txt
2️⃣ Mengimpor Dataset dari Roboflow
python
Salin
Edit
from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_API_KEY") # Ganti dengan API key Roboflow
project = rf.workspace("workspace-name").project("dataset-name")
dataset = project.version(1).download("yolov5")
3️⃣ Melatih Model YOLOv5
bash
Salin
Edit
!python train.py --img 640 --batch 16 --epochs 360 --data dataset.yaml --weights yolov5s.pt
4️⃣ Mendeteksi ID Card dengan Model yang Dilatih
bash
Salin
Edit
!python detect.py --weights runs/train/exp/weights/best.pt --img 640 --source /content/id_card_sample.jpg
📈 Evaluasi Model
Evaluasi dilakukan menggunakan Google Colab & Roboflow Health Check, dengan metrik berikut:
✅ mAP (Mean Average Precision): 95.1%
✅ Precision: 98.9%
✅ Recall: 93.7%

📌 Visualisasi Evaluasi Model:

Confusion Matrix → Memeriksa prediksi yang benar dan salah.
Precision-Recall Curve → Menilai keseimbangan antara presisi & recall.
Bounding Box Analysis → Menilai akurasi deteksi objek pada ID Card.
📜 How to Use
1️⃣ Clone repository ini:

bash
Salin
Edit
git clone https://github.com/username/pendeteksi-id-card.git
2️⃣ Install dependencies:

bash
Salin
Edit
pip install -r requirements.txt
3️⃣ Buka Google Colab & Jalankan Notebook

bash
Salin
Edit
jupyter notebook
4️⃣ Upload dataset & jalankan training model

🤝 Contributing
Jika Anda ingin berkontribusi, silakan fork repository ini, buat branch baru, dan ajukan pull request! 🚀

📩 Contact
📧 Email: sungkarmaher6@gmail.com
🔗 LinkedIn: Maher Ismail Sungkar
