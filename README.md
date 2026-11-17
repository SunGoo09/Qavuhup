# Văn chương phiêu lưu ký — iOS

## Cấu trúc repository

- `codemagic.yaml`: workflow build IPA cho Codemagic, đặt ngay tại thư mục gốc.
- `ios/VanChuongPhieuLuuKy.xcodeproj`: dự án Xcode và scheme dùng để build.
- `index.html` cùng các ảnh/âm thanh ở thư mục gốc: tài nguyên được đưa vào ứng dụng khi build.

## Đưa lên GitHub và chạy Codemagic

1. Tải gói nguồn, giải nén **toàn bộ nội dung** vào thư mục gốc repository; không chỉ tải riêng file ZIP lên GitHub.
2. Commit và push các tệp lên nhánh mà ứng dụng Codemagic đang theo dõi.
3. Trong Codemagic, chọn nhánh đó và bấm **Check for configuration files**. Chọn workflow `ios-app-store` để build.
4. Trong phần Code signing identities của Codemagic, cấu hình Apple Distribution certificate và App Store provisioning profile cho bundle ID `vn.edu.vanchuongphieuluuky`.

Workflow xuất IPA đã ký vào artifacts của Codemagic. Bản App Store dùng cho App Store Connect/TestFlight; muốn cài trực tiếp lên thiết bị cần cấu hình Development hoặc Ad Hoc signing phù hợp. Không đưa certificate, provisioning profile, API key hay mật khẩu ký vào GitHub.

Build iOS cần macOS/Xcode; máy Windows chỉ chứa mã nguồn, không thể tự tạo IPA.
