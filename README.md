# Lab: Automated IT Asset Lifecycle Management

## 1. Thông tin cấu hình hệ thống
- **URL Snipe-IT API:** http://172.17.176.1:8081/api/v1/hardware
- **Status ID sử dụng:** 1 (Ready to Deploy - Deployable)
- **Model ID sử dụng:** 1

## 2. Các lệnh thực thi quan trọng
- Lệnh chạy thử (Check mode):
  `ansible-playbook -i hosts.ini itam_lifecycle.yml --check`
- Lệnh chạy thật:
  `ansible-playbook -i hosts.ini itam_lifecycle.yml`

## 3. Lưu ý khi khởi động lại máy sau này
- Mỗi lần máy tính khởi động lại, IP của WSL có thể thay đổi. Nếu chạy lại bị lỗi kết nối, cần gõ lệnh `ip route show | grep default` để lấy IP mới và cập nhật lại vào mục `snipeit_url` trong file `itam_lifecycle.yml`.
- Đảm bảo Docker Desktop trên Windows đã được bật trước khi mở Ansible Semaphore hoặc Snipe-IT.
