# Báo cáo cá nhân — NguyenHoanThien-2A202603123



Dữ liệu: 12 ảnh người COCO val2017 (Lin et al., 2014) và 8 ảnh chân dung Wikimedia Commons, chỉ dùng trong lớp.

## 0. Thông tin học viên

- Họ tên: Nguyễn Hoàn Thiện
- MSSV: 2A202603123
- Email: nht270605@gmail.com
- Link repository: https://github.com/leejihoon-quant/K5-L2-NguyenHoanThien-2A202603123-KeypointPose-Student
- Phiên bản CVAT (Help → About): 2.74.1
- Máy: Windows 11 Pro · RAM 15,7 GB · chạy CVAT chế độ đầy đủ [TỰ ĐIỀN: xác nhận đầy đủ hay lite]
- Bộ ảnh (`src/exports/assignment.json`): có. File ghi đúng cấu trúc của `lab.py setup` (MSSV, bộ ảnh tính từ MSSV, id task và job); task được tạo qua giao diện CVAT trên trình duyệt, không qua lệnh `lab.py setup` (lệnh đó cần nhập mật khẩu).
- Giờ bắt đầu: 4:35pm
- Giờ kết thúc: 7:00pm

## 1. Kiểm tra label (CP0)

| Label | Kiểu | Số điểm | Tên điểm đúng bảng của lab? | Đúng thứ tự? | Số cạnh |
|---|---|---:|---|---|---:|
| `person` | Skeleton | 17 | Có | Có | 19 |
| `face` | Skeleton | 13 | Có | Có | 13 |

Mẫu `person` dựng theo người quay mặt về camera (các điểm `left_*` nằm bên phải khung mẫu)? Có (ảnh chụp 1 cho thấy `left_shoulder`, `left_elbow`, `left_wrist`, `left_hip` nằm bên phải khung mẫu).

Cách đổi cờ `occluded` / `outside` cho **một điểm** trên phiên bản CVAT này (một câu):chọn part, chọn một điểm muốn đổi, rồi nhấn O


## 2. Số lượng đã gán và thời gian (CP1, CP2)

| Nhóm ảnh | Số ảnh | Số skeleton đã gán | Số người dưới 60 px (không gán) | Số poster / gương / màn hình bỏ qua | Thời gian (phút) |
|---|---:|---:|---:|---:|---:|
| `easy` | 5 | 5 | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [TỰ ĐIỀN] |
| `occluded` | 3 | 6 | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [TỰ ĐIỀN] |
| `back` | 2 | 3 | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [TỰ ĐIỀN] |
| `small` | 1 | 3 | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [TỰ ĐIỀN] |
| `crowd` | 1 | 3 | [TỰ ĐIỀN] | [TỰ ĐIỀN] | [TỰ ĐIỀN] |
| `faces` | 8 | 8 | — | [TỰ ĐIỀN] | [TỰ ĐIỀN] |

(Số skeleton lấy từ file xuất: tổng 20 skeleton người và 8 skeleton mặt; nhóm ảnh theo bộ ảnh trong `assignment.json`.)

- Số ảnh người đã xong ở mốc phút 105: [TỰ ĐIỀN] / 10
- Thời gian thực tế (phút): CP1 [TỰ ĐIỀN] · CP2 [TỰ ĐIỀN] · CP3 [TỰ ĐIỀN]
- Ảnh tốn thời gian nhất là ảnh nào, vì sao?

[TỰ ĐIỀN]

## 3. Bảng ca khó (CP1, CP2)



Mỗi điểm bạn phân vân một dòng, nhất là phân vân giữa `v = 1` và `v = 0`, hoặc không chắc hướng người.

| Ảnh | Người / mặt | Điểm | Cờ đã chọn | Phân vân giữa | Lý do chọn |
|---|---|---|---:|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

## 4. Bảng tự review (CP3)



Đi từ ảnh cuối về ảnh đầu. 5 ảnh người (ít nhất 2 ảnh `back` hoặc `crowd`) và 3 ảnh mặt. Ít nhất 8 dòng, kể cả dòng `ok`. Ghi lỗi trước, sửa sau.

Mã lỗi dùng đúng một trong: `lr_swap`, `vis_flag`, `position`, `missing`, `extra`, `ok`.

| Ảnh | Người / mặt | Điểm | Mã lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo mã:

| `lr_swap` | `vis_flag` | `position` | `missing` | `extra` | `ok` |
|---:|---:|---:|---:|---:|---:|
| | | | | | |

Điểm còn phân vân giữa `v = 1` và `v = 0` (ghi cả hai lựa chọn và lý do chọn):

[TỰ ĐIỀN]

## 5. Kiểm file xuất và kết quả tự kiểm (CP4)

Tự kiểm trong file JSON (`annotations/person_keypoints_default.json` trong zip):

| File | Người / mặt kiểm (ảnh, thứ tự) | Số phần tử `keypoints` | Điểm `outside` ra `v = 0`, `occluded` ra `v = 1`? | `num_keypoints` khớp? |
|---|---|---:|---|---|
| `NguyenHoanThien_persons.zip` | `000000043719.jpg`, người 1 (quay lưng) | 51 | Có: mũi, 2 mắt, 2 gối, 2 cổ chân `v = 0`; 2 tai `v = 1` | Có (10 = 8 điểm `v = 2` + 2 điểm `v = 1`) |
| `NguyenHoanThien_persons.zip` | `000000122199.jpg`, annotation id 2 | 51 | Có: `right_ear` `v = 0`; `left_ear`, `right_elbow` `v = 1` | Có (16 = 14 + 2) |
| `NguyenHoanThien_faces.zip` | `face_185015.jpg`, mặt 1 | 39 | Có: `mouth_right` `v = 1` (bị ngón tay che); không có điểm `v = 0` | Có (13 = 12 + 1) |

