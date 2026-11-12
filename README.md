# 🚀 Muasamcong Autopilot SDK (Multi-Industry e-Bidding Engine v3.0)

**Giải pháp Tự động hóa Săn Thầu, Bóc Tách YCBG/E-HSMT, Đóng Gói Hồ Sơ Năng Lực & Ký Số USB Token 1-Shot (45 giây) trên Hệ thống Mạng đấu thầu Quốc gia (`muasamcong.mof.gov.vn`) — Hỗ trợ Đa Ngành Nghề & Tích hợp sẵn cho AI Agent (Antigravity, Claude Code, Cursor).**

---

## 🌟 Điểm Nổi Bật (Why Muasamcong Autopilot SDK?)

1. **Hỗ trợ Đa Ngành Nghề (Multi-Industry Out-of-the-Box)** — Tích hợp sẵn 06 bộ cấu hình mẫu (`presets/`) cho các lĩnh vực đấu thầu phổ biến nhất tại Việt Nam:
   - 🏥 **Thiết bị Y tế, Vật tư tiêu hao, Hóa chất xét nghiệm & Dược phẩm** (`presets/01_thiet_bi_y_te_duoc_pham.json`)
   - 🏗️ **Xây lắp, Cải tạo sửa chữa, Cơ điện M&E & PCCC** (`presets/02_xay_dung_co_dien_pccc.json`)
   - 🧹 **Vệ sinh công nghiệp Bệnh viện/Trường học & Cảnh quan cây xanh** (`presets/03_ve_sinh_cong_nghiep_canh_quan.json`)
   - 💻 **Công nghệ thông tin, Phần mềm, Máy tính & Thiết bị văn phòng** (`presets/04_cntt_phan_mem_van_phong.json`)
   - 🛡️ **Dịch vụ Kiểm soát dịch hại, Diệt côn trùng & Khử khuẩn y tế** (`presets/05_kiem_soat_dich_hai_diet_con_trung.json`)
   - 🍱 **Cung cấp Suất ăn công nghiệp, Thực phẩm & Dịch vụ Bảo vệ** (`presets/06_suat_an_thuc_pham_bao_ve.json`)
2. **Nộp Thầu & Ký Số USB Token 1-Shot (45 Giây)**:
   - Tự động kết nối máy trạm Windows cắm USB Token (Viettel-CA, VNPT-CA, NewTel-CA, FPT-CA, EasyCA...) qua giao thức `WinRM` + `Interactive Scheduled Task`.
   - Tự động giữ phiên đăng nhập trên Chrome Profile riêng biệt (không cần giải lại reCAPTCHA).
   - Tự động điền bảng đơn giá đa hạng mục, tải lên gói hồ sơ `.zip` (`<300MB`) theo chuẩn **Zero-Scroll**, tự động chuyển về Tab 1 nếu USB Token bật tab quảng cáo, tự động nhập mã PIN Token và chụp ảnh màn hình biên nhận có mã băm `SHA-1` làm bằng chứng.
3. **Tương thích 100% với AI Agent (`SKILL.md`)**:
   - Chỉ cần mở thư mục repo này trong **Google Antigravity**, **Cursor**, hoặc **Claude Code**, AI Agent sẽ đọc file `SKILL.md` và thực thi toàn bộ quy trình đấu thầu bằng ngôn ngữ tự nhiên mà không bao giờ bấm lụi hay quên bước.

---

## 🎁 Chính Sách Dùng Thử Miễn Phí 03 Gói Thầu & Bản Quyền (Freemium)

| Hạng mục / Gói Cước | Số Lượng Gói Thầu (`RQ*` / `IB*`) | Chi Phí Bản Quyền | Cơ Chế Kích Hoạt |
| :--- | :---: | :---: | :--- |
| **🎁 Gói Dùng Thử (Free Trial)** | **Miễn phí 03 gói thầu đầu tiên** / mỗi Mã số thuế (`MST`) | **0 VNĐ** | Tự động kích hoạt ngay khi tải Repo về máy |
| **⚡ Gói Theo Lượt (Starter 10)** | **10 gói thầu / năm** | **3.000.000 VNĐ** | Cấp file `config/license.lic` định danh theo MST |
| **💎 Gói Doanh Nghiệp (Pro Yearly)** | **Không giới hạn số gói / 01 năm** | **15.000.000 VNĐ / năm** | Cấp file `config/license.lic` chữ ký số RSA-2048 |
| **🏢 Gói Tập Đoàn (Enterprise Lifetime)** | **Không giới hạn trọn đời + Đa máy trạm** | **65.000.000 VNĐ** | Cấp khóa Enterprise Multi-Node + Hỗ trợ 1-1 |

