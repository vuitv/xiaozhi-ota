# VuiTV Robot OTA — Firmware Releases

Repository chứa firmware binary releases cho **VuiTV Robot** (ESP32-S3 N16R8).

## Download

Vào tab **[Releases](../../releases)** để tải firmware mới nhất.

## Cách dùng

Firmware được tự động kiểm tra và cập nhật qua OTA Server:
- **OTA Server**: https://vuitv-robot-ota.vuitv.workers.dev
- **API Docs**: https://vuitv-robot-ota.vuitv.workers.dev/docs

## Board Info

| Thông số | Giá trị |
|----------|---------|
| **MCU** | ESP32-S3 N16R8 |
| **Display** | OLED SSD1306 128×64 |
| **Audio** | INMP441 + MAX98357A |
| **Motor** | DRV8833 (2x DC Motor) |
| **Framework** | ESP-IDF v5.5.3 |

## Naming Convention

Firmware binary: `vuitv-robot.bin`  
Pattern: `vuitv-robot-v{version}.bin` (optional)
