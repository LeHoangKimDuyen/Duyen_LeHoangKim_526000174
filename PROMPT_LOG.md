# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Lê Hoàng Kim Duyên
- **MSSV:** 526000174
- **Tên đề tài Website:** Book Landing Page - 5 Tác Phẩm Trinh Thám Kinh Điển Nhất Của Agatha Christie
- **Công cụ AI đã sử dụng:** Gemini (Google Deepmind)

## 1. Yêu cầu ban đầu (System/Initial Prompt)
> Bạn là một Senior Frontend Developer chuyên về thiết kế web UI/UX. Nhiệm vụ của bạn là tạo mã nguồn đầy đủ cho một trang web giới thiệu sách (Book Landing Page) có chủ đề: "5 Tác Phẩm Trinh Thám Kinh Điển Nhất Của Agatha Christie". Trang web này được sử dụng làm bài kiểm tra giữa kỳ, do đó mã nguồn phải đạt chuẩn tối đa về Semantic HTML5, CSS Variables, Flexbox/Grid layout, hiệu ứng thư viện (Animate.css, AOS) và chuẩn bị sẵn cho Responsive. Ghi vào file index.html và style.css, chỉ sử dụng HTML và CSS. Yêu cầu hiển thị 5 tác phẩm với ảnh Unsplash, 5 section riêng biệt, và setup biến CSS :root.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Layout cơ bản
- **Prompt đã dùng:** Yêu cầu khởi tạo trang web ban đầu gồm `<header>`, `<nav>`, `<main>`, 5 thẻ `<section>` cho 5 cuốn sách, và `<footer>`. Kết hợp việc sử dụng Flexbox cho thanh điều hướng và Grid (2 cột) cho các thẻ sách, đồng thời có hiệu ứng xen kẽ đảo ngược lưới trên các thẻ chẵn để giao diện không bị nhàm chán.
- **Kết quả AI tạo ra:** AI đã tạo chính xác khung trang, sử dụng Semantic HTML5 chuẩn xác (`<article>` bên trong `<section>`), cấu hình biến CSS (Variables) đầy đủ và xây dựng lưới Grid responsive.
- **Nhận xét & Tinh chỉnh của SV:** AI đã xử lý rất tốt việc gán id cho từng section (`#book1` -> `#book5`) và kết nối tính năng cuộn mượt (smooth scroll) thành công. Giao diện chuẩn UI/UX và responsive khi co nhỏ màn hình dưới 768px.

### Lần 2: Bổ sung Hero Section về tác giả Agatha Christie và tinh chỉnh hiệu ứng Animate.css, AOS
- **Prompt đã dùng:** "Hãy điều chỉnh cấu trúc trang web để bổ sung `<section id="about-author">` nằm ở VỊ TRÍ TRÊN CÙNG... Section này đóng vai trò là Hero Section chính... Sử dụng Grid/Flexbox chia 2 cột... thêm Khối Thống kê dạng thẻ (Stats Cards) với các chỉ số ấn tượng... Tối ưu giao diện, viết hiệu ứng :hover cho các Stats Cards... Áp dụng Animate.css cho tiêu đề và data-aos="fade-down" cho toàn bộ Hero Section."
- **Thách thức gặp phải:** Khi bổ sung một khối mới toanh vào thiết kế, layout có thể bị phá vỡ hoặc màu sắc không đồng bộ với biến CSS sẵn có. Ngoài ra, việc áp dụng hiệu ứng hover kết hợp với Animation khi tải trang cần được xử lý khéo léo để không gây chói mắt.
- **Cách sửa prompt (Debug prompt):** Yêu cầu AI đặt cụ thể khối `<section id="about-author">` vào ngay dưới thẻ mở `<main>`. Giao phó rõ yêu cầu về cách chia flexbox cho khối thông số (`.stats-container`) và bắt buộc tái sử dụng lại các biến CSS `:root` (`--primary-color`, `--accent-color`, `--card-bg`) thay vì viết mã màu cứng. Yêu cầu rõ hiệu ứng bóng đổ (box-shadow) và trượt lên (transform) khi hover.

## 3. Đánh giá cá nhân về quá trình Vibe Coding
- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**
  AI đã giúp tiết kiệm 80% thời gian gõ các đoạn code boilerplate (các thẻ HTML lặp đi lặp lại), cũng như setup cấu trúc ban đầu của CSS Variables và bố cục CSS Grid/Flexbox. Đặc biệt là việc tự động tìm và chèn các liên kết thư viện (CDN cho Animate.css, AOS) và placeholder image (Unsplash) nhanh chóng.
- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?**
  Cần đóng vai và định hình ngữ cảnh rõ ràng (ví dụ: "Bạn là Senior Frontend Developer..."). Việc chỉ định kỹ thuật cụ thể (Semantic HTML5, CSS Grid, Flexbox, Variable) giúp AI không sinh ra các giải pháp cũ kỹ (như xài quá nhiều thẻ `div` hay dùng float). Ngoài ra, khi yêu cầu sửa lỗi hay thêm chức năng, cần chỉ rõ "vị trí tương đối" (chèn trước thẻ nào, sau thẻ nào) và quy định rõ class name để AI tuân thủ theo luồng tư duy của mình.
