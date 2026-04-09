# Hoang Hiep - 2A202600065

**1. Role cụ thể trong nhóm**
* **Product Manager (PM) & Full-stack / AI Integrator:** Đóng vai trò là người định hướng tầm nhìn sản phẩm, lên kế hoạch tiến độ (roadmap) trong đồng thời trực tiếp tham gia lập trình và kết nối các thành phần hệ thống để đảm bảo luồng demo chạy thông suốt.

**2. Phần phụ trách cụ thể (Outputs)**
* **Phát triển Frontend:** Xây dựng thành công giao diện tương tác trên nền tảng Web, tạo ra 2 luồng trải nghiệm rõ rệt cho Giáo viên (Upload & Review) và Học sinh (Interactive Video Player).
* **Tích hợp AI Core:** Chịu trách nhiệm cầu nối (Bridge), nhận dữ liệu JSON từ bộ phận AI để móc nối vào logic điều khiển Frontend (xử lý logic video tự động dừng tại đúng timestamp và gọi API đánh giá câu trả lời).
* **Nội dung Pitching:** Lên khung kịch bản thuyết trình, thiết kế slide và chuẩn bị nội dung demo sắc nét, tập trung đánh mạnh vào nỗi đau giáo dục thụ động và giải pháp AI an toàn.

**3. SPEC phần nào mạnh nhất, phần nào yếu nhất? Vì sao?**
* **Mạnh nhất - User Stories & Failure Modes:** Phần này được định nghĩa cực kỳ chặt chẽ. Việc lường trước các rủi ro nguy hiểm (như AI Chatbot bịa sự thật lịch sử) và đưa ra luồng "Low-confidence/Correction" (Học sinh báo lỗi, Giáo viên duyệt) đã giúp giải pháp trở nên thực tế và an toàn cho môi trường giáo dục.
* **Yếu nhất - ROI & Kịch bản tài chính:** Trong khuôn khổ thời gian ngắn, các con số giả định về tỷ lệ giữ chân (retention) hay hiệu suất giảm tải giờ làm cho giáo viên chỉ dừng ở mức ước lượng lý thuyết (educated guess). Việc thiếu data thực tế từ người dùng để back-up khiến phần chứng minh tính khả thi về mặt kinh tế chưa thực sự chắc chắn.

**4. Đóng góp cụ thể khác**
* **Technology Advisor:** Đưa ra các gợi ý về Tech Stack tối ưu thời gian (sử dụng các công cụ/framework phù hợp) cho các thành viên khác để bắt kịp deadline 3 tiếng.
* **Code Reviewer (AI-Gen):** Khởi xướng và dẫn dắt cả nhóm thực hiện review chéo (cross-review) các đoạn code do AI sinh ra, thay vì copy-paste mù quáng, đảm bảo hệ thống không bị sập vì lỗi logic ẩn.

**5. 1 điều học được trong hackathon mà trước đó chưa biết**
* Nắm bắt sâu hơn về kỹ thuật ép kiểu dữ liệu (Structured Output) khi làm việc với LLM. Cụ thể là cách thiết lập prompt và pipeline để AI luôn trả về định dạng JSON chuẩn xác tuyệt đối, phục vụ cho việc điều khiển các thành phần UI phức tạp (như trình phát video) thay vì chỉ sinh ra văn bản thuần túy. Học thêm được cách ứng dụng thực tế của một số mô hình nền tảng mới trong quá trình làm RAG.

**6. Nếu làm lại, đổi gì?**
* **Data cho RAG:** Thay vì chỉ dựa vào transcript của video, sẽ chủ động viết script crawl thêm dữ liệu nền tảng (sách giáo khoa, tài liệu lịch sử chuẩn) để nạp vào Vector Database. Điều này sẽ giúp Chatbot không chỉ trả lời quanh quẩn trong video mà có độ sâu kiến thức tốt hơn.
* **Quản trị rủi ro API:** Sẽ nạp sẵn tiền (Top-up credit) và thiết lập nhiều API Key dự phòng để tuyệt đối tránh tình trạng bị Rate Limit (giới hạn lượt gọi) dẫn đến "chết lâm sàng" đúng khoảnh khắc đứng trên sân khấu Demo.

**7. Đánh giá việc sử dụng AI (Pros & Cons)**
* **Mặt tích cực (Giúp ích):** AI đóng vai trò như một co-pilot xuất sắc trong việc viết mã nguồn Frontend và dựng khung ứng dụng (boilerplate) với tốc độ 10x. Nó giúp team tiết kiệm hàng giờ gõ code thủ công để dựng UI.
* **Mặt tiêu cực (Sai/Mislead):** AI thường xuyên bị ảo giác trong việc quản lý trạng thái (State Management) hoặc bịa ra các hàm thư viện không tồn tại. Lúc đầu, code sinh ra bị lỗi logic đứt luồng liên tục. Để khắc phục, nhóm phải ngồi lại đọc hiểu code, sửa lại cấu trúc System Prompt, cung cấp SPEC kỹ thuật và ranh giới rõ ràng hơn thì AI mới gen ra code chạy ổn định.
