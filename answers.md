### PHẦN A — KIỂM TRA ĐỌC HIỂU
### Câu A1 — HTTP & Browser
Khi truy cập https://shopee.vn:
Trình duyệt gửi DNS lookup để tìm địa chỉ IP
Thiết lập kết nối TCP với server
Thực hiện HTTPS handshake (SSL/TLS)
Gửi HTTP request đến server
Server trả về HTML
Trình duyệt parse HTML và tải CSS, JS
Render trang web
Nguồn: 01_introduction_html_universe.md (HTTP & Browser)

Tab Network: Trong Google Chrome DevTools, tab Network dùng để theo dõi toàn bộ quá trình trình duyệt tải tài nguyên của một trang web.
Cụ thể, tab Network hiển thị:


Danh sách tất cả các request gửi đi (HTML, CSS, JavaScript, hình ảnh, API…)
Status Code của từng request (ví dụ: 200, 404, 500…)
Thời gian tải của từng tài nguyên
Tổng thời gian load trang
Kích thước file
Loại tài nguyên (document, stylesheet, script…)
### Câu A2 — Semantic HTML
- Lỗi:
Dùng div thay vì header
Dùng div thay vì nav
Không dùng main
Không dùng article cho sản phẩm
Thiếu alt cho img
- Cách sửa:
Dùng header, nav, main, article, footer đúng semantic HTML5
ShopTLU
Trang chủ Sản phẩm © 2026 ShopTLU
Nguồn: Chương 04 — Semantic HTML

### Câu A3 — Block vs Inline
- Kết quả hiển thị:
Hộp 1
Text A Text B
Hộp 2
Text C Text D
Hộp 3
- Giải thích:
div là block → luôn xuống dòng
span, strong là inline → nằm cùng dòng
Nguồn: Kiến thức HTML cơ bản

### Câu A4 — Table
thead: phần tiêu đề bảng
tbody: phần nội dung chính
tfoot: phần cuối bảng
- Không nên dùng table để layout vì:
Khó responsive
Code khó đọc và bảo trì
Không đúng semantic
Nguồn: Chương 05 — Table

### PHẦN B
### Bài B3 — Debug HTML
Lỗi 1: Dòng 1 — Thiếu khai báo đầy đủ DOCTYPE — Sửa thành

Lỗi 2: Dòng 2 — Thẻ thiếu thuộc tính lang — Sửa thành

Lỗi 3: Dòng 4 — Thẻ <title> chưa đóng — Thêm </title>

Lỗi 4: Dòng 5 — Sai charset "utf8" — Sửa thành "UTF-8"

Lỗi 5: Dòng 8 — Thẻ

chưa đóng đúng — Sửa thành
Lỗi 6: Dòng 12 — Thẻ chưa đóng — Thêm

Lỗi 7: Dòng 18 — Thẻ  thiếu dấu ngoặc kép và thuộc tính alt — Sửa thành src="iphone.jpg" alt="iPhone"

Lỗi 8: Dòng 20 — Sai thứ tự đóng thẻ và

— Sửa lại đúng nesting:

Giá: ...

Lỗi 9: Dòng 25 — Bảng thiếu và — Thêm cấu trúc chuẩn cho table

Lỗi 10: Dòng 26 — Dùng cho tiêu đề — Sửa thành

Lỗi 11: Dòng 36 — Có 2 thẻ

— Đổi thẻ thứ hai thành
Lỗi 12: Dòng 41 — Thẻ

trong footer chưa đóng — Thêm

### BÀI B4 - PHÂN TÍCH TRANG WEB THẬT
Sau khi inspect trang thegioididong.com: 3 thẻ semantic mà trang sử dụng

Vị trí: Phần đầu trang Chức năng: Chứa logo, thanh tìm kiếm, menu Ý nghĩa: Xác định khu vực giới thiệu và điều hướng chính 2.

Vị trí: Bên trong header Chức năng: Chứa danh mục (Điện thoại, Laptop, …) Ý nghĩa: Xác định khu vực điều hướng 3. Vị trí: Bao quanh nội dung chính Chức năng: Hiển thị sản phẩm, banner Ý nghĩa: Nội dung chính của trang
Các lỗi chưa dùng semantic tốt

Lạm dụng
Các khối sản phẩm dùng
thay vì:
(nhóm nội dung) (nội dung độc lập) 2. Thiếu heading chuẩn (
,
) Một số tiêu đề dùng
hoặc Làm giảm khả năng hiểu nội dung của Google ** PHÂN TÍCH TABLE -Nội dung bảng: Bảng hiển thị thông số kỹ thuật sản phẩm (ví dụ: màn hình, RAM, pin…) -Cấu trúc bảng: Có sử dụng: Không có hoặc chưa rõ:
### PHẦN C - SUY LUẬN
### CÂU C1: THIẾT KẾ CẤU TRÚC
<title>Chi tiết sản phẩm</title>
<!-- HEADER: dùng header vì là phần đầu trang chứa logo + điều hướng -->
<header>
    <h1>Shop</h1> <!-- h1 cho tiêu đề chính toàn trang -->

    <!-- NAV: điều hướng chính của website -->
    <nav>
        <ul> <!-- ul vì menu là danh sách -->
            <li><a href="/">Trang chủ</a></li>
            <li><a href="/dien-thoai">Điện thoại</a></li>
            <li><a href="/phu-kien">Phụ kiện</a></li>
        </ul>
    </nav>