Sau khi xuất, CVAT ghi `occluded` thành `v = 1` và `outside` thành `v = 0`. Tọa độ của điểm `outside` trong file là tọa độ cũ (ví dụ nose của người quay lưng ra `436.4, 414.1, 0`), không phải `0, 0`.

Hai job đã chuyển sang completed trên CVAT? Có (job 12 `persons`, job 13 `faces`).

Dán phần **TÓM TẮT** in ra từ `src/check_submission.py`:

```text
- File person: NguyenHoanThien_persons.zip
  Số ảnh: 12 · số skeleton `person`: 20 · mỗi annotation 51 số
  Skeleton theo ảnh: 000000043719=1, 000000122199=2, 000000164659=1, 000000177889=1, 000000179201=2, 000000269462=3, 000000311300=2, 000000311497=2, 000000343057=1, 000000381889=3, 000000463932=1, 000000493741=1
  Cờ v: v=2 223 (66%) · v=1 49 (14%) · v=0 68 (20%)
  num_keypoints trung bình: 13.6
- File face: NguyenHoanThien_faces.zip
  Số ảnh: 8 · số skeleton `face`: 8 · mỗi annotation 39 số
  Skeleton theo ảnh: face_185015=1, face_249336=1, face_256814=1, face_3348=1, face_415073=1, face_496353=1, face_560282=1, face_575921=1
  Cờ v: v=2 92 (88%) · v=1 12 (12%) · v=0 0 (0%)
  num_keypoints trung bình: 13.0
- Ghi chú: 68 điểm v = 0 vẫn mang tọa độ cũ (CVAT 2.x xuất như vậy; chuẩn COCO ghi 0, 0). Không phải lỗi: điểm v = 0 bị bỏ qua khi huấn luyện và khi chấm.
- Số [LỖI]: 0 · số [CẢNH BÁO]: 2
Kết quả: ĐẠT (đọc lại từng cảnh báo ở trên)
```

Các `[CẢNH BÁO]` của script và lý do giữ nguyên hoặc đã sửa:

- `000000122199.jpg #2`: cặp `shoulder` nằm ngược phía so với các cặp còn lại. [TỰ ĐIỀN: sau khi mở ảnh, đây là lỗi `lr_swap` đã sửa hay tay chân bắt chéo thật? Ghi lý do]
- `000000311497.jpg #1`: cặp `knee`, `ankle` nằm ngược phía. [TỰ ĐIỀN: tương tự]

## 6. Ảnh chụp màn hình

1. Label `person` trong label constructor (đủ 17 điểm có tên):

   ![Label person](images/1_label_person.png)

2. Một người quay lưng đã gán, cờ đã đặt:

   ![Người quay lưng](images/2_nguoi_quay_lung.png)

3. Một khuôn mặt đã gán 13 điểm, phóng to vùng mắt:

   ![Khuôn mặt phóng to](images/3_mat_phong_to.png)

4. Một đoạn JSON xuất của một người:

   ![JSON export](images/4_json_export.png)

Nguồn ảnh: COCO val2017 / Wikimedia Commons.

## 7. Tự đánh giá

[TỰ ĐIỀN: phải do bạn tự viết]

1. Lỗi bạn mắc nhiều nhất hôm nay, và cách bạn sẽ tránh ở dự án thật:

   [TỰ ĐIỀN]

2. Một quy tắc bạn đề xuất thêm vào guideline (kèm ảnh ví dụ nếu có):

   [TỰ ĐIỀN]

3. Nhãn của bạn đi vào model ở đâu? Chọn một lỗi bạn đã sửa và nói nó sẽ làm model học sai thế nào (heatmap, trọng số trong loss, hay bước lật ảnh):

   [TỰ ĐIỀN]

## 8. Khó khăn và lỗi kỹ thuật

[TỰ ĐIỀN: nếu không có thì ghi "Không có". Gợi ý: nếu bạn dựng task qua giao diện CVAT thay vì `lab.py setup`, ghi rõ ở đây]

## Bonus (nếu làm)

[TỰ ĐIỀN hoặc xóa cả mục này nếu không làm bonus. Hai job bonus đã tạo (`persons-extra`, `faces-extra`) và đã completed, nhưng file `NguyenHoanThien_bonus_persons.zip` và `NguyenHoanThien_bonus_faces.zip` chưa được xuất.]

## 9. Tài liệu tham khảo và công cụ AI đã dùng

[TỰ ĐIỀN: ghi công cụ AI nào, dùng vào việc gì (RULES.md yêu cầu khai báo). Ví dụ nội dung cần nêu: trợ lý AI dùng để giải thích khái niệm, tạo task trên CVAT, chạy script tự kiểm, trích tóm tắt số liệu và chụp ảnh màn hình; không dùng để sinh điểm keypoint]

- COCO Keypoints: https://cocodataset.org/#keypoints-2017
- Tài liệu lab: `docs/GUIDELINE.md`, `docs/CVAT_CHEATSHEET.md`, `docs/COCO_KEYPOINTS.md`
