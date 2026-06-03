# Bài làm App Teardown - MoMo Moni

## 1. Sản phẩm được chọn

**Sản phẩm:** MoMo - Moni  
**Tính năng AI:** Trợ lý tài chính cá nhân, hỗ trợ hỏi đáp, phân tích và gợi ý quản lý chi tiêu  
**Cách truy cập:** Ứng dụng MoMo  
**Người dùng mục tiêu:** Người dùng MoMo có nhu cầu theo dõi chi tiêu cá nhân, lập kế hoạch tiết kiệm và hiểu rõ hơn về tình hình tài chính của mình.

Em chọn Moni của MoMo vì đây là một tính năng AI nằm trong ứng dụng tài chính rất phổ biến. MoMo vốn đã có nhiều dữ liệu liên quan đến hành vi tài chính của người dùng như chuyển tiền, thanh toán hóa đơn, nạp điện thoại, mua vé, thanh toán dịch vụ. Vì vậy, khi thấy Moni được giới thiệu như một trợ lý tài chính, người dùng sẽ kỳ vọng rằng AI có thể hiểu tình hình tài chính cá nhân của mình, chứ không chỉ trả lời các lời khuyên chung chung.

## 2. Product hứa gì?

Moni tạo cảm giác rằng sản phẩm có thể giúp người dùng quản lý tài chính cá nhân tốt hơn bằng cách trò chuyện tự nhiên. Người dùng có thể hỏi các câu như:

- Tháng này tôi tiêu nhiều nhất vào đâu?
- Tôi nên tiết kiệm như thế nào?
- Khoản chi nào có thể cắt giảm?
- Tôi có đang tiêu quá nhiều không?
- Làm sao để quản lý tiền tốt hơn?

Lời hứa chính của Moni là biến việc quản lý tài chính từ một việc khó, mất thời gian và cần ghi chép thủ công thành một cuộc trò chuyện đơn giản với AI.

## 3. User nào được hứa sẽ được giúp?

Nhóm user phù hợp nhất là những người dùng MoMo hằng ngày nhưng chưa có thói quen quản lý tài chính rõ ràng. Ví dụ:

- Sinh viên muốn kiểm soát tiền sinh hoạt.
- Nhân viên văn phòng muốn biết mình tiêu tiền vào đâu mỗi tháng.
- Người mới đi làm muốn tiết kiệm một khoản cố định.
- Người thường xuyên thanh toán qua MoMo nhưng chưa tự tổng hợp lại chi tiêu.

Với nhóm user này, vấn đề không phải là họ không muốn quản lý tiền, mà là họ không có đủ thời gian, dữ liệu được tổng hợp sẵn, hoặc không biết bắt đầu phân tích từ đâu.

## 4. Kỳ vọng khi dùng Moni

Khi sử dụng Moni, em kỳ vọng AI có thể làm được các task sau:

- Tổng hợp chi tiêu cá nhân theo tháng.
- Phân loại giao dịch thành các nhóm như ăn uống, đi lại, mua sắm, hóa đơn, giải trí.
- Chỉ ra nhóm chi tiêu nào đang cao bất thường.
- Gợi ý khoản nào nên cắt giảm trước.
- Lập kế hoạch tiết kiệm dựa trên thu nhập và thói quen chi tiêu.
- Nhớ ngữ cảnh câu hỏi trước để trả lời các câu hỏi tiếp theo.

Ví dụ, nếu em hỏi "Tháng này tôi tiêu nhiều nhất vào đâu?", Moni nên có khả năng trả lời dựa trên dữ liệu thật của em. Nếu chưa có dữ liệu, Moni cần nói rõ rằng chưa có dữ liệu và hướng dẫn em cách cung cấp thêm thông tin.

## 5. Reality - Điểm gãy khi dùng thật

Điểm gãy lớn nhất là Moni có hình ảnh của một trợ lý tài chính cá nhân, nhưng chưa thật sự cho thấy rằng nó đang nắm được thông tin tài chính cá nhân của người dùng.

Khi người dùng hỏi một câu mang tính cá nhân như:

```text
Tháng này tôi tiêu nhiều nhất vào đâu?
```

