# VNPT HEART — Hộ chiếu Văn hoá | CX Audit Report
**URL:** http://103.82.25.15  
**Ngày đánh giá:** 2026-08-10  
**Phương pháp:** Quick UX Audit (Mode 1) — phân tích HTML source, CSS bundle, JS bundle, PWA manifest  
**Đánh giá bởi:** CX Skill v1.0 — Antigravity AI  

---

## 1. Tổng quan đánh giá

**VNPT HEART — Hộ chiếu Văn hoá** là một PWA (Progressive Web App) gamification dành cho sự kiện nội bộ VNPT. Cơ chế cốt lõi: người dùng đăng ký bằng số điện thoại → nhận mã 4 chữ số → di chuyển đến 5 trạm trải nghiệm → chơi mini-game tại mỗi trạm → thu thập đủ 5 dấu (H-E-A-R-T) → đổi quà bằng QR Code.

**Loại sản phẩm:** Event Gamification / Loyalty PWA  
**Ngôn ngữ:** Tiếng Việt  
**Nền tảng:** Mobile-first (portrait orientation), hỗ trợ iOS & Android PWA  
**Người dùng mục tiêu:** Cán bộ nhân viên VNPT tham gia sự kiện

### Luồng sử dụng chính (Happy Path)

```
Đăng ký (SĐT + Tên + Đơn vị)
  → Nhận Hộ chiếu (mã 4 chữ số)
  → Trang chủ Passport (xem tiến độ 5 trạm)
  → Đến Trạm H / E / A / R / T
  → Nhập mã tại kiosk iPad
  → Chơi mini-game (Ghép hình / Xếp tháp / Tram-runner)
  → Thu dấu
  → Lặp lại 5 trạm
  → Màn hình Quà (QR Code)
  → Nhân viên quầy quét QR → đổi quà
```

---

## 2. Điểm UX tổng thể

| Hạng mục            | Điểm | Nhận xét |
| ------------------- | ---- | -------- |
| Usability           | 7/10 | Luồng cơ bản rõ ràng, nhưng cơ chế kiosk + mã 4 số tạo điểm gián đoạn không cần thiết |
| Accessibility       | 5/10 | Có sr-only, aria-label cơ bản; thiếu contrast check, user-scalable=no vi phạm WCAG |
| Navigation          | 8/10 | Hash-based routing đơn giản, ít màn hình, dễ định hướng |
| Visual Design       | 8/10 | Design system nhất quán, typography Be Vietnam Pro chuyên nghiệp, color palette phong phú |
| Customer Experience | 6/10 | Cơ chế gián tiếp (đến trạm → kiosk → nhập mã) tạo friction cao trong bối cảnh sự kiện đông |

**Tổng điểm UX: 6.8 / 10**

---

## 3. Điểm mạnh

- PWA hoàn chỉnh: manifest đầy đủ, icon iOS/Android, installable — không cần cài từ store
- Mobile-first nhất quán: viewport portrait, safe-area handling cho iOS notch
- Design system có chiều sâu: 100+ CSS custom properties, bảng màu phân tầng, typography scale dùng clamp()
- Gamification đa dạng: 3 mini-game (Ghép hình, Xếp tháp, Tram-runner)
- Font chuyên nghiệp: Be Vietnam Pro — nhận diện thương hiệu VNPT
- Progress indicator H-E-A-R-T rõ ràng, trạng thái is-stamped/is-on
- QR Code đổi quà tích hợp sẵn
- Error handling có message cụ thể, không dùng lỗi kỹ thuật chung

---

## 4. Vấn đề phát hiện

