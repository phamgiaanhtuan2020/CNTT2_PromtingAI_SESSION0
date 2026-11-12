---


---

<h3 id="phần-1-bản-chất-llm-–-cách-ai-đoán-từ-thay-vì-hiểu-biết">Phần 1: Bản chất LLM – Cách AI “đoán từ” thay vì “hiểu biết”</h3>
<ul>
<li>
<p><strong>Nguyên lý cốt lõi:</strong> Large Language Models (LLM) không suy nghĩ, lập luận hay có ý thức như con người. Bản chất của LLM là một mô hình thống kê dự đoán xác suất (Statistical Next-Token Prediction). Dựa trên văn bản đầu vào (prompt), mô hình tính toán từ hoặc mảnh từ (token) tiếp theo có xác suất xuất hiện cao nhất dựa trên kho dữ liệu khổng lồ mà nó được huấn luyện.</p>
</li>
<li>
<p><strong>Hệ quả cho tân sinh viên lập trình:</strong></p>
<ul>
<li>
<p>Khi bạn hỏi AI về một đoạn code, nó không thực sự “hiểu” thuật toán hay logic phía sau, mà đang ráp nối các cấu trúc mã nguồn có tần suất xuất hiện cao nhất trong các kho lưu trữ công cộng (như GitHub, StackOverflow).</p>
</li>
<li>
<p>Nếu bạn hỏi sai cú pháp, đặt câu hỏi mơ hồ hoặc sử dụng thuật ngữ sai, mô hình vẫn sẽ tiếp tục dự đoán chuỗi token tiếp theo, dẫn đến những đoạn code chạy được nhưng chứa lỗ hổng bảo mật nghiêm trọng hoặc logic sai lệch.</p>
</li>
</ul>
</li>
</ul>
<h3 id="phần-2-3-cách-nhận-diện-ảo-giác-hallucination-của-ai">Phần 2: 3 cách nhận diện “ảo giác” (Hallucination) của AI</h3>
<p>Ảo giác là hiện tượng AI tự tin bịa ra thông tin sai lệch, hàm thư viện không có thực hoặc giải thích sai bản chất kỹ thuật nhưng viết văn phong rất thuyết phục. Ba dấu hiệu nhận diện:</p>
<ol>
<li>
<p><strong>Bia đặt API, thư viện hoặc hàm không tồn tại (Ghost APIs):</strong></p>
<ul>
<li>
<p><em>Biểu hiện:</em> AI đưa cho bạn một đoạn code gọi một hàm rất tiện lợi, hoàn hảo đến mức khó tin trong một thư viện quen thuộc (ví dụ: gọi hàm <code>sortUsersByActivityScore()</code> trực tiếp từ thư viện chuẩn của Python hoặc một module phụ trợ).</p>
</li>
<li>
<p><em>Cách kiểm tra:</em> Tra cứu tài liệu chính thức (Official Documentation) của ngôn ngữ hoặc framework đó. Nếu không tìm thấy, đó là ảo giác.</p>
</li>
</ul>
</li>
<li>
<p><strong>Giải thích sai logic toán học hoặc kết quả thực thi của code:</strong></p>
<ul>
<li>
<p><em>Biểu hiện:</em> AI khẳng định đoạn code tối ưu hóa độ phức tạp thời gian từ O(n2)O(n^2)O(n2) xuống O(n)O(n)O(n) nhưng thực tế cấu trúc vòng lặp lồng nhau bên trong vẫn giữ nguyên O(n2)O(n^2)O(n2).</p>
</li>
<li>
<p><em>Cách kiểm tra:</em> Luôn chạy thử nghiệm (testing/debugging) trên môi trường cục bộ, viết unit test hoặc dùng công cụ phân tích tĩnh thay vì tin hoàn toàn vào lời giải thích của AI.</p>
</li>
</ul>
</li>
<li>
<p><strong>Sự thay đổi mâu thuẫn giữa các lần hỏi (Inconsistency):</strong></p>
<ul>
<li>
<p><em>Biểu hiện:</em> Khi bạn hỏi lại cùng một câu hỏi ở một phiên làm việc khác hoặc yêu cầu giải thích sâu hơn, AI đưa ra một kết quả khác hoàn toàn hoặc phủ nhận chính câu trả lời trước đó mà không có sự đính chính logic.</p>
</li>
<li>
<p><em>Cách kiểm tra:</em> Yêu cầu AI cung cấp nguồn tham chiếu, giải thích từng dòng lệnh chi tiết hoặc đối chiếu chéo với các nguồn uy tín khác.</p>
</li>
</ul>
</li>
</ol>
<h3 id="phần-3-cấu-trúc-prompt-mẫu-tối-ưu-bằng-khung-create">Phần 3: Cấu trúc prompt mẫu tối ưu bằng khung CREATE</h3>
<p>Khung <strong>CREATE</strong> giúp bạn kiểm soát hoàn toàn đầu ra của AI, hạn chế tối đa ảo giác và tiết kiệm token:</p>
<ul>
<li>
<p><strong>C (Character - Vai trò):</strong> Định hình chuyên môn và góc nhìn cho AI.</p>
</li>
<li>
<p><strong>R (Request - Yêu cầu chính):</strong> Nêu rõ hành động cần thực hiện.</p>
</li>
<li>
<p><strong>E (Example - Ví dụ mẫu):</strong> Cung cấp chuẩn đầu vào/đầu ra để AI định hình phong cách.</p>
</li>
<li>
<p><strong>A (Adjustment - Điều kiện/Ràng buộc):</strong> Đặt ra giới hạn kỹ thuật, phiên bản, hoặc các lỗi cần tránh.</p>
</li>
<li>
<p><strong>T (Tone - Văn phong):</strong> Quy định sắc thái diễn đạt (ngắn gọn, học thuật, thực tế).</p>
</li>
<li>
<p><strong>E (Environment/Format - Định dạng):</strong> Quy định cấu trúc trình bày kết quả (Markdown, bảng, khối mã nguồn).</p>
</li>
</ul>
<h4 id="prompt-mẫu-áp-dụng-cho-việc-viết-hàm-xử-lý-dữ-liệu">Prompt mẫu áp dụng cho việc viết hàm xử lý dữ liệu:</h4>
<p>Plaintext</p>
<pre><code>[Character]: Bạn là một kỹ sư phần mềm cao cấp, chuyên giamentor hướng dẫn sinh viên lập trình viết code sạch, tối ưu và an toàn.
[Request]: Viết một hàm tính tổng giá trị các đơn hàng hợp lệ từ một danh sách các đối tượng đơn hàng bằng ngôn ngữ Python.
[Example]: 
Đầu vào: [{'id': 1, 'amount': 150, 'status': 'completed'}, {'id': 2, 'amount': 200, 'status': 'pending'}]
Đầu ra mong đợi: 150 (chỉ tính đơn hàng có status là 'completed').
[Adjustment]: 
- Không sử dụng các hàm thư viện bên ngoài (chỉ dùng Python thuần túy).
- Phải có phần xử lý ngoại lệ (try-except) đề phòng trường hợp dữ liệu đầu vào thiếu key 'amount' hoặc 'status'.
- Chú thích (comment) giải thích ngắn gọn tại các dòng logic quan trọng.
[Tone]: Chuyên nghiệp, súc tích, mang tính định hướng sư phạm.
[Format]: Trình bày bằng một khối mã nguồn (code block) Python duy nhất, kèm theo 2-3 dòng giải thích ngắn gọn ngay bên dưới.

</code></pre>