> 💡 **Cơ chế chống gian lận Hardware-Bound**: Hạn mức 03 gói miễn phí được đối chiếu trực tiếp với **Mã số thuế (`MST`) nằm trong Chứng thư số cứng (USB Token)** khi ký nộp trên `muasamcong.mof.gov.vn` và niêm phong kép. Từ gói thầu thứ 4 trở đi, hệ thống sẽ yêu cầu file bản quyền `config/license.lic` được ký số bất đối xứng **RSA-2048**.

---

## 🛠️ Hướng Dẫn Cài Đặt & Sử Dụng Trong 3 Phút

### Bước 1: Tải Repo và cài đặt thư viện Python
```bash
git clone https://github.com/vanthangqtbv-cpu/muasamcong-autopilot-sdk.git
cd muasamcong-autopilot-sdk
pip install -r requirements.txt
```

### Bước 2: Chọn cấu hình Ngành nghề & Điền thông tin Doanh nghiệp
Sao chép 1 trong 6 file cấu hình mẫu trong thư mục `presets/` đè vào `config/company_profile.json`:
```bash
# Ví dụ: Doanh nghiệp Thiết bị Y tế & Dược phẩm
cp presets/01_thiet_bi_y_te_duoc_pham.json config/company_profile.json
```
Sau đó mở `config/company_profile.json` và điền:
- `tax_code`: Mã số thuế doanh nghiệp của bạn (ví dụ: `"0109998887"`).
- `egp_contractor_id`: Mã định danh nhà thầu trên Mua Sắm Công (ví dụ: `"vn0109998887"`).
- `signing_node`: Địa chỉ máy Windows cắm USB Token (`host`, `username`, `password`, `token_pin`).

### Bước 3: Khởi tạo kết nối 1 lần trên máy Windows cắm USB Token
Trên máy tính Windows cắm USB Token (đã cài sẵn phần mềm `eGP-Agent` của Bộ KH&ĐT và đăng nhập sẵn tài khoản `muasamcong.mof.gov.vn` trên Chrome `Profile 1`), chạy 1 lần lệnh:
```bash
python3 bin/ebid_autopilot.py init-windows --profile config/company_profile.json
```

### Bước 4: Các lệnh vận hành chính

1. **Kiểm tra trạng thái 03 gói miễn phí hoặc thời hạn License**:
   ```bash
   python3 bin/ebid_autopilot.py status --profile config/company_profile.json
   ```
2. **Săn gói thầu & Yêu cầu báo giá mới nhất theo từ khóa ngành nghề**:
   ```bash
   python3 bin/ebid_autopilot.py hunt --profile config/company_profile.json
   ```
3. **Kiểm tra Pre-Flight (Pin, EGP-Agent port `11945`, Chứng thư số USB Token)**:
   ```bash
   python3 bin/ebid_autopilot.py preflight --profile config/company_profile.json
   ```
4. **Đóng gói 04 file PDF Hồ sơ năng lực + Báo giá thành 1 file `.zip` chuẩn Zero-Scroll**:
   ```bash
   python3 bin/ebid_autopilot.py bundle \
     --profile config/company_profile.json \
     --quotation ./01_Bao_Gia_Ky_So.pdf \
     --out ./00_Ho_So_De_Xuat_Tong_Hop_Full.zip
   ```
5. **Nộp Báo Giá & Ký Số USB Token 1-Shot (45 giây)**:
   ```bash
   python3 bin/ebid_autopilot.py submit \
     --profile config/company_profile.json \
     --pkg-code "RQ2600100001" \
     --unit-prices "26000000,8500000,15500000" \
     --local-bundle "./00_Ho_So_De_Xuat_Tong_Hop_Full.zip" \
     --doc-name "Ho so bao gia va nang luc du thau RQ2600100001" \
     --proof "./Minh_Chung_Nop_Thau_RQ2600100001.png"
   ```

---

## 📞 Liên Hệ Đăng Ký Bản Quyền & Hỗ Trợ Kỹ Thuật (Sau Khi Dùng Hết 03 Gói Miễn Phí)

Khi hoàn tất 03 gói thầu miễn phí đầu tiên, để mở khóa nộp thầu không giới hạn, Quý Doanh nghiệp vui lòng liên hệ trực tiếp:

- **Hotline / Zalo hỗ trợ & cấp khóa bản quyền**: **`0889 666 635`**
- **Cú pháp nhắn Zalo**: `EGP <Mã Số Thuế Công Ty Bạn>` (Ví dụ: `EGP 0109998887`)
- **Hướng dẫn kích hoạt**: Sau khi nhận thông tin thanh toán và file `license.lic` qua Zalo, chỉ cần chép vào thư mục `config/license.lic` là hệ thống tự động mở khóa ngay lập tức!
