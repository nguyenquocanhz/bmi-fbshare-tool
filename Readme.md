# 🧮 BMI Calculator + Random FB Share — **NQA TECH**

Web mini **all–in–one** viết bằng **HTML + Tailwind CSS + Vanilla JS**.  
Tập trung vào 2 việc: **tính/giải thích BMI chuẩn WHO** và **sinh link Facebook share (mock)** để test QA.

---

## ✨ Tính năng chính

- **BMI Calculator (WHO)**
  - Công thức chuẩn, phân loại rõ ràng (Gầy → Bình thường → Tiền béo phì → Béo phì 1/2/3).
  - Hiển thị **“độ cận” ±0.2 BMI** (phản ánh sai số đo).
  - **Cân nặng lý tưởng** theo chiều cao (range WHO).
  - **Thang màu + kim chỉ** trực quan.
  - **Tính tuổi** từ **DOB** (ngày sinh) nếu cung cấp.

- **Sàng lọc NVQS (VN) – sơ bộ**
  - Rule mặc định: **BMI 18.0–29.9**, **cận > 1.5 diop** hoặc **loạn > 1.0 diop** thường **không đạt** (tham khảo).
  - Có field ghi **tiền sử bệnh** để note rủi ro, chỉ **tham khảo** – quyết định thuộc **Hội đồng khám**.

- **Random Facebook Share Link (mock)**
  - Sinh link dạng: `https://www.facebook.com/share/p/<MÃ>/`
  - **Mã luôn bắt đầu bằng ký tự `1`**, cho phép tùy biến **độ dài** & **charset**.
  - **Copy** nhanh vào clipboard, **Download .txt**.

- **Theme**
  - Hỗ trợ **Light/Dark/System/Auto** (lưu vào `localStorage`, tự boot tránh flash).

---

## 🧩 Luật validate & ràng buộc dữ liệu

- **DOB (dd/mm/yyyy)**:
  - **Năm sinh 1998–2010** (bao gồm 2 đầu).
  - **Tuổi ≤ 26** tại thời điểm hiện tại.
  - Không cho **ngày tương lai**.
- **Cân nặng**: 1–200 **kg**.
- **Chiều cao**: 1–200 **cm**.
- **Cận/Loạn**: cho phép bỏ trống; nếu nhập phải **0–10 diop**.
- Hiển thị **lỗi ngay dưới input** + viền đỏ; không spam `alert`.

> **Lưu ý:** Phần **NVQS** chỉ là **sàng lọc sơ bộ** để tham khảo. Chuẩn chính thức phụ thuộc văn bản hiện hành và kết luận **Hội đồng khám**.

---

## 🚀 Chạy nhanh (local)

Không cần build. Chỉ 1 file `index.html`.

```bash
git clone https://github.com/<your-username>/bmi-fbshare-tool.git
cd bmi-fbshare-tool

# Mở trực tiếp:
start index.html    # Windows
open index.html     # macOS
xdg-open index.html # Linux
