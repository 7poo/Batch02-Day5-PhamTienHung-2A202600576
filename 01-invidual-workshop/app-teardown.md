# Workshop - Mổ App AI Thật

**Sản phẩm chọn:** MoMo - Moni
**AI feature:** Trợ lý tài chính cá nhân, hỏi đáp và gợi ý quản lý chi tiêu
**Người dùng quan sát:** Người dùng MoMo có nhu cầu theo dõi chi tiêu, tiết kiệm tiền, hiểu dòng tiền cá nhân
**Output:** Finding note + sketch `as-is / to-be`

## 1. Lý do chọn Moni của MoMo

Moni được đặt trong MoMo, một ứng dụng có nhiều giao dịch tài chính hằng ngày như chuyển tiền, thanh toán hóa đơn, nạp điện thoại, mua vé, thanh toán dịch vụ. Vì vậy, kỳ vọng từ phía người dùng là Moni không chỉ là chatbot trả lời chung chung, mà có thể trở thành một trợ lý tài chính cá nhân thật sự.

Với người dùng bình thường, bài toán quan trọng không phải là "AI có nói hay không", mà là:

- Tôi đã tiêu tiền vào đâu?
- Tháng này có bất thường gì không?
- Khoản nào nên cắt giảm?
- Tôi có đang vượt ngân sách không?
- Nếu tôi hỏi tiếp, AI có nhớ câu hỏi trước để tiếp tục phân tích không?

## 2. Promise vs Reality

### Product hứa gì?

Moni tạo cảm giác như một trợ lý tài chính cá nhân trong MoMo. Lời hứa chính là giúp người dùng hiểu hơn về chi tiêu, quản lý tiền tốt hơn, và nhận gợi ý tài chính nhanh bằng cách chat tự nhiên.

### User nào được hứa sẽ được giúp?

User chính là người dùng MoMo hằng ngày, đặc biệt là người trẻ, sinh viên, nhân viên văn phòng hoặc người có thu nhập hằng tháng nhưng chưa có thói quen ghi chép tài chính.

### Kỳ vọng AI làm được task nào?

Khi sử dụng Moni, tôi kỳ vọng AI có thể:

- Tổng hợp các khoản chi trong MoMo theo tháng.
- Phân loại chi tiêu thành ăn uống, di chuyển, mua sắm, hóa đơn, giải trí.
- Trả lời các câu hỏi cá nhân hóa như "tháng này tôi tiêu nhiều nhất vào đâu?".
- Nhớ ngữ cảnh hỏi đáp ngắn hạn để tiếp tục phân tích.
- Nếu không có dữ liệu, AI cần nói rõ hạn chế và hướng dẫn cách kết nối/nhập thêm thông tin.

### Khi dùng thật, điểm gãy xuất hiện ở đâu?

Điểm gãy lớn nhất là Moni có dáng của một trợ lý tài chính, nhưng lại chưa thật sự nắm được bức tranh tài chính cá nhân của người dùng. Nếu AI không truy cập được lịch sử giao dịch, ngân sách, thu nhập, hoặc danh mục chi tiêu của tôi, câu trả lời dễ bị chung chung.

Điểm gãy thứ hai là context ngắn. Khi hỏi tiếp sau một câu hỏi trước, Moni có thể không giữ được ngữ cảnh, làm người dùng phải nhắc lại từ đầu. Điều này làm trải nghiệm trợ lý bị đứt mạch, giống như đang hỏi một bot hỏi đáp riêng lẻ hơn là một người cùng phân tích tài chính cá nhân.

## 3. Evidence / Observation

> Lưu ý: phần evidence này dựa trên self-use và quan sát workflow. Nếu nộp bản cuối, có thể chèn thêm screenshot màn hình chat Moni vào mục này.

| Observation | Prompt/input đã thử | Path liên quan | Điều học được |
|---|---|---|---|
| Moni có thể trả lời theo hướng tư vấn tài chính chung, nhưng chưa cho thấy đang nắm được thông tin tài chính cá nhân của tôi. | "Tháng này tôi tiêu nhiều nhất vào đâu?" | Failure / Low-confidence | AI cần biết khi nào mình thiếu data và cần hỏi xin quyền, xin thêm thông tin, hoặc nói rõ không thể kết luận. |
| Khi hỏi tiếp một câu ngắn dựa trên câu trước, Moni dễ mất ngữ cảnh và yêu cầu người dùng hỏi lại rõ hơn. | Câu 1: "Tôi muốn tiết kiệm tiền tháng này." Câu 2: "Vậy nên cắt khoản nào trước?" | Correction / Failure | Trợ lý tài chính cần có session memory ngắn hạn để tiếp tục phân tích cùng một mục tiêu. |
| Câu trả lời nếu không gắn với số liệu cá nhân sẽ khó tạo niềm tin. | "Lập cho tôi kế hoạch chi tiêu từ nay đến cuối tháng." | Low-confidence | Với bài toán tài chính, độ tin cậy đến từ dữ liệu và cách AI giải thích hạn chế của mình. |

