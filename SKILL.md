---
name: muasamcong-autopilot-sdk
description: Hệ thống AI Tự động Săn Thầu, Bóc Tách YCBG/E-HSMT, Đóng Gói Hồ Sơ & Nộp Thầu Ký Số USB Token 1-Shot (45 giây) Đa Ngành Nghề trên Hệ thống Mạng đấu thầu Quốc gia (muasamcong.mof.gov.vn).
---

# QUY TRÌNH VẬN HÀNH MUASAMCONG AUTOPILOT SDK CHO AI AGENT (CURSOR / CLAUDE / ANTIGRAVITY)

Khi người dùng yêu cầu **tìm gói thầu**, **kiểm tra máy ký số USB Token**, hoặc **nộp báo giá / dự thầu** trên `muasamcong.mof.gov.vn`, AI Agent **BẮT BUỘC** sử dụng trực tiếp công cụ CLI `bin/ebid_autopilot.py` trong repo này (tuyệt đối không tự viết script bấm chuột mò mẫm).

## 1. Kiểm tra hạn mức Miễn phí (03 gói đầu) hoặc Bản quyền (`status`)
```bash
python3 bin/ebid_autopilot.py status --profile config/company_profile.json
```

## 2. Săn gói thầu & Yêu cầu báo giá theo ngành nghề (`hunt`)
```bash
python3 bin/ebid_autopilot.py hunt --profile config/company_profile.json
```

## 3. Kiểm tra Pre-Flight máy Windows & USB Token trước khi nộp (`preflight`)
```bash
python3 bin/ebid_autopilot.py preflight --profile config/company_profile.json
```

## 4. Nộp Báo Giá & Ký Số USB Token 1-Shot trong 45 giây (`submit`)
```bash
python3 bin/ebid_autopilot.py submit \
  --profile config/company_profile.json \
  --request-quote-id "<UUID_HOAC_DE_TRONG>" \
  --pkg-code "<MA_RQ_HOAC_IB>" \
  --unit-prices "<GIA_MUC_1,GIA_MUC_2,...>" \
  --local-bundle "<DUONG_DAN_FILE_ZIP_HO_SO>" \
  --doc-name "Ho so bao gia va nang luc du thau <MA_GOI>" \
  --proof "./Minh_Chung_Nop_Thau_<MA_GOI>.png"
```
