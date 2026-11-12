---


---

<h3 id="phần-a-bảng-che-mờ-dữ-liệu-masking-table">Phần A: Bảng che mờ dữ liệu (Masking Table)</h3>
<p>Thông tin PII thật</p>
<p>Nhãn che mờ Placeholder</p>
<p>Loại dữ liệu</p>
<p>Phạm Minh C</p>
<p><code>[CUSTOMER_NAME]</code></p>
<p>Tên cá nhân</p>
<p>0988.111.222</p>
<p><code>[PHONE_NUMBER]</code></p>
<p>Số điện thoại</p>
<p><a href="mailto:minhc@gmail.com">minhc@gmail.com</a></p>
<p><code>[EMAIL_ADDRESS]</code></p>
<p>Địa chỉ thư điện tử</p>
<p>Căn hộ 502 Chung cư Sunrise, Q7</p>
<p><code>[CUSTOMER_ADDRESS]</code></p>
<p>Địa chỉ nhà ở</p>
<p>MartX District 7</p>
<p><code>[STORE_LOCATION]</code></p>
<p>Địa điểm cửa hàng</p>
<p>2kg thịt bò Wagyu</p>
<p><code>[PRODUCT_NAME]</code></p>
<p>Tên sản phẩm</p>
<p>4.500.000 VNĐ</p>
<p><code>[TRANSACTION_AMOUNT]</code></p>
<p>Số tiền giao dịch</p>
<h3 id="phần-b-văn-bản-khiếu-nại-đã-che-mờ-masked-input">Phần B: Văn bản khiếu nại đã che mờ (Masked Input)</h3>
<blockquote>
<p>“Tôi là <code>[CUSTOMER_NAME]</code> (SĐT: <code>[PHONE_NUMBER]</code>, Email: <code>[EMAIL_ADDRESS]</code>, ở <code>[CUSTOMER_ADDRESS]</code>). Ngày 20/09 tôi mua <code>[PRODUCT_NAME]</code> giá <code>[TRANSACTION_AMOUNT]</code> tại <code>[STORE_LOCATION]</code> nhưng bị giao chậm 3 tiếng làm hỏng tiệc gia đình. Tôi yêu cầu bồi thường 100%!”</p>
</blockquote>
<h3 id="phần-c-prompt-gửi-ai">Phần C: Prompt gửi AI</h3>
<p>Plaintext</p>
<pre><code>Bạn là Trưởng bộ phận Chăm sóc khách hàng của siêu thị. Dựa trên nội dung khiếu nại của khách hàng dưới đây, hãy soạn một thư xin lỗi lịch sự, chân thành, thừa nhận lỗi giao hàng chậm, đồng thời đề xuất phương án bồi thường 100% giá trị đơn hàng và tặng voucher ưu đãi cho lần mua sắm tiếp theo. Giữ nguyên các nhãn placeholder trong văn bản.

Nội dung khiếu nại:
"Tôi là [CUSTOMER_NAME] (SĐT: [PHONE_NUMBER], Email: [EMAIL_ADDRESS], ở [CUSTOMER_ADDRESS]). Ngày 20/09 tôi mua [PRODUCT_NAME] giá [TRANSACTION_AMOUNT] tại [STORE_LOCATION] nhưng bị giao chậm 3 tiếng làm hỏng tiệc gia đình. Tôi yêu cầu bồi thường 100%!"

</code></pre>
<h3 id="phần-d-văn-bản-khôi-phục-cuối-cùng-de-mask">Phần D: Văn bản khôi phục cuối cùng (De-mask)</h3>
<p>Kính gửi anh Phạm Minh C,</p>
<p>Lời đầu tiên, siêu thị MartX District 7 xin gửi lời xin lỗi chân thành và sâu sắc nhất đến anh và gia đình vì sự cố giao hàng chậm 3 tiếng trong ngày 20/09 vừa qua đối với đơn hàng 2kg thịt bò Wagyu trị giá 4.500.000 VNĐ. Chúng tôi rất tiếc khi sự chậm trễ này đã làm ảnh hưởng trực tiếp đến buổi tiệc gia đình quan trọng của anh tại Căn hộ 502 Chung cư Sunrise, Q7.</p>
<p>MartX hoàn toàn ghi nhận và tiếp thu khiếu nại của anh. Theo đúng yêu cầu, chúng tôi xin thực hiện bồi thường 100% giá trị đơn hàng (4.500.000 VNĐ) và gửi tặng anh một voucher mua sắm trị giá 500.000 VNĐ để chuộc lại thiện cảm trong những lần phục vụ tiếp theo.</p>
<p>Đội ngũ CSKH sẽ liên hệ trực tiếp qua số điện thoại 0988.111.222 hoặc email <a href="mailto:minhc@gmail.com">minhc@gmail.com</a> của anh trong thời gian sớm nhất để hoàn tất thủ tục bồi thường.</p>
<p>Trân trọng,</p>
<p>Ban Quản lý Chăm sóc Khách hàng MartX</p>

