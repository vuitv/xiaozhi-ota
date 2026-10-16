# xiaozhi-ota — firmware phát hành của VuiTV

Repo này **chỉ chứa GitHub Releases** (file `.bin` để cập nhật qua mạng), không có mã nguồn. Release do CI của các
repo nguồn tạo khi gắn tag:

| Dòng firmware | Mã nguồn | Tag release ở đây | File |
|---|---|---|---|
| Robot | [vuitv/xiaozhi-esp32](https://github.com/vuitv/xiaozhi-esp32) | `vX.Y.Z`, `vX.Y.Z-beta.N` | `vuitv-unified-s3.bin`, `vuitv-unified-c3.bin`, `vuitv-robot.bin`, `vuitv-robot-c3.bin` |
| Camera | [vuitv/vuitv-vision](https://github.com/vuitv/vuitv-vision) | `vision-vX.Y.Z` (vd. `vision-v0.1.1`) | `vuitv-vision-s3.bin` |
| Node IR/relay | [vuitv/vuitv-node](https://github.com/vuitv/vuitv-node) | `node-vX.Y.Z` | `vuitv-node-s3.bin`, `vuitv-node-c3.bin` |

- **Robot `vX.Y.Z`** — bản chính thức, mời mọi robot (tự cài ở lần khởi động kế tiếp nếu bật *Tự động cập nhật*).
- **Robot `vX.Y.Z-beta.N`** — đăng thành **pre-release**; chỉ robot đã bật **Nhận bản beta** mới được mời.
- **Camera `vision-vX.Y.Z`** — không đánh dấu *latest* (latest của repo này dành cho firmware robot). Tiền tố `vision-`,
  `node-` để tag các dòng không đụng nhau.

Ảnh factory (flash USB lần đầu) không nằm ở đây mà ở release riêng của `vuitv/xiaozhi-esp32`.

## Ai đọc repo này

Worker OTA **https://ota.vuitv.dev** (mã nguồn [vuitv/xiaozhi-ota-server](https://github.com/vuitv/xiaozhi-ota-server))
đọc 30 release gần nhất, chọn bản mới nhất theo kênh (chính thức / beta) **có file khớp đúng** `board.type` + chip của
thiết bị, rồi trả link tải file đó.

| `board.type` | Chip | Flash | File |
|---|---|---|---|
| `vuitv-unified` | ESP32-S3 | 16 MB | `vuitv-unified-s3.bin` |
| `vuitv-unified` | ESP32-C3 | 16 MB | `vuitv-unified-c3.bin` |
| `vuitv-robot` | ESP32-S3 (N16R8) | 16 MB | `vuitv-robot.bin` |
| `vuitv-robot-c3` | ESP32-C3 | 4 MB | `vuitv-robot-c3.bin` |
| `vuitv-vision` | ESP32-S3 | ≥ 8 MB | `vuitv-vision-s3.bin` |
| `vuitv-node` | ESP32-S3 / ESP32-C3 | 16 MB / 4 MB | `vuitv-node-s3.bin` / `vuitv-node-c3.bin` |

Tạo release bằng tay thì giữ đúng tên tag và tên file ở trên — Worker khớp tên file chính xác, sai một ký tự là thiết bị
báo "không có bản mới". Cả ba dòng firmware dựng bằng ESP-IDF 6.1.

## Tài liệu

Ở repo `xiaozhi-esp32`:

- [`docs/areas/release/README.md`](https://github.com/vuitv/xiaozhi-esp32/blob/master/docs/areas/release/README.md) —
  quy trình phát hành, OTA, kênh beta.
- [`docs/STATUS.md`](https://github.com/vuitv/xiaozhi-esp32/blob/master/docs/STATUS.md) — trạng thái cả hệ thống, bản
  đang phát hành.
