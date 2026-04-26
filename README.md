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

## 📂 Danh sách Notebook (Notebooks & Usage)

Tùy vào mục đích thử nghiệm, bạn hãy chọn notebook tương ứng:

*   **Dành cho ảnh thực tế (Recommend):** [CAST_test.ipynb](./experiments/Test_UnlimtedAPI/CAST_test.ipynb)
    *   *Mục đích:* Nhận diện nhiều vật thể (18+) và dựng 3D từng cái một cách tự động.
*   **Dành cho Pipeline gốc (Baseline):** [CASE_Baselien1_2.ipynb](./experiments/baseline_1/CAST_org_pipeline/CASE_Baselien1_2.ipynb)
    *   *Mục đích:* Chạy theo quy trình chuẩn của framework CAST.
*   **Dành cho chạy Unofficial:** [CAST_unoff.ipynb](./experiments/Test_Full/CAST_unoff.ipynb)
    *   *Mục đích:* Các thử nghiệm mở rộng khác.

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