<div align="center">

<h1 align="center">📘 Mạch Loa OTL Vi Sai - Đồ án PBL2</h1>

 *Một nơi lưu trữ mồ hôi nước mắt sau những đêm "cày cuốc" chạy mô phỏng, đóng gói cẩn thận để sau này lôi ra ngắm cho bõ công!* 😆

<p>
  <img src="https://img.shields.io/badge/repo%20size-1.5%20MB-blue" alt="Repo Size">
  <img src="https://img.shields.io/badge/last%20commit-September-green" alt="Last Commit">
  <img src="https://img.shields.io/badge/Focus-Analog_Circuit-red" alt="Focus">
</p>

<p>⚙️ <b>Analog</b> &bull; 💻 <b>Simulation</b> &bull; 🎧 <b>Audio Amplifier</b></p>

</div>

👉 *Từ những dòng bias (phân cực) cơ bản nhất — đến khi sóng âm khuếch đại mượt mà không bị "cắt ngọn"* 

👋 **Chào bạn,**

Mình là **Nguyễn Đức Ngân** (thành viên lớp 24DT4). Hiện tại, mình đang là sinh viên năm 2 "hệ cày cuốc" thuộc chuyên ngành Điện tử - Viễn thông tại Đại học Bách Khoa - Đại học Đà Nẵng (DUT). 

Với niềm đam mê đặc biệt dành cho các bộ môn điện tử tương tự (**Analog**), mình rất thích việc tính toán linh kiện, căn chỉnh mạch và ngồi soi từng gợn sóng trên máy hiện sóng (Oscilloscope). 

Mình tạo repo này nhằm mục đích đóng gói toàn bộ tài liệu, bản vẽ Proteus và thông số kỹ thuật của đồ án PBL2. Nói một cách thực tế thì đây là nơi mình sao lưu lại một cột mốc học tập, để thỉnh thoảng rảnh rỗi lôi ra "ngắm" lại thành quả thiết kế phần cứng của chính mình .

---
# 🎧 Đồ án PBL2: Thiết kế và Mô phỏng Mạch Loa OTL Vi Sai

Kho lưu trữ này chứa các tệp thiết kế và mô phỏng Proteus cho Đồ án Thiết kế mạch khuếch đại âm tần OTL (Output Transformer Less) với đầu vào là tầng vi sai, thuộc chương trình đào tạo ngành Điện tử - Viễn thông, Trường Đại học Bách Khoa - Đại học Đà Nẵng.

## 👨‍💻 Thông tin thực hiện
* **Thành viên nhóm:** 
  * Nguyễn Đức Ngân (MSSV: 106240186)
  * Trần Nguyễn Hoàng Bách (MSSV: 106240161)
* **Giảng viên hướng dẫn:** TS. Huỳnh Thanh Tùng & ThS. Vũ Vân Thanh

---

## 🎯 Chỉ tiêu kỹ thuật (Specifications)
Mạch được thiết kế và tinh chỉnh để đáp ứng các tiêu chí đầu ra như sau:

| Thông số | Giá trị |
| :--- | :--- |
| **Công suất ra loa (Pout)** | 15W |
| **Trở kháng tải (Speaker)** | 4Ω |
| **Trở kháng ngõ vào (Zin)** | 220kΩ |
| **Điện áp ngõ vào (Vin)** | 0.7V |
| **Băng thông (Bandwidth)** | 50Hz - 15000Hz |
| **Méo phi tuyến (THD)** | 0.3% |

---

## 📂 Cấu trúc Repository
Dự án sử dụng phần mềm **Proteus 8.16** để mô phỏng. Dưới đây là chức năng của từng file `.pdsprj`:

* 📄 `OTL_Visai_Ok.pdsprj`: **[Bản chính]** File mô phỏng tổng thể toàn mạch OTL vi sai hoàn chỉnh. 
* 📄 `OTL_Visai_TungTang.pdsprj`: Bản bóc tách, dùng để đo đạc và kiểm tra hoạt động của từng tầng khuếch đại riêng biệt.
* 📄 `Bandwitch_OTL_Visai_ok.pdsprj`: File chuyên dụng thiết lập sẵn các máy phát để đo đạc và vẽ biểu đồ Bode đáp ứng tần số (Băng thông).

---

## 🖥️ Sơ đồ nguyên lý toàn mạch (Schematic)**

*<img width="1631" height="897" alt="image" src="https://github.com/user-attachments/assets/e480a758-46e1-4c92-902a-c7e079e47ff0" />*

> 💡 **Cấu trúc & Nguyên lý hoạt động:**
> Sơ đồ trên thể hiện kiến trúc hoàn chỉnh của mạch khuếch đại, được thiết kế theo 3 khối chức năng chuyên biệt:
> 
> * **Tầng đầu vào (Vi sai):** Sử dụng cặp BJT ghép vi sai giúp triệt tiêu nhiễu đồng pha hiệu quả và giữ ổn định điểm làm việc tĩnh (Q-point) khi nhiệt độ môi trường thay đổi.
> * **Tầng khuếch đại điện áp (Thúc):** Có nhiệm vụ khuếch đại biên độ tín hiệu lên mức đủ lớn để kích dẫn tầng công suất phía sau.
> * **Tầng công suất OTL:** Hoạt động ở chế độ đẩy kéo (Push-Pull). Tín hiệu được xuất âm qua tụ hóa ngõ ra dung lượng lớn để chặn thành phần dòng một chiều (DC), bảo vệ an toàn tuyệt đối cho loa tải 4Ω.
>
> Toàn bộ giá trị linh kiện (điện trở phân cực, tụ thoát, biến trở vi chỉnh) đều được tính toán và tinh chỉnh trên Proteus để mạch đạt công suất 15W với độ méo phi tuyến (THD) bám sát yêu cầu < 0.3%.
---

## 📊 Đánh giá kết quả mô phỏng

**1. Đáp ứng miền thời gian (Time Domain)**

*<img width="1372" height="836" alt="image" src="https://github.com/user-attachments/assets/5b948cda-9ba0-475a-93e3-7b7664b5a855" />*

> 💡 **Phân tích Oscilloscope:** 
> Hình ảnh trích xuất từ máy hiện sóng cho thấy tín hiệu ngõ ra (đường màu xanh) đã được khuếch đại biên độ chuẩn xác so với tín hiệu ngõ vào (đường màu vàng). Sóng âm duy trì độ mượt mà, không xảy ra hiện tượng cắt ngọn (clipping) ở các đỉnh dốc. 
> 
> Điều này minh chứng cho việc tầng vi sai đã triệt tiêu nhiễu đồng pha rất tốt, đồng thời các tụ thoát và phân cực tầng công suất OTL đang hoạt động đúng điểm làm việc tối ưu.

<br>

**2. Đáp ứng miền tần số (Frequency Domain)**

*<img width="1909" height="927" alt="image" src="https://github.com/user-attachments/assets/10962ade-79eb-4333-a162-26be796a357c" />*

> 💡 **Phân tích đồ thị Bode:**
> Biểu đồ Bode phía trên thể hiện rõ băng thông hoạt động của toàn mạch. Đường đặc tuyến độ lợi (Gain) duy trì sự ổn định tuyệt đối ở phần dải giữa. Các tần số cắt dưới và cắt trên hoàn toàn bao phủ và vượt mức yêu cầu thiết kế ban đầu (50Hz - 15kHz). 
> 
> Kết quả này khẳng định việc tính toán thông số tụ nối tầng, tụ lọc và linh kiện toàn mạch đã đạt độ chính xác cao, đảm bảo tín hiệu truyền ra loa giữ được cả dải âm bass và treble một cách trung thực nhất.

---

## 🔌 Danh sách linh kiện chủ chốt
Dựa trên bảng tính toán thiết kế, mạch sử dụng hệ thống linh kiện thực tế bao gồm:

* **Transistor Công suất:** cặp BJT `2SD718` (NPN) & `2SB688` (PNP).
* **Transistor Thúc (Driver):** `TIP41C`, `TIP42C`.
* **Transistor Tiền khuếch đại & Vi sai:** `2SA1085`, `2SA1015`, `2SC1815`, `2SA1013`, `BD139`.
* **Diode phân cực:** `1N4007`, `1N4148`.
* **Tụ điện:** Tụ nối tầng, tụ thoát tín hiệu xoay chiều, tụ lọc nguồn đa dạng (từ `150pF` đến `10000uF`).
* **Điện trở / Biến trở:** Trở công suất `0.22Ω/5W`, `220Ω/2W` và các biến trở vi chỉnh `200Ω`, `500Ω`, `30kΩ` định thiên dòng tĩnh.

---

## 🚀 Hướng dẫn sử dụng
1. Tải toàn bộ mã nguồn về máy tính.
2. Mở các file bằng **Proteus Professional phiên bản 8.16** trở lên để tránh lỗi tương thích thư viện.
3. Bấm **Play** góc dưới bên trái màn hình Proteus để xem hoạt động. Có thể mở công cụ *Oscilloscope* để xem trực tiếp dạng sóng ngõ vào/ra.
