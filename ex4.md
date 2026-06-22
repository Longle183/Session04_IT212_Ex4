# BÀI 4: Phân tích & Lựa chọn (Kỹ thuật Prompt lặp tối ưu hóa thuật toán)

## Đáp án lựa chọn: B

## Giải thích lý do lựa chọn

Phương án B là lựa chọn tối ưu nhất vì cung cấp đầy đủ thông tin kỹ thuật, chỉ rõ vấn đề hiệu năng hiện tại và đưa ra các ràng buộc cụ thể về thuật toán cần sử dụng.

Prompt này thể hiện đúng tinh thần của **Iterative Prompting**: sau khi nhận được lời giải ban đầu từ AI, người dùng phân tích hạn chế của lời giải và đưa ra yêu cầu cải tiến có căn cứ kỹ thuật.

### Các điểm mạnh của phương án B

#### 1. Chỉ rõ nguyên nhân vấn đề

Prompt nêu rõ:

> "Hàm fib đệ quy trên có độ phức tạp O(2^N), gây treo hệ thống khi n = 50."

Điều này giúp AI hiểu chính xác lý do cần tối ưu thay vì chỉ biết rằng chương trình "chạy chậm".

#### 2. Chỉ định thuật toán cần sử dụng

Prompt yêu cầu:

> "Sử dụng Dynamic Programming (Tabulation hoặc Memoization)."

AI không cần suy đoán hướng giải quyết mà tập trung vào kỹ thuật phù hợp nhất cho bài toán Fibonacci.

#### 3. Đưa ra mục tiêu hiệu năng cụ thể

Prompt yêu cầu:

* Độ phức tạp thời gian: `O(N)`
* Độ phức tạp bộ nhớ: `O(1)` hoặc `O(N)`

Đây là những tiêu chí kỹ thuật có thể kiểm chứng được, giúp phản hồi chính xác hơn.

#### 4. Giữ nguyên ràng buộc hệ thống

Prompt yêu cầu:

> "Giữ nguyên kiểu trả về long."

Điều này giúp AI tối ưu thuật toán mà không làm thay đổi giao diện của hàm hiện tại.

---

## Phân tích nhược điểm của phương án A

### Prompt A

```text
Code chạy chậm quá, viết lại bằng thuật toán khác tối ưu hơn giúp tôi.
```

### Nhược điểm

* Không nêu rõ nguyên nhân gây chậm.
* Không chỉ định thuật toán mong muốn.
* Không có yêu cầu về độ phức tạp thời gian.
* Không có yêu cầu về độ phức tạp bộ nhớ.
* Không có ràng buộc giữ nguyên kiểu dữ liệu.

### Nguy cơ

AI có thể:

* Dùng đệ quy kết hợp cache.
* Dùng vòng lặp.
* Dùng ma trận lũy thừa.
* Dùng thuật toán khác hoàn toàn.

Mặc dù có thể nhanh hơn nhưng chưa chắc đáp ứng đúng mục tiêu học tập về Dynamic Programming.

---

## Phân tích nhược điểm của phương án C

### Prompt C

```text
Hãy viết lại code tính Fibonacci bằng cách sử dụng Java Stream API để code chạy song song (parallel) cho nhanh hơn.
```

### Nhược điểm

#### 1. Giải quyết sai vấn đề gốc

Nguyên nhân chính của sự chậm chạp là:

* Thuật toán đệ quy có quá nhiều phép tính lặp lại.
* Độ phức tạp là O(2^N).

Đây là vấn đề về thuật toán, không phải vấn đề về khả năng tận dụng CPU đa luồng.

#### 2. Stream API không phù hợp

Fibonacci là bài toán có tính phụ thuộc dữ liệu:

```text
F(n) = F(n-1) + F(n-2)
```

Mỗi bước phụ thuộc kết quả bước trước nên không phù hợp với mô hình xử lý song song của Stream API.

#### 3. Có thể làm hiệu năng tệ hơn

Việc tạo và quản lý nhiều luồng:

* Tăng chi phí đồng bộ.
* Tăng chi phí lập lịch CPU.
* Không loại bỏ được các phép tính trùng lặp.

Do đó vẫn không giải quyết được bản chất của bài toán.

---

## Kết luận

**Phương án B** là lựa chọn tốt nhất vì:

* Xác định rõ nguyên nhân hiệu năng kém.
* Chỉ định chính xác kỹ thuật tối ưu (Dynamic Programming).
* Đưa ra mục tiêu độ phức tạp cụ thể (`O(N)`).
* Đặt ràng buộc kỹ thuật rõ ràng (giữ nguyên kiểu `long`).
* Thể hiện đúng kỹ thuật **Iterative Prompting**, trong đó người dùng liên tục tinh chỉnh yêu cầu dựa trên kết quả trước đó của AI để đạt được lời giải tối ưu hơn.

Vì vậy, phương án B có khả năng tạo ra phản hồi chính xác và hiệu quả nhất ngay ở lần tương tác tiếp theo với AI.