</header>

<!-- MAIN: nội dung chính của trang -->
<main>

    <!-- BREADCRUMB -->
    <nav aria-label="breadcrumb"> <!-- nav vì là điều hướng -->
        <ol> <!-- ol vì breadcrumb có thứ tự -->
            <li><a href="/">Trang chủ</a></li>
            <li><a href="/dien-thoai">Điện thoại</a></li>
            <li>iPhone 16</li>
        </ol>
    </nav>

    <!-- SECTION: nhóm nội dung chính sản phẩm -->
    <section class="product-detail">

        <!-- ARTICLE: 1 sản phẩm là nội dung độc lập -->
        <article>

            <!-- HÌNH ẢNH SẢN PHẨM -->
            <section class="product-images"> <!-- section vì là 1 nhóm nội dung -->
                <figure> <!-- figure cho nội dung media -->
                    <img src="img1.jpg" alt="Ảnh sản phẩm 1">
                </figure>
                <figure>
                    <img src="img2.jpg" alt="Ảnh sản phẩm 2">
                </figure>
                <figure>
                    <img src="img3.jpg" alt="Ảnh sản phẩm 3">
                </figure>
                <figure>
                    <img src="img4.jpg" alt="Ảnh sản phẩm 4">
                </figure>
                <figure>
                    <img src="img5.jpg" alt="Ảnh sản phẩm 5">
                </figure>
            </section>

            <!-- THÔNG TIN SẢN PHẨM -->
            <section class="product-info">
                <h2>Tên sản phẩm</h2> <!-- h2 vì là tiêu đề của article -->

                <p class="price">Giá</p> <!-- p cho text thông thường -->

                <!-- ĐÁNH GIÁ -->
                <div class="rating"> <!-- div vì không có semantic riêng -->
                    <span>★★★★★</span>
                </div>

                <!-- MÔ TẢ -->
                <section class="description"> <!-- section cho nội dung mô tả -->
                    <h3>Mô tả</h3>
                    <p>Nội dung mô tả sản phẩm</p>
                </section>
            </section>

            <!-- BẢNG THÔNG SỐ -->
            <section class="specs">
                <h3>Thông số kỹ thuật</h3>

                <table> <!-- table vì dữ liệu dạng bảng -->
                    <thead> <!-- thead cho tiêu đề bảng -->
                        <tr>
                            <th>Thuộc tính</th>
                            <th>Giá trị</th>
                        </tr>
                    </thead>
                    <tbody> <!-- tbody cho nội dung -->
                        <tr>
                            <td>RAM</td>
                            <td>8GB</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <!-- ĐÁNH GIÁ / BÌNH LUẬN -->
            <section class="reviews">
                <h3>Đánh giá</h3>

                <article class="review"> <!-- mỗi review là 1 nội dung độc lập -->
                    <p>Người dùng A: Sản phẩm tốt</p>
                </article>
            </section>

        </article>
    </section>

    <!-- SIDEBAR -->
    <aside> <!-- aside vì là nội dung phụ -->
        <h3>Sản phẩm tương tự</h3>

        <ul> <!-- danh sách sản phẩm -->
            <li><a href="#">Sản phẩm 1</a></li>
            <li><a href="#">Sản phẩm 2</a></li>
        </ul>
    </aside>

</main>

<!-- FOOTER -->
<footer> <!-- footer cho phần cuối trang -->
    <p>© 2026 Shop</p>
</footer>

### CÂU 2: SO SÁNH VÀ TRANH LUẬN
Tôi không đồng ý với ý kiến “dùng <div> cho mọi thứ là đủ”, vì về lâu dài sẽ gây nhiều vấn đề. Thứ nhất là về SEO. Các công cụ tìm kiếm không chỉ đọc chữ mà còn dựa vào cấu trúc HTML để hiểu nội dung. Khi dùng các thẻ semantic như <header>, <nav>, <main>, <article>, Google sẽ dễ nhận ra đâu là phần chính, đâu là menu hay nội dung phụ. Nếu tất cả đều là <div> thì cấu trúc bị mờ, bot khó phân tích, dẫn đến việc đánh giá trang kém hơn.
Thứ hai là về accessibility. Người dùng sử dụng screen reader cần các thẻ semantic để điều hướng nhanh. Ví dụ họ có thể chuyển thẳng đến <nav> hoặc bỏ qua header để vào <main>. Nếu chỉ dùng <div>, screen reader sẽ đọc tuần tự từ trên xuống, rất khó sử dụng và không thân thiện.
Một ví dụ cụ thể là trang sản phẩm. Nếu mỗi sản phẩm được bọc trong <article>, có tiêu đề <h2>, mô tả <p>, thì cả Google và các công cụ hỗ trợ đều hiểu đây là một nội dung độc lập. Điều này giúp SEO tốt hơn và cải thiện trải nghiệm người dùng, so với việc chỉ dùng <div class="product">.
Tuy vậy, <div> vẫn có chỗ dùng hợp lý. Ví dụ khi tạo layout bằng CSS (flexbox, grid) hoặc làm container để nhóm các phần tử không mang ý nghĩa nội dung rõ ràng, thì dùng <div> là hoàn toàn bình thường.
Nói chung, semantic HTML không phải là “học cho có”, mà giúp code rõ ràng hơn, dễ bảo trì và thân thiện hơn với cả máy lẫn người dùng.