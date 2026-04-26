# Enhanced CAST 3D Reconstructor 🚀

Dự án cải tiến luồng tái tạo 3D (3D Reconstruction) dựa trên framework CAST, tối ưu hóa cho việc chạy trên Google Colab với cấu hình T4 GPU.

## 🛠 Yêu cầu hệ thống (Environment)
- **Platform:** Google Colab
- **Hardware:** T4 GPU (Khuyến nghị)
- **Python:** 3.10+

## 🚀 Hướng dẫn thực hiện (Execution Flow)

Để đảm bảo các thư viện được nạp chính xác, bạn **BẮT BUỘC** phải tuân thủ thứ tự sau:

1. **Setup Environment:** Chạy Cell cài đặt các thư viện cơ bản.
2. **🔄 Restart Session:** Sau khi Cell 1 chạy xong, vào `Runtime` -> `Restart Session`.
3. **Initialize Models:** Chạy các Cell tải Model Checkpoints và khởi tạo.
4. **Phase 1 (Object Segmentation):** Chạy luồng nhận diện và bóc tách vật thể 2D.
5. **Phase 2 (3D Generation):** Chạy luồng dựng hình 3D (TripoSR Local).

> [!IMPORTANT]
> Việc **Restart Session** sau khi cài đặt thư viện là bước không thể thiếu để tránh lỗi `ImportError` hoặc xung đột phiên bản.

## 🔑 Cấu hình API Keys (API Configuration)

Dự án hỗ trợ cả luồng miễn phí (TripoSR Local) và luồng trả phí (Tripo3D API). Để sử dụng các tính năng nâng cao, bạn cần nạp API Keys theo mẫu sau trong code:

```python
import os
os.environ['OPENAI_API_KEY'] = 'YOUR_OPENAI_API_KEY_HERE'
os.environ['TRIPO3D_API_KEY'] = 'YOUR_TRIPO3D_API_KEY_HERE'
os.environ['REPLICATE_API_TOKEN'] = 'YOUR_REPLICATE_API_TOKEN_HERE'
```

*Lưu ý: Không bao giờ push API keys thật của bạn lên GitHub.*

---
*Phát triển bởi Bubusr cho đồ án tốt nghiệp.*