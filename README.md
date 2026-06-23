
# 🛡️ Hệ Thống Phát Hiện Xâm Nhập Mạng IoT Bằng AI (IoT-NIDS)

> **Dự án:** Ứng dụng Trí tuệ nhân tạo (Machine Learning & Deep Learning) để phân tích lưu lượng mạng và phát hiện các cuộc tấn công nhắm vào thiết bị IoT.

---

## 📖 1. Giới thiệu dự án (Project Overview)
Sự bùng nổ của các thiết bị Internet of Things (IoT) mang lại nhiều tiện ích nhưng cũng mở ra các lỗ hổng bảo mật nghiêm trọng (như Botnet, DDoS). Các hệ thống tường lửa dựa trên luật (rule-based) truyền thống không còn đủ khả năng đối phó với các dạng tấn công biến đổi liên tục.

**Mục tiêu của dự án:**
Xây dựng một "bộ lọc" AI tự động phân loại gói tin mạng (Bình thường vs Tấn công) bằng cách học hỏi từ hành vi luồng dữ liệu (Network Flow). Dự án sẽ tiến hành huấn luyện song song và so sánh hiệu năng của hai kiến trúc:
1.  **Machine Learning:** Random Forest (RF).
2.  **Deep Learning:** Multi-layer Perceptron Neural Network (MLP).

---

## 🏗️ 2. Kiến trúc hệ thống (System Architecture)
Dự án được triển khai theo luồng Pipeline 4 bước chuẩn hóa:

1.  **Data Collection:** Sử dụng tập dữ liệu mạng IoT tiêu chuẩn (dự kiến: *CICIoT2023* hoặc *Edge-IIoTset*).
2.  **Preprocessing:** Xử lý giá trị rỗng, loại bỏ các đặc trưng gây nhiễu (IP, MAC), mã hóa nhãn (Label Encoding) và chuẩn hóa dữ liệu (StandardScaler).
3.  **Model Training:** Huấn luyện mô hình RF và kiến trúc mạng MLP.
4.  **Evaluation:** Đánh giá trên tập dữ liệu kiểm thử (Test set) dựa trên 4 chỉ số: Accuracy, Precision, Recall và F1-Score.

---

## 📁 3. Cấu trúc Thư mục (Directory Structure)
Cấu trúc repository được thiết kế để dễ dàng mở rộng và bảo trì:

```text
BTL_AI_NETWORK/
│
├── datasets/                   # (Đang cập nhật) Chứa dữ liệu gốc (CSV)
├── clean_data/                 # Chứa dữ liệu đã qua tiền xử lý (Train/Test)
├── models/                     # Thư mục lưu trữ mô hình sau huấn luyện (.pkl, .h5)
├── source_code/                # Nơi chứa mã nguồn chính
│   ├── 1_preprocessing.py      # Script làm sạch và chuẩn hóa dữ liệu
│   ├── 2_train_rf.py           # Script huấn luyện Random Forest
│   ├── 3_train_dl.py           # Script huấn luyện Neural Network
│   └── 4_evaluation.py         # Script kiểm thử và xuất báo cáo hiệu năng
│
├── docs/                       # Slide báo cáo, tài liệu tham khảo
├── requirements.txt            # Danh sách các thư viện cần cài đặt
└── README.md                   # Thông tin tổng quan dự án
## 👥 6. Nhóm phát triển (Contributors)

Dự án được phân chia theo luồng kiến trúc Pipeline để tối ưu hóa thời gian phát triển và tích hợp:

* **Lê Việt Bắc** (Data Engineer & ML Engineer)
  * Khảo sát, thu thập tập dữ liệu CICIoT2023 / Edge-IIoTset.
  * Lập trình khâu tiền xử lý (Làm sạch, Label Encoding, StandardScaler).
  * Xây dựng và tinh chỉnh siêu tham số cho mô hình Random Forest.

* **Chương Tuấn Hùng** (DL Engineer & QA)
  * Thiết kế kiến trúc mạng nơ-ron đa lớp (MLP) với kỹ thuật Dropout.
  * Huấn luyện mô hình Deep Learning trên tập dữ liệu đã chuẩn hóa.
  * Viết script đánh giá (Evaluation) và trực quan hóa (Confusion Matrix, Feature Importances).
💻 4. Công nghệ sử dụng (Tech Stack)
Ngôn ngữ: Python 3.x

Xử lý dữ liệu: Pandas, Numpy, Scikit-learn

Machine Learning: Scikit-learn (RandomForestClassifier)

Deep Learning: TensorFlow / Keras

Môi trường huấn luyện: Google Colab / Jupyter Notebook

🚀 5. Lộ trình triển khai (Roadmap)
[ ] Lên ý tưởng và xác định kiến trúc hệ thống.

[ ] Khởi tạo Repository và setup môi trường.

[ ] Thu thập dữ liệu (CICIoT2023) và viết script tiền xử lý (1_preprocessing.py).

[ ] Xây dựng và huấn luyện mô hình Random Forest & Neural Network.

[ ] Chạy kiểm thử, tinh chỉnh siêu tham số (Hyperparameter tuning) để tăng Precision/Recall.

[ ] Hoàn thiện source code, viết báo cáo tổng kết và chuẩn bị Slide bảo vệ.