AI rất dễ trả lời theo hướng chung chung, ví dụ khuyên người dùng nên kiểm tra lại lịch sử giao dịch, chia khoản chi thành từng nhóm, hoặc lập ngân sách. Những lời khuyên này không sai, nhưng chưa giải quyết đúng kỳ vọng của người dùng. User không cần một bài học chung về quản lý tiền; user cần AI phân tích chính dữ liệu tài chính của mình.

Vấn đề thứ hai là context ngắn. Khi người dùng hỏi tiếp dựa trên câu trước, Moni có thể không hiểu rằng câu hỏi mới đang nối tiếp cuộc trò chuyện cũ.

Ví dụ:

```text
User: Tôi muốn tiết kiệm 2 triệu trong tháng này.
Moni: Đưa ra một số lời khuyên tiết kiệm chung.

User: Vậy tôi nên cắt khoản nào trước?
```

Ở câu hỏi thứ hai, nếu Moni không nhớ mục tiêu "tiết kiệm 2 triệu trong tháng này", nó sẽ trả lời chung chung hoặc yêu cầu người dùng nói lại từ đầu. Điều này làm trải nghiệm bị đứt mạch và không còn giống một trợ lý tài chính cá nhân.

## 6. Evidence / Observation

| Observation | Prompt/Input đã thử | Path liên quan | Điều học được |
|---|---|---|---|
| Moni có thể tư vấn tài chính ở mức tổng quát, nhưng chưa thể hiện rõ rằng đang phân tích dữ liệu tài chính cá nhân của user. | "Tháng này tôi tiêu nhiều nhất vào đâu?" | Failure / Low-confidence | AI cần biết khi nào mình thiếu dữ liệu và phải nói rõ điều đó với user. |
| Khi hỏi tiếp một câu dựa trên câu trước, AI dễ mất ngữ cảnh. | "Tôi muốn tiết kiệm 2 triệu tháng này" rồi hỏi tiếp "Vậy nên cắt khoản nào trước?" | Correction / Failure | Trợ lý tài chính cần có khả năng nhớ ngữ cảnh trong một phiên chat. |
| Nếu câu trả lời không dựa trên số liệu cá nhân, user khó tin vào gợi ý. | "Lập kế hoạch chi tiêu cho tôi từ nay đến cuối tháng." | Low-confidence | Với bài toán tài chính, độ tin cậy phụ thuộc vào dữ liệu và cách AI giải thích giới hạn của mình. |

## 7. Phân tích 4 paths

| Path | Mô tả hiện tại | Vấn đề | Đề xuất cải thiện |
|---|---|---|---|
| Happy path | Khi user hỏi câu chung như "làm sao để tiết kiệm tiền?", Moni có thể đưa lời khuyên tổng quát. | Câu trả lời có thể đúng nhưng chưa cá nhân hóa. | Nếu có dữ liệu, Moni nên trả lời dựa trên chi tiêu thật của user. |
| Low-confidence path | Khi thiếu dữ liệu, Moni chưa luôn nói rõ rằng mình không có đủ dữ liệu để kết luận. | User có thể hiểu nhầm rằng AI đã phân tích tài chính cá nhân, trong khi thực tế chỉ đang trả lời chung. | Moni cần nói rõ đang thiếu dữ liệu nào và hỏi user có muốn nhập hoặc cho phép truy cập dữ liệu không. |
| Failure path | User hỏi về chi tiêu cá nhân nhưng AI không có dữ liệu để tính toán. | Lỗi nằm ở data-tool layer: AI không có hoặc không dùng được dữ liệu tài chính cá nhân. | Thêm fallback: xin quyền phân tích giao dịch MoMo, cho nhập thu nhập/ngân sách, hoặc chuyển sang lời khuyên chung. |
| Correction path | User sửa hoặc hỏi tiếp nhưng AI không lưu lại correction/ngữ cảnh. | User phải giải thích lại từ đầu, làm workflow bị gián đoạn. | Moni cần lưu context ngắn hạn trong phiên chat và cập nhật lại phân tích khi user sửa thông tin. |

## 8. Finding chính

Khi user hỏi Moni về tình hình chi tiêu cá nhân, AI/product có thể trả lời theo hướng tư vấn chung vì chưa nắm được dữ liệu tài chính thật của user hoặc chưa nói rõ rằng mình không có dữ liệu. Hậu quả là user khó tin vào kết quả, không biết nên hành động dựa trên số liệu nào, và cảm thấy Moni giống một chatbot hỏi đáp hơn là một trợ lý tài chính cá nhân.