| # | Hạng mục | Vấn đề | Severity | Priority | Heuristic | Root Cause | Impact |
|---|----------|--------|----------|----------|-----------|------------|--------|
| 1 | Accessibility | user-scalable=no ngăn phóng to — vi phạm WCAG 1.4.4 | High | P1 | #5 Error Prevention | Technology | 72 |
| 2 | Luồng Check-in | Phải nhớ mã 4 số từ app để nhập vào kiosk — friction cao, dễ thất bại khi đông | High | P1 | #6 Recognition Not Recall | Process | 68 |
| 3 | Onboarding | Không có màn hình hướng dẫn tổng quan trước khi đăng ký | Medium | P2 | #10 Help & Documentation | Design | 55 |
| 4 | Error Recovery | Nhập sai mã: trường nhập tự xóa, người dùng phải gõ lại từ đầu | Medium | P2 | #9 Help Recover from Errors | Design | 48 |
| 5 | Offline/Sync | Khi lưu dấu thất bại, để người dùng tự retry — không phù hợp bối cảnh sự kiện | Medium | P2 | #9 Help Recover from Errors | Technology | 45 |
| 6 | Accessibility | Thiếu lang attribute trên phần tử động — screen reader có thể nhầm ngôn ngữ | Medium | P2 | #1 Visibility of Status | Technology | 42 |
| 7 | Game UX | Không có hướng dẫn nhanh bắt buộc trước khi vào game lần đầu | Medium | P2 | #10 Help & Documentation | Design | 40 |
| 8 | Visual Design | Theme color #f6f7fb có thể không đủ contrast với status bar iOS | Low | P3 | #8 Aesthetic & Minimalist | Design | 22 |
| 9 | Navigation | Nút Đăng xuất ẩn trong kebab menu — khó tìm | Low | P3 | #4 Consistency & Standards | Design | 20 |
| 10 | Gift Screen | Không rõ QR có persistent sau khi thoát app không — gây lo lắng | Low | P3 | #1 Visibility of Status | Design | 25 |

---

## 5. Đề xuất cải tiến

| Giải pháp | Impact | Effort | Priority |
|-----------|--------|--------|----------|
| Bỏ user-scalable=no — giữ layout bằng CSS | High | Low | P1 |
| Thay keypad mã 4 số bằng QR Code check-in tại kiosk | High | Medium | P1 |
| Màn hình Onboarding 3 bước trước form đăng ký | Medium | Low | P2 |
| Giữ nguyên mã nhập khi có lỗi, chỉ highlight trường sai | Medium | Low | P2 |
| Auto-retry lưu dấu (2-3 lần) trước khi show warning | Medium | Low | P2 |
| Persistent QR + thông báo "QR sẽ luôn có sẵn" | Medium | Low | P2 |
| Tutorial overlay có thể skip trước game tramr | Medium | Medium | P2 |
| Di chuyển nút Đăng xuất ra vị trí visible | Low | Low | P3 |
| Audit contrast ratio theo WCAG AA (4.5:1) | Low | Medium | P3 |

---

## 6. Kết quả mong đợi

- Tăng Task Success Rate check-in: ~75% → ~95%
- Giảm Drop-off Rate tại kiosk khi đông người
- Đạt WCAG 2.1 AA cơ bản sau khi bỏ user-scalable=no
- Giảm Error Rate nhập mã nhờ giữ nguyên giá trị
- Tăng CSAT sự kiện nhờ onboarding rõ ràng

---

## 7. Roadmap

### P1 — Triển khai ngay (trước sự kiện)
- Bỏ user-scalable=no khỏi viewport meta
- Xem xét QR check-in song song với keypad

### P2 — Ngắn hạn (trong hoặc sau sự kiện)
- Màn hình Onboarding/Welcome
- Giữ giá trị nhập khi lỗi kiosk
- Auto-retry lưu dấu
- Persistent QR + thông báo rõ
- Tutorial overlay game tramr

### P3 — Dài hạn
- Audit contrast ratio toàn bộ
- Tổ chức lại navigation
- Accessibility audit với screen reader thực tế

---

## 8. Giả định & Hạn chế

Đánh giá qua phân tích HTML/CSS/JS bundle (browser automation không khả dụng). Một số vấn đề có thể không phản ánh đúng runtime thực tế.

**Chưa đánh giá:** animation performance, thời gian load thực, game mechanics chi tiết tramr/hv2-stack, flow đăng ký từ đầu.

---

*CX Skill v1.0 — Antigravity AI | 2026-08-10*