## 4. Four Paths

| Path | Hiện tại quan sát được | Vấn đề | Đề xuất |
|---|---|---|---|
| Happy | Khi hỏi câu chung như "làm sao để tiết kiệm tiền?", Moni có thể đưa lời khuyên tổng quát. | Câu trả lời có ích ở mức kiến thức chung, nhưng chưa cá nhân hóa. | Thêm chế độ "phân tích trên dữ liệu của tôi" nếu user cho phép truy cập giao dịch. |
| Low-confidence | Khi thiếu dữ liệu, Moni chưa luôn nói rõ "tôi không có dữ liệu chi tiêu của bạn". | User có thể tưởng AI đã phân tích tài chính cá nhân, trong khi thực ra AI đang trả lời chung. | Hiện thông báo thiếu data, hỏi user có muốn kết nối lịch sử giao dịch/nhập ngân sách không. |
| Failure | User hỏi "tháng này tôi tiêu nhiều nhất vào đâu?" nhưng AI không có dữ liệu để tính. | Lỗi nằm ở data-tool layer: AI không có công cụ truy vấn dữ liệu cá nhân hoặc không nói rõ mình không có quyền truy cập. | Tạo fallback: "Mình chưa có dữ liệu giao dịch của bạn. Bạn có thể chọn: xem giao dịch MoMo, nhập thu nhập, tạo ngân sách." |
| Correction | User hỏi tiếp "vậy cắt khoản nào trước?" nhưng AI không nhớ ngữ cảnh câu trước. | Lỗi nằm ở context/memory và UX recovery. User phải nhắc lại từ đầu. | Lưu session context theo chủ đề trong một phiên chat, tóm tắt mục tiêu tài chính hiện tại và cho user sửa/xác nhận. |

## 5. Finding chính

Khi user hỏi Moni về tình hình chi tiêu cá nhân, AI/product trả lời theo hướng tư vấn chung vì chưa nắm được dữ liệu tài chính của user hoặc chưa nói rõ mình không có dữ liệu. Hậu quả là user khó tin vào kết quả, không biết mình nên hành động dựa trên số liệu nào, và cảm thấy Moni giống chatbot hỏi đáp hơn là trợ lý tài chính cá nhân.

Lỗi thuộc layer **data-tool + UX recovery**. Nên sửa bằng cách thêm low-confidence path: nếu AI thiếu dữ liệu, phải nói rõ đang thiếu gì, xin quyền truy cập/phân tích lịch sử giao dịch MoMo, hoặc cho user nhập nhanh thu nhập, ngân sách, mục tiêu tiết kiệm.

## 6. Finding phụ: Context ngắn

Khi user hỏi tiếp dựa trên câu hỏi trước đó, Moni có thể quên ngữ cảnh và bắt user nhắc lại từ đầu. Hậu quả là workflow phân tích tài chính bị đứt mạch, đặc biệt với các task cần hỏi đáp nhiều bước như lập ngân sách, cắt giảm chi tiêu, hoặc theo dõi mục tiêu tiết kiệm.

Lỗi thuộc layer **intent + context memory + UX recovery**. Nên sửa bằng session memory ngắn hạn: trong một phiên chat, Moni cần nhớ mục tiêu đang thảo luận, các giả định đã xác nhận, và câu hỏi đang tiếp nối.

## 7. Product Decision

### Requirement 1: Data transparency

Nếu Moni không có dữ liệu tài chính cá nhân, không được trả lời như thể đã phân tích dữ liệu. Hệ thống cần hiện rõ:

```text
Mình chưa có dữ liệu chi tiêu của bạn trong tháng này, nên chưa thể kết luận khoản nào cao nhất.
Bạn có muốn mình phân tích lịch sử giao dịch MoMo hoặc nhập nhanh ngân sách không?
```

### Requirement 2: Personal finance setup

Trước khi tư vấn cá nhân hóa, Moni nên có bước setup ngắn:

- Thu nhập hằng tháng.
- Mục tiêu tiết kiệm.
- Hạn mức chi tiêu.
- Có cho phép dùng lịch sử giao dịch MoMo hay không.
- Các khoản chi ngoài MoMo nếu user muốn nhập thêm.

### Requirement 3: Short-term memory trong phiên chat

Trong cùng một phiên, Moni cần nhớ:

- Câu hỏi trước đó của user.
- Mục tiêu tài chính đang nói đến.
- Dữ liệu/số liệu user vừa cung cấp.
- Đề xuất vừa đưa ra.

Nếu Moni không chắc câu hỏi tiếp theo đang nói về điều gì, cần hỏi lại thay vì reset:

```text
Bạn đang hỏi tiếp về kế hoạch tiết kiệm tháng này đúng không?
```

### Requirement 4: Correction path

Khi user sửa thông tin, ví dụ "khoản đó không phải mua sắm, đó là tiền học", Moni cần:

- Cập nhật phân loại trong phiên.
- Ghi nhận correction.
- Hiện lại kết quả sau khi sửa.
- Nếu không thể lưu lâu dài, phải nói rõ correction chỉ áp dụng trong phiên hiện tại.

## 8. Sketch As-is / To-be

### As-is

```text
User mở Moni
    |
    v
Hỏi: "Tháng này tôi tiêu nhiều nhất vào đâu?"
    |
    v
Moni trả lời chung / không có số liệu cá nhân rõ ràng
    |
    v
User hỏi tiếp: "Vậy cắt khoản nào trước?"
    |
    v
Moni mất ngữ cảnh hoặc hỏi lại chung chung
    |
    v
User phải giải thích lại từ đầu
    |
    v
Mất niềm tin + bỏ workflow
```

**Điểm gãy:** AI không nói rõ thiếu data, không có path xin thêm dữ liệu, và không giữ ngữ cảnh hỏi đáp.

### To-be

```text
User mở Moni
    |
    v
Hỏi: "Tháng này tôi tiêu nhiều nhất vào đâu?"
    |
    v
Moni kiểm tra quyền/dữ liệu tài chính
    |
    +-- Có dữ liệu --> Phân tích chi tiêu theo danh mục
    |                  |
    |                  v
    |              Hiện 3 khoản cao nhất + lý do + mức độ tin cậy
    |
    +-- Thiếu dữ liệu --> Nói rõ thiếu gì
                       |
                       v
                 Đề xuất 3 cách tiếp tục:
                 1. Cho phép phân tích giao dịch MoMo
                 2. Nhập nhanh thu nhập/ngân sách
                 3. Nhận lời khuyên chung
                       |
                       v
User hỏi tiếp: "Vậy cắt khoản nào trước?"
    |
    v
Moni nhớ context: user đang muốn cắt giảm chi tiêu tháng này
    |
    v
Gợi ý khoản cần cắt + hỏi user xác nhận/correction
```

**Path đã sửa:** Low-confidence, Failure, Correction.

## 9. SPEC sẽ đổi gì từ finding này?

Finding này sẽ làm SPEC đổi từ "chatbot tư vấn tài chính" thành "trợ lý phân tích chi tiêu có minh bạch về dữ liệu".

Build slice nên được chốt nhỏ hơn:

```text
Cho người dùng MoMo muốn biết tháng này mình tiêu nhiều vào đâu,
prototype dùng AI để phân tích hoặc hỏi xin dữ liệu chi tiêu,
tạo ra bản tóm tắt 3 nhóm chi tiêu lớn nhất và 1 gợi ý cắt giảm,
đồng thời xử lý failure mode thiếu dữ liệu bằng low-confidence path và tùy chọn nhập/kết nối dữ liệu.
```

## 10. Test cases để kiểm tra prototype

| Test case | Input | Expected behavior |
|---|---|---|
| Có dữ liệu | "Tháng này tôi tiêu nhiều nhất vào đâu?" | Moni trả về top danh mục chi tiêu, số tiền, tỷ lệ, và gợi ý hành động. |
| Thiếu dữ liệu | "Lập kế hoạch tiết kiệm cho tôi." | Moni nói rõ thiếu thu nhập/ngân sách/giao dịch và hỏi user muốn nhập gì. |
| Context follow-up | "Tôi muốn tiết kiệm 2 triệu tháng này" -> "Vậy cắt khoản nào trước?" | Moni hiểu "cắt khoản nào" đang nói về mục tiêu tiết kiệm 2 triệu. |
| Correction | "Khoản 500k đó là tiền học, không phải mua sắm" | Moni cập nhật phân loại và tính lại gợi ý. |

## 11. Tự kiểm trước khi nộp

- [x] Có observation cụ thể từ workflow sử dụng Moni.
- [x] Có đủ 4 paths: Happy, Low-confidence, Failure, Correction.
- [x] Finding được viết thành product decision.
- [x] Có sketch as-is và to-be.
- [x] Có câu nói rõ finding này sẽ đổi SPEC như thế nào.
- [ ] Chèn screenshot màn hình Moni nếu giáo viên yêu cầu bằng chứng hình ảnh.