Lỗi thuộc layer **data-tool + UX recovery**.

Nên sửa bằng cách thêm low-confidence path rõ ràng: nếu AI thiếu dữ liệu, AI phải nói rõ đang thiếu gì, xin quyền truy cập/phân tích lịch sử giao dịch MoMo, hoặc cho user nhập nhanh thu nhập, ngân sách và mục tiêu tiết kiệm.

## 9. Finding phụ: Context ngắn

Khi user hỏi tiếp dựa trên câu hỏi trước đó, Moni có thể quên ngữ cảnh và bắt user nhắc lại từ đầu. Hậu quả là workflow phân tích tài chính bị đứt mạch, đặc biệt với các task cần nhiều bước như lập ngân sách, cắt giảm chi tiêu hoặc theo dõi mục tiêu tiết kiệm.

Lỗi thuộc layer **intent + context memory + UX recovery**.

Nên sửa bằng session memory ngắn hạn: trong một phiên chat, Moni cần nhớ mục tiêu đang thảo luận, dữ liệu user vừa cung cấp, giả định đã xác nhận và đề xuất vừa đưa ra.

## 10. Product decision

### Requirement 1: Minh bạch về dữ liệu

Nếu Moni không có dữ liệu tài chính cá nhân, Moni không nên trả lời như thể đã phân tích dữ liệu của user. Thay vào đó, hệ thống cần nói rõ:

```text
Mình chưa có dữ liệu chi tiêu của bạn trong tháng này, nên chưa thể kết luận khoản nào cao nhất.
Bạn có muốn mình phân tích lịch sử giao dịch MoMo hoặc nhập nhanh ngân sách không?
```

### Requirement 2: Bước thiết lập tài chính cá nhân

Trước khi đưa ra gợi ý cá nhân hóa, Moni nên hỏi user một số thông tin cơ bản:

- Thu nhập hằng tháng.
- Mục tiêu tiết kiệm.
- Hạn mức chi tiêu mong muốn.
- Có cho phép phân tích lịch sử giao dịch MoMo hay không.
- Có khoản chi ngoài MoMo cần nhập thêm hay không.

### Requirement 3: Ghi nhớ ngữ cảnh trong phiên chat

Trong cùng một phiên trò chuyện, Moni cần nhớ:

- Câu hỏi trước đó của user.
- Mục tiêu tài chính đang thảo luận.
- Số liệu user vừa cung cấp.
- Gợi ý vừa đưa ra.

Ví dụ:

```text
User: Tôi muốn tiết kiệm 2 triệu tháng này.
Moni: Mình sẽ giúp bạn tìm các khoản có thể cắt giảm.
User: Vậy nên cắt khoản nào trước?
Moni: Với mục tiêu tiết kiệm 2 triệu tháng này, mình sẽ ưu tiên xem các khoản chi linh hoạt như ăn uống, mua sắm và giải trí.
```

### Requirement 4: Cho phép user sửa và cập nhật lại kết quả

Nếu user sửa phân loại giao dịch, Moni cần cập nhật lại kết quả.

Ví dụ:

```text
User: Khoản 500k đó là tiền học, không phải mua sắm.
Moni: Mình đã chuyển khoản 500k từ nhóm mua sắm sang nhóm học tập. Tổng chi mua sắm của bạn hiện giảm còn ...
```

Nếu correction chỉ được lưu trong phiên hiện tại, Moni cũng cần nói rõ để tránh user hiểu nhầm.

## 11. Sketch As-is

```text
User mở Moni
    |
    v
Hỏi: "Tháng này tôi tiêu nhiều nhất vào đâu?"
    |
    v
Moni trả lời chung chung hoặc không có số liệu cá nhân rõ ràng
    |
    v
User hỏi tiếp: "Vậy tôi nên cắt khoản nào trước?"
    |
    v
Moni không nhớ rõ ngữ cảnh câu trước
    |
    v
User phải giải thích lại từ đầu
    |
    v
User mất niềm tin và bỏ workflow
```

**Điểm gãy trong as-is:**

