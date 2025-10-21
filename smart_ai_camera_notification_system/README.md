# Hướng dẫn sử dụng Blueprint Gửi Tổng Hợp Buổi Sáng qua Zalo

## 1. Giới thiệu
Blueprint này giúp bạn chụp ảnh từ camera được kích hoạt khi cảm biến chuyển động, cửa, hiện hiện phát hiện chuyển động. Sau đó sẽ phân tích ảnh và đưa ra nội dung trong ảnh có người hay không rồi sẽ thông báo qua các nền tảng nếu bạn đã bật.

## 2. Yêu cầu
- Đã cài đặt Home Assistant phiên bản >= 2023.8.0.
- Đã cài đặt tích hợp Zalo Bot, Telegram, Discorrd và cấu hình xong nếu muốn sử dụng.
- Đã cấu hình Conversation Agent (AI) Google Generative AI.
- Tham khảo cách thêm cấu hình thư mục `media` để có thể lưu và lấy ảnh: https://www.home-assistant.io/integrations/media_source/

## 3. Cài đặt
Nhấn vào nút dưới đây để import blueprint trực tiếp vào Home Assistant của bạn:

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/khaisilk1910/Blueprints/blob/main/smart_ai_camera_notification_system/smart_ai_camera_notification_system.yaml)

Hoặc copy file `smart_ai_camera_notification_system.yaml` vào thư mục `blueprints/automation/` trong Home Assistant.

## 4. Hướng dẫn sử dụng

### 4.1. Cấu hình

Sau khi import blueprint, tạo automation từ blueprint với các thông số sau:

#### **Thông số bắt buộc:**

- **Trigger sensor** - Chọn sensor để kích hoạt automation
  - Có thể là: motion, door, occupancy

- **Camera** - Chọn camera sẽ chụp ảnh
  - Camera sẽ chụp ảnh để phân tích

- **AI-powered (Optional)** - Sử dụng AI hay không
  - Sử dụng AI để phân tích ảnh hay chỉ sử dụng Trigger sensor để gửi thông báo

- **Conversation Agent** - AI model để phân tích ảnh và trả nội dung


#### **Thông số tùy chọn:**

- **Nhiều thông số** - Tùy chọn kéo thả, thêm mới
  - Hỗ trợ nhiều hành động, điều kiện kết hợp

---

### 4.2. Cách hoạt động

Blueprint thực hiện các bước sau:

1. **Kích hoạt** khi có chuyển động từ các sensor đã chọn
2. **Chụp ảnh** từ camera đã chọn và lưu vào `media\snapshots`
3. **Phân tích ảnh** từ các ảnh đã chụp và cho ra nội dung đã phân tích
4. **Gửi thông báo** lên các nền tảng đã trọn.
5. **Tùy chỉnh thêm Actions** nếu muốn

---

### 4.4. Tùy chỉnh nâng cao

#### **Tùy chỉnh Prompt cho AI:**

Bạn có thể thay đổi prompt mặc định để AI tạo tin nhắn theo phong cách riêng

## 5. Xử lý lỗi

### **Tin nhắn không gửi được:**

Kiểm tra:
- Zalo Bot, Telegram, Discord integration đã hoạt động chưa
- Các ID có đúng không
- Kết nối mạng có ổn định không

### **AI không tạo tin nhắn hay tin nhắn quá chung chung:**

Thử:
- Thêm chi tiết hơn vào prompt
- Kiểm tra các entity có dữ liệu thực tế không
- Thử với conversation agent khác


## 7. Lưu ý

- **Múi giờ:** Thời gian sẽ theo múi giờ được cấu hình trong Home Assistant.
- **AI Model:** Chất lượng tin nhắn phụ thuộc vào conversation agent bạn chọn.
- **Zalo Bot:** Cần cấu hình đúng Zalo Bot integration trước khi sử dụng.
- **Weather Data:** Dữ liệu thời tiết phụ thuộc vào weather integration (AccuWeather, OpenWeatherMap, etc.).
- **Calendar Range:** Thời gian xem trước mặc định là 18 giờ, có thể điều chỉnh.
- **Privacy:** Blueprint này không chia sẻ dữ liệu ra bên ngoài, chỉ sử dụng conversation agent đã cấu hình.

---

## 8. Blueprint liên quan

---

## 9. Changelog

**Version 20251021**
- Initial release
- Phân tích hình ảnh chụp được từ camera trích xuất ra nội dung
- Tích hợp conversation agent (AI)
- Tùy chỉnh prompt cho AI
- Gửi qua Home Assistant, Zalo Bot, Telegram, Discord
- Gửi qua Home Assistant: tùy chỉnh icon, màu sắc, nội dung Title, thêm Hành động trên thông báo tùy chọn
- TTS ra loa nội dung đã trích xuất từ ảnh bằng AI

---

## 10. Tác giả

Tạo bởi **khaisilk1910**

---

*Được làm với ❤️ cho cộng đồng Home Assistant Việt Nam*