- AI không nói rõ mình thiếu dữ liệu tài chính cá nhân.
- AI không có bước xin thêm dữ liệu hoặc xin quyền phân tích giao dịch.
- AI không giữ ngữ cảnh đủ tốt cho câu hỏi tiếp theo.
- User không biết nên sửa hoặc bổ sung thông tin ở đâu.

## 12. Sketch To-be

```text
User mở Moni
    |
    v
Hỏi: "Tháng này tôi tiêu nhiều nhất vào đâu?"
    |
    v
Moni kiểm tra quyền truy cập và dữ liệu tài chính
    |
    +-- Có dữ liệu
    |       |
    |       v
    |   Phân tích giao dịch theo danh mục
    |       |
    |       v
    |   Trả về 3 nhóm chi tiêu cao nhất + số tiền + gợi ý cắt giảm
    |
    +-- Thiếu dữ liệu
            |
            v
        Nói rõ đang thiếu dữ liệu
            |
            v
        Đưa 3 lựa chọn:
        1. Cho phép phân tích giao dịch MoMo
        2. Nhập nhanh thu nhập/ngân sách
        3. Nhận lời khuyên chung
            |
            v
User hỏi tiếp: "Vậy tôi nên cắt khoản nào trước?"
    |
    v
Moni nhớ context: user đang muốn giảm chi tiêu trong tháng này
    |
    v
Moni gợi ý khoản nên cắt trước và hỏi user xác nhận
```

**Path đã được cải thiện:** Low-confidence, Failure, Correction.

## 13. SPEC sẽ đổi gì từ finding này?

Finding này làm SPEC đổi từ:

```text
Xây chatbot tư vấn tài chính cho người dùng.
```

thành:

```text
Xây trợ lý phân tích chi tiêu cá nhân có minh bạch dữ liệu, biết khi nào thiếu dữ liệu, biết hỏi thêm thông tin và nhớ ngữ cảnh trong một phiên chat.
```

Build slice nên được chốt nhỏ lại:

```text
Cho người dùng MoMo muốn biết tháng này mình tiêu nhiều vào đâu,
prototype dùng AI để phân tích hoặc hỏi xin dữ liệu chi tiêu,
tạo ra bản tóm tắt 3 nhóm chi tiêu lớn nhất và 1 gợi ý cắt giảm,
đồng thời xử lý failure mode thiếu dữ liệu bằng low-confidence path và tùy chọn nhập/kết nối dữ liệu.
```

## 14. Test cases cho prototype

| Test case | Input | Expected behavior |
|---|---|---|
| Có dữ liệu chi tiêu | "Tháng này tôi tiêu nhiều nhất vào đâu?" | Moni trả về top danh mục chi tiêu, số tiền, tỷ lệ và gợi ý hành động. |
| Thiếu dữ liệu | "Lập kế hoạch tiết kiệm cho tôi." | Moni nói rõ thiếu thu nhập/ngân sách/giao dịch và hỏi user muốn nhập gì. |
| Hỏi tiếp dựa trên context | "Tôi muốn tiết kiệm 2 triệu tháng này" -> "Vậy cắt khoản nào trước?" | Moni hiểu câu hỏi thứ hai đang nói về mục tiêu tiết kiệm 2 triệu. |
| User sửa thông tin | "Khoản 500k đó là tiền học, không phải mua sắm" | Moni cập nhật phân loại và tính lại gợi ý. |

## 15. Kết luận

Moni có tiềm năng trở thành một trợ lý tài chính cá nhân hữu ích vì nằm ngay trong MoMo, nơi có nhiều giao dịch tài chính của người dùng. Tuy nhiên, vấn đề hiện tại là Moni chưa thể hiện rõ khả năng nắm dữ liệu tài chính cá nhân và dễ bị mất ngữ cảnh khi user hỏi tiếp.

Để cải thiện, Moni cần minh bạch khi thiếu dữ liệu, có bước xin thêm dữ liệu hoặc xin quyền phân tích giao dịch, và có khả năng nhớ ngữ cảnh ngắn hạn trong một phiên chat. Như vậy, Moni sẽ chuyển từ một chatbot tư vấn chung thành một trợ lý tài chính cá nhân đáng tin cậy hơn.
