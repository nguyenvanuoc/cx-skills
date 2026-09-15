---
name: ui-checklist-library
description: Thư viện checklist UI chuẩn. Dùng để list, tra cứu, lọc và cung cấp checklist UI cho hoạt động Design Review, Design QA và UI Audit.
---

# UI Checklist Library Skill

## Mục tiêu

Skill này chứa toàn bộ checklist UI 

## Quy tắc sử dụng

- Đây là nguồn checklist UI chuẩn; không tự ý thêm, xóa hoặc sửa nội dung checklist.
- Giữ nguyên Checklist ID, Phần tử, Phân loại, Mô tả tiêu chí, Nội dung kiểm tra, Pass khi, Nhãn và Cơ sở tham chiếu.
- Khi người dùng yêu cầu list tất cả, phải hiển thị toàn bộ checklist.
- Khi người dùng yêu cầu tìm kiếm, tìm trong ID, Phần tử, Phân loại, Mô tả, Nội dung kiểm tra, Pass khi, Nhãn và Cơ sở tham chiếu.
- Khi người dùng yêu cầu lọc theo nhóm, chỉ trả về các checklist thực sự phù hợp.
- Khi dùng cho UI Audit, checklist có thể được đánh giá thành PASS / FAIL / N/A / NEEDS VALIDATION.
- Không tự tạo issue hoặc điểm số nếu người dùng chỉ yêu cầu xem checklist.

## Tổng quan

- Tổng số checklist UI: **81**

## Toàn bộ checklist UI

| STT | ID | Phần tử | Phân loại | Mô tả tiêu chí | Nội dung kiểm tra | Pass khi | Nhãn | Cơ sở tham chiếu |
|---:|---|---|---|---|---|---|---|---|
| 1 | UI-LA01 | Layout | Bố cục & Grid | Layout sử dụng hệ lưới thống nhất | Kiểm tra container, column, gutter và các vùng nội dung. | Các khối bám cùng hệ lưới, không lệch hoặc phá vỡ cấu trúc trang. | Cơ bản | ISO 9241-161; File chuẩn dòng 15–16 |
| 2 | UI-LA02 | Layout | Căn gióng | Các khối nội dung được căn theo cùng mốc, căn đều, căn giữa theo trật tự nhất định | So sánh mép trái, mép phải, baseline và trục giữa của các khối.<br>Kiểm tra căn giữa/căn đều,... có bị lệch không | Không xuất hiện sai lệch thị giác giữa các đối tượng cùng cấp. | Cơ bản | ISO 9241-161; File chuẩn dòng 15–16 |
| 3 | UI-LA03 | Layout | Phân cấp thị giác | Màn hình có đường dẫn mắt rõ ràng | Kiểm tra thứ tự nhìn từ tiêu đề, nội dung chính đến hành động. | Người xem nhận biết được nội dung chính trước nội dung phụ. | Cơ bản | ISO 9241-161; File chuẩn dòng 17 |
| 4 | UI-LA04 | Layout | Khoảng cách & Khoảng trắng | Nội dung liên quan được gom nhóm bằng khoảng cách | So sánh khoảng cách trong nhóm và giữa các nhóm. | Khoảng cách trong nhóm nhỏ hơn khoảng cách giữa các nhóm. | Cơ bản | File chuẩn dòng 20, 60 |
| 5 | UI-LA05 | Layout | Khoảng cách & Khoảng trắng | Khoảng cách tuân thủ spacing scale | Kiểm tra margin, padding và gap so với token hoặc scale thiết kế. | Không sử dụng giá trị tùy tiện; các khoảng cách bám cùng một scale. | Cơ bản | Material 3; File chuẩn dòng 18–21 |
| 6 | UI-LA06 | Layout | Màu sắc & Tương phản | Đảm bảo độ tương phản | So sánh độ bão hòa và tương phản của background với nội dung chính.<br>Văn bản thông thường (nhỏ hơn 18pt hoặc 24px): Tỷ lệ tương phản tối thiểu là 4,5:1.<br>Văn bản cỡ lớn (từ 18pt / 24px trở lên, hoặc 14pt / 18.5px nếu in đậm): Tỷ lệ tương phản tối thiểu là 3:1.<br>Thành phần phi văn bản (giao diện UI, icon, đường viền): Tỷ lệ tối thiểu là 3:1 | Background hỗ trợ nội dung và không cạnh tranh điểm nhìn. | Cơ bản | WCAG 2.2 SC 1.4.09 |
| 7 | UI-LA07 | Layout | Responsive | Layout tái bố trí theo viewport | Kiểm tra desktop, tablet, mobile và các breakpoint được hỗ trợ. | Không chồng lấn, mất nội dung hoặc phát sinh cuộn ngang ngoài chủ đích. | Bắt buộc | WCAG 2.2 SC 1.4.10 |
| 8 | UI-LA08 | Layout | Khả năng tiếp cận thị giác | Giao diện giữ nguyên nội dung khi phóng to | Kiểm tra zoom văn bản và zoom trình duyệt đến mức áp dụng. | Nội dung không bị cắt, che khuất hoặc mất chức năng khi phóng to. | Bắt buộc | WCAG 2.2 SC 1.4.4, 1.4.10 |
| 9 | UI-SI01 | Sidebar | Trạng thái & Hiệu ứng | Sidebar phân biệt rõ mục hiện tại | Kiểm tra default, hover, focus, active, expanded và collapsed. | Mục hiện tại dễ nhận biết và không chỉ được phân biệt bằng màu. | Bắt buộc | WCAG 2.2 SC 1.4.1, 2.4.7 |
| 10 | UI-LO01 | Logo | Nhận diện thương hiệu | Logo sử dụng đúng phiên bản | Đối chiếu cấu tạo, màu sắc và biến thể logo với Brand Guideline. | Không dùng sai logo, sai màu hoặc sai cấu trúc. | Bắt buộc | File chuẩn dòng 4 |
| 11 | UI-LO02 | Logo | Kích thước & Tỷ lệ | Logo giữ đúng tỷ lệ | Kiểm tra tỷ lệ chiều rộng, chiều cao và cách scale. | Logo không bị kéo giãn, bóp méo hoặc crop sai. | Bắt buộc | File chuẩn dòng 4 |
| 12 | UI-LO03 | Logo | Khoảng cách & Khoảng trắng | Logo có vùng an toàn | Kiểm tra khoảng cách giữa logo với chữ, viền và thành phần lân cận. | Khoảng trống đạt quy định Brand Guideline và logo không bị che khuất. | Cơ bản | File chuẩn dòng 4 |
| 13 | UI-LO04 | Logo | Responsive | Logo rõ nét ở các kích thước hiển thị | Kiểm tra header, sidebar, mobile, màn đăng nhập và nền khác nhau. | Logo không mờ, mất chi tiết hoặc mất khả năng nhận diện. | Bắt buộc | Apple HIG; File chuẩn dòng 4 |
| 14 | UI-TY01 | Typography | Nhận diện thương hiệu | Font family đúng nhận diện | Đối chiếu font sử dụng với Brand Guideline hoặc Design System. | Không xuất hiện font ngoài danh mục được cho phép. | Cơ bản | File chuẩn dòng 5 |
| 15 | UI-TY02 | Typography | Khả năng tiếp cận thị giác | Nội dung văn bản hiển thị rõ ràng và có thể nhận biết | Kiểm tra độ tương phản, độ rõ nét, lỗi font, clipping, chồng chữ và khả năng hiển thị khi phóng to hoặc thay đổi khoảng cách văn bản | Chữ không nhòe, dính, mất dấu, chồng lấn hoặc bị cắt; text đạt contrast tối thiểu theo WCAG; nội dung vẫn đầy đủ khi resize và điều chỉnh text spacing (Phóng to chữ đến 200% không mất nội dung hoặc chức năng) | Cơ bản | WCAG 2.2 |
| 16 | UI-TY03 | Typography | Typography | Các vai trò chữ có style riêng | Kiểm tra heading, subtitle, body, label, caption, link và status text. | Mỗi vai trò có font-size, weight, line-height và màu được xác định. | Cơ bản | Material 3; File chuẩn dòng 47 |
| 17 | UI-TY04 | Typography | Phân cấp thị giác | Các cấp chữ thể hiện đúng quan hệ | So sánh heading, subtitle, body và caption trên cùng màn hình. | Cấp trên nổi bật hơn cấp dưới và không có hai cấp hiển thị giống nhau. | Cơ bản | File chuẩn dòng 57 |
| 18 | UI-TY05 | Typography | Kích thước & Tỷ lệ | Cỡ chữ đủ lớn để đọc | Kiểm tra body, label, caption và nội dung quan trọng. | Đạt typography token; nếu áp dụng quy định nội bộ, body thường là 16px, tối thiểu 14px và trường hợp hẹp không dưới 12px. | Cơ bản | File chuẩn dòng 37; không phải ngưỡng WCAG |
| 19 | UI-TY06 | Typography | Khoảng cách & Khoảng trắng | Line-height phù hợp với loại nội dung | Kiểm tra line-height của body và heading. Line-height khoảng 1,5 lần font-size đối với font body. 1.1*font-size<=Line-height <=1.4*font-size đối với heading | Các dòng không dính nhau hoặc quá rời; đạt typography token đã quy định. | Cơ bản | WCAG 2.2 SC 1.4.12; File chuẩn dòng 40 |
| 20 | UI-TY07 | Typography | Khoảng cách & Khoảng trắng | Khoảng cách đoạn văn rõ ràng | Kiểm tra paragraph spacing giữa các đoạn liên tiếp. Giữ khoảng cách đoạn văn trong khoảng từ 0,75x - 1,25x lần kích thước font. Cấu trúc phân đoạn rõ ràng dễ đọc. | Các đoạn được phân biệt rõ và không làm mất nhịp đọc. | Cơ bản | WCAG 2.2 SC 1.4.12; File chuẩn dòng 39 |
| 21 | UI-TY08 | Typography | Căn gióng | Đoạn văn dài có cách căn phù hợp | Kiểm tra body text nhiều dòng theo chiều ngôn ngữ.<br>- Đoạn văn bản yêu cầu căn trái, không căn đều 2 bên/căn giữa/căn phải (Căn phải chỉ được chấp nhận nếu ứng dụng đó dành cho các ngôn ngữ RTL (right-to-left) như Arabic, Hebrew) <br>- Không thụt đầu dòng, không lẻ chữ | Văn bản LTR ưu tiên căn trái; không căn giữa hoặc justify đoạn dài ngoài chủ đích. | Cơ bản | File chuẩn dòng 38 |
| 22 | UI-TY09 | Typography | Phong cách thiết kế | Không lạm dụng viết hoa, bold và italic | Kiểm tra paragraph, label và text thông thường. | Không viết hoa toàn bộ đoạn dài; bold và italic chỉ dùng để nhấn mạnh có chủ đích. | Cơ bản | File chuẩn dòng 35–36 |
| 23 | UI-TY10 | Typography | Màu sắc & Tương phản | Chữ có độ tương phản đạt chuẩn | Đo contrast giữa chữ và nền ở mọi trạng thái. | Text thường đạt tối thiểu 4.5:1; text lớn đạt tối thiểu 3:1, trừ ngoại lệ WCAG. | Bắt buộc | WCAG 2.2 SC 1.4.3 |
| 24 | UI-TY11 | Typography | Khả năng tiếp cận thị giác | Không chỉ dùng màu để biểu đạt nghĩa của chữ | Kiểm tra link, trạng thái, lỗi và nội dung highlight. | Thông tin còn được phân biệt bằng underline, icon, label hoặc hình thức khác. | Bắt buộc | WCAG 2.2 SC 1.4.1 |
| 25 | UI-TY12 | Typography | Tính nhất quán | Text cùng vai trò có cùng style | So sánh text cùng chức năng trên các màn hình. | Font, size, weight, màu và spacing thống nhất theo token. | Cơ bản | WCAG 2.2 SC 3.2.4; File chuẩn dòng 47 |
| 26 | UI-TY13 | Typography | Kích thước & Tỷ lệ | Chiều dài dòng văn bản phù hợp để đọc liên tục | Đếm số ký tự hoặc glyph trên mỗi dòng của đoạn văn dài tại viewport mặc định và khi thay đổi kích thước cửa sổ | Mỗi dòng không vượt quá 80 ký tự hoặc glyph; giao diện nên duy trì khoảng 45–75 ký tự mỗi dòng để hỗ trợ khả năng đọc | Bắt buộc | WCAG 2.2 SC 1.4.8 Visual Presentation (AAA); typography best practice |
| 27 | UI-TY14 | Typography | Responsive | Chiều dài dòng thích ứng với viewport | Thu nhỏ và phóng to giao diện để kiểm tra độ rộng khối văn bản | Khối chữ co giãn hoặc đổi cột hợp lý; không tạo dòng quá dài và không bắt người dùng cuộn ngang để đọc. Không mất dấu, clipping, chồng chữ hoặc tràn khỏi vùng chứa. | Bắt buộc | WCAG 2.2 SC 1.4.4, 1.4.10 |
| 28 | UI-IC01 | Icon | Hình ảnh & Iconography | Icon thuộc cùng một ngôn ngữ tạo hình | Các icon trong cùng một ngữ cảnh cần nhất quán về:<br>Outlined hoặc Filled.<br>Rounded hoặc Sharp.<br>Stroke width.<br>Corner style.<br>Mức độ chi tiết.<br>Tỷ lệ hình khối.<br>Visual weight. | Icon cùng nhóm có style thống nhất và toàn bộ thư viện có tính liên hệ. | Cơ bản | File chuẩn dòng 6, 42 |
| 29 | UI-IC02 | Icon | Kích thước & Tỷ lệ | Kích thước icon phù hợp với vai trò | So sánh icon inline, navigation, action và status. | Icon cùng vai trò có cùng bounding box và kích thước thị giác. | Cơ bản | Material 3; Apple HIG |
| 30 | UI-IC03 | Icon | Căn gióng | Icon được căn quang học với chữ và vùng chứa | Kiểm tra icon trong button, input, menu và list item. | Icon không bị lệch baseline hoặc lệch tâm thị giác. | Cơ bản | ISO 9241-161; Material 3 |
| 31 | UI-IC04 | Icon | Màu sắc & Tương phản | Icon chức năng có contrast phù hợp | Đo contrast của icon cần thiết để nhận biết control hoặc trạng thái. | Icon thiết yếu đạt tối thiểu 3:1 so với màu liền kề. | Bắt buộc | WCAG 2.2 SC 1.4.11 |
| 32 | UI-IC05 | Icon | Tính logic & Quen thuộc | Hình dạng icon phù hợp với ý nghĩa | Kiểm tra icon với quy ước nền tảng và ngữ cảnh sử dụng. | Icon dễ nhận biết | Cơ bản | ISO 9241-161; File chuẩn dòng 65 |
| 33 | UI-IC06 | Icon | Tính nhất quán | Một chức năng sử dụng cùng một icon | So sánh cùng hành động trên các màn hình khác nhau. | Không dùng nhiều biểu tượng khác nhau cho cùng một chức năng. | Cơ bản | WCAG 2.2 SC 3.2.4 |
| 34 | UI-HÌ01 | Hình ảnh/Illustration | Nhận diện thương hiệu | Hình ảnh phù hợp phong cách thương hiệu | Kiểm tra tone màu, phong cách vẽ, phối cảnh và mức độ chi tiết. | Các hình cùng nhóm thể hiện cùng phong cách và tinh thần thương hiệu. | Cơ bản | File chuẩn dòng 7, 45 |
| 35 | UI-HÌ02 | Hình ảnh/Illustration | Kích thước & Tỷ lệ | Hình ảnh giữ đúng tỷ lệ | Kiểm tra crop, scale và aspect ratio. | Hình không méo; chủ thể không bị crop sai hoặc mất chi tiết quan trọng. | Bắt buộc | Apple HIG |
| 36 | UI-HÌ03 | Hình ảnh/Illustration | Phân cấp thị giác | Chủ thể chính trong ảnh được nhấn mạnh | Kiểm tra độ nét, tương phản, vị trí và lớp hiển thị của chủ thể. | Chủ thể chính được nhận biết trước thành phần trang trí. | Cơ bản | File chuẩn dòng 53 |
| 37 | UI-HÌ04 | Hình ảnh/Illustration | Màu sắc & Tương phản | Màu ảnh hài hòa với giao diện | So sánh màu của ảnh, banner và illustration với hệ màu sản phẩm. | Hình ảnh không lệch tone hoặc gây xung đột màu với giao diện. | Cơ bản | File chuẩn dòng 28 |
| 38 | UI-HÌ05 | Hình ảnh/Illustration | Khả năng tiếp cận thị giác | Hình ảnh mang thông tin có mô tả thay thế | Kiểm tra ảnh nội dung, biểu đồ ảnh và illustration có ý nghĩa. | Có text alternative tương đương; ảnh trang trí được bỏ qua đúng cách. | Bắt buộc | WCAG 2.2 SC 1.1.1 |
| 39 | UI-BU01 | Button | Phong cách thiết kế | Button sử dụng đúng variant | Kiểm tra primary, secondary, tertiary, text và destructive button. | Variant phù hợp với mức độ quan trọng và loại hành động. | Cơ bản | Material 3; WAI-ARIA APG |
| 40 | UI-BU02 | Button | Phân cấp thị giác | Mỗi nhóm chỉ có một primary action | Kiểm tra button trong form, dialog, card và toolbar. | Chỉ một hành động quan trọng nhất được thể hiện nổi bật trong cùng nhóm. | Cơ bản | File chuẩn dòng 48, 58 |
| 41 | UI-BU03 | Button | Kích thước & Tỷ lệ | Button có kích thước phù hợp | Kiểm tra chiều cao, chiều rộng tối thiểu và vùng tương tác. | Kích thước bám Design System; target đạt tối thiểu 24×24 CSS px hoặc ngoại lệ WCAG. | Bắt buộc | WCAG 2.2 SC 2.5.8 |
| 42 | UI-BU04 | Button | Khoảng cách & Khoảng trắng | Padding và khoảng cách icon–label nhất quán | Kiểm tra padding ngang, dọc và gap bên trong button. | Nội dung không sát viền và các button cùng loại dùng cùng token. | Cơ bản | Material 3; File chuẩn dòng 19, 21 |
| 43 | UI-BU05 | Button | Trạng thái & Hiệu ứng | Button có đủ trạng thái thị giác | Kiểm tra default, hover, focus, pressed, disabled và loading. | Mỗi trạng thái nhận biết được; thay đổi trạng thái không làm button dịch chuyển. | Bắt buộc | WAI-ARIA APG; WCAG 2.2 SC 2.4.7 |
| 44 | UI-BU06 | Button | Màu sắc & Tương phản | Nội dung và ranh giới button đủ tương phản | Đo contrast của label, icon, border và focus indicator. | Text đạt SC 1.4.3; phần tử phi văn bản thiết yếu đạt SC 1.4.11. | Bắt buộc | WCAG 2.2 SC 1.4.3, 1.4.11 |
| 45 | UI-BU07 | Button | Tính nhất quán | Button cùng vai trò có cùng style | So sánh màu, radius, padding, font và icon giữa các màn hình. | Không xuất hiện nhiều kiểu button cho cùng một vai trò. | Cơ bản | WCAG 2.2 SC 3.2.4; File chuẩn dòng 42 |
| 46 | UI-BU08 | Button | Responsive | Label button không bị cắt | Kiểm tra nội dung dài, bản dịch, zoom và mobile. | Button co giãn hoặc xuống dòng đúng quy định; không mất nội dung. | Bắt buộc | WCAG 2.2 SC 1.4.10 |
| 47 | UI-TE01 | Text field/Input | Phong cách thiết kế | Input có cấu trúc nhận diện rõ | Kiểm tra label, field, placeholder, supporting text, icon và counter. | Người xem phân biệt được label, giá trị, gợi ý và thông báo hỗ trợ. | Cơ bản | Material 3; WAI-ARIA APG |
| 48 | UI-TE02 | Text field/Input | Tính nhất quán | Vị trí label thống nhất | So sánh label trên, trái hoặc floating label giữa các form. | Các form cùng loại sử dụng cùng một quy tắc đặt label. | Cơ bản | File chuẩn dòng 46 |
| 49 | UI-TE03 | Text field/Input | Kích thước & Tỷ lệ | Input và button cạnh nhau có chiều cao tương ứng | Kiểm tra các control nằm cùng hàng trong form hoặc toolbar. | Không lệch chiều cao hoặc baseline ngoài chủ đích. | Cơ bản | File chuẩn dòng 43 |
| 50 | UI-TE04 | Text field/Input | Trạng thái & Hiệu ứng | Input có đủ trạng thái thị giác | Kiểm tra default, hover, focus, filled, disabled, read-only, error và success. | Các trạng thái phân biệt rõ; error không chỉ dựa vào màu. | Bắt buộc | WCAG 2.2 SC 1.4.1, 3.3.1 |
| 51 | UI-TE05 | Text field/Input | Màu sắc & Tương phản | Border, label và nội dung input đủ tương phản | Kiểm tra field trên các nền và ở mọi trạng thái. | Text đạt SC 1.4.3; ranh giới cần thiết và focus đạt SC 1.4.11. | Bắt buộc | WCAG 2.2 SC 1.4.3, 1.4.11 |
| 52 | UI-TE06 | Text field/Input | Responsive | Input không vỡ bố cục khi nội dung dài | Kiểm tra label dài, error message, prefix, suffix và bàn phím mobile. | Không chồng lấn, cắt label hoặc che khuất thông báo. | Bắt buộc | WCAG 2.2 SC 1.4.10 |
| 53 | UI-DR01 | Dropdown/Select | Tính logic & Quen thuộc | Select có hình dạng dễ nhận biết | Kiểm tra trường đóng, dấu hiệu mở danh sách và item được chọn. | Người dùng phân biệt được select với input thông thường. | Cơ bản | ISO 9241-161; WAI-ARIA APG |
| 54 | UI-DR02 | Dropdown/Select | Trạng thái & Hiệu ứng | Select có đủ trạng thái | Kiểm tra default, hover, focus, expanded, selected, disabled và error. | Trạng thái mở và item được chọn được thể hiện rõ. | Bắt buộc | WAI-ARIA APG Combobox/Listbox |
| 55 | UI-DR03 | Dropdown/Select | Kích thước & Tỷ lệ | Danh sách có kích thước phù hợp | Kiểm tra chiều cao item, chiều rộng popup và vùng scroll. | Item dễ đọc; popup không hẹp hơn nội dung cần thiết hoặc tràn viewport. | Cơ bản | Material 3; Apple HIG |
| 56 | UI-DR04 | Dropdown/Select | Màu sắc & Tương phản | Focus và selected item không chỉ dựa vào màu | Kiểm tra outline, icon check, background và text của item. | Focus và lựa chọn vẫn nhận biết được trong chế độ màu hạn chế. | Bắt buộc | WCAG 2.2 SC 1.4.1, 2.4.7 |
| 57 | UI-CH01 | Checkbox/Radio/Switch | Phong cách thiết kế | Sử dụng đúng loại control lựa chọn | Kiểm tra checkbox cho nhiều lựa chọn, radio cho một lựa chọn và switch cho bật/tắt. | Loại control phù hợp với cấu trúc lựa chọn và Design System. | Cơ bản | WAI-ARIA APG |
| 58 | UI-CH02 | Checkbox/Radio/Switch | Kích thước & Tỷ lệ | Control và vùng nhấn đủ lớn | Kiểm tra hình điều khiển, label và toàn bộ hit area. | Target đạt tối thiểu 24×24 CSS px hoặc ngoại lệ WCAG. | Bắt buộc | WCAG 2.2 SC 2.5.8 |
| 59 | UI-CH03 | Checkbox/Radio/Switch | Trạng thái & Hiệu ứng | Control có đầy đủ trạng thái | Kiểm tra unchecked, checked, indeterminate, focus, disabled và error. | Mỗi trạng thái có dấu hiệu thị giác rõ ràng. | Bắt buộc | WAI-ARIA APG |
| 60 | UI-CH04 | Checkbox/Radio/Switch | Khả năng tiếp cận thị giác | Trạng thái không chỉ thể hiện bằng màu | Kiểm tra checkmark, dot, vị trí thumb, icon và label trạng thái. | Vẫn xác định được trạng thái khi không phân biệt được màu. | Bắt buộc | WCAG 2.2 SC 1.4.1 |
| 61 | UI-CH05 | Checkbox/Radio/Switch | Tính nhất quán | Màu active thống nhất với hệ thống | So sánh active color và focus style giữa các control lựa chọn. | Các control sử dụng cùng semantic token theo Design System. | Cơ bản | File chuẩn dòng 44 |
| 62 | UI-CA01 | Card | Phong cách thiết kế | Card sử dụng cùng ngôn ngữ thiết kế | Kiểm tra border, radius, shadow, nền và cấu trúc card. | Card cùng loại có cùng style và phân biệt được với nền trang. | Cơ bản | Material 3; File chuẩn dòng 9, 42 |
| 63 | UI-CA02 | Card | Khoảng cách & Khoảng trắng | Nội dung card có padding phù hợp | Kiểm tra khoảng cách giữa viền, tiêu đề, nội dung và action. | Nội dung không sát viền; spacing bám token và nhất quán. | Cơ bản | File chuẩn dòng 18 |
| 64 | UI-CA03 | Card | Phân cấp thị giác | Nội dung chính và phụ trong card rõ ràng | Kiểm tra title, body, metadata, image và action. | Nội dung quan trọng được nhận biết trước metadata và action phụ. | Cơ bản | File chuẩn dòng 51, 56 |
| 65 | UI-CA04 | Card | Trạng thái & Hiệu ứng | Card tương tác có trạng thái rõ | Kiểm tra hover, focus, selected, pressed và disabled. | Card tương tác phân biệt với card tĩnh; focus indicator nhìn thấy rõ. | Bắt buộc | WCAG 2.2 SC 2.4.7; Material 3 |
| 66 | UI-ME01 | Menu/Navigation | Tính nhất quán | Navigation giữ nguyên cách nhận diện | So sánh tên, icon, vị trí và style giữa các màn hình. | Thành phần cùng chức năng được nhận diện thống nhất. | Bắt buộc | WCAG 2.2 SC 3.2.3, 3.2.4 |
| 67 | UI-TA01 | Tab | Trạng thái & Hiệu ứng | Tab hiện tại được phân biệt rõ | Kiểm tra default, hover, focus, selected và disabled. | Tab selected không chỉ khác tab thường bằng màu. | Bắt buộc | WAI-ARIA APG Tabs; WCAG 2.2 SC 1.4.1 |
| 68 | UI-BR01 | Breadcrumb | Tính logic & Quen thuộc | Breadcrumb thể hiện đúng cấu trúc cấp bậc | Kiểm tra separator, item trung gian và trang hiện tại. | Trang hiện tại dễ nhận biết và không hiển thị như một link có thể điều hướng. | Cơ bản | WAI-ARIA APG Breadcrumb |
| 69 | UI-PA01 | Pagination | Kích thước & Tỷ lệ | Pagination có vùng tương tác phù hợp | Kiểm tra số trang, previous, next và ellipsis. | Target đủ lớn, khoảng cách rõ và không gây nhấn nhầm. | Bắt buộc | WCAG 2.2 SC 2.5.8 |
| 70 | UI-ME02 | Menu/Tab/Breadcrumb | Căn gióng | Các item navigation được căn đều | Kiểm tra baseline, icon, label, indicator và khoảng cách item. | Item cùng cấp có cùng chiều cao và căn chỉnh thống nhất. | Cơ bản | Material 3; Apple HIG |
| 71 | UI-DA01 | Data table | Bố cục & Grid | Cột và hàng sử dụng lưới rõ ràng | Kiểm tra header, body, divider, alignment và vùng scroll. | Dữ liệu bám cột; header liên hệ rõ với nội dung bên dưới. | Cơ bản | ISO 9241-161; Material 3 |
| 72 | UI-DA02 | Data table | Căn gióng | Dữ liệu được căn theo loại | Kiểm tra text, số, ngày, trạng thái và action trong cột. | Text thường căn trái; số có cùng mốc căn; action được đặt nhất quán. | Cơ bản | ISO 9241-161 |
| 73 | UI-DA03 | Data table | Trạng thái & Hiệu ứng | Bảng có trạng thái hàng rõ ràng | Kiểm tra hover, selected, expanded, loading, empty và error. | Mỗi trạng thái nhận biết được và không làm thay đổi cấu trúc cột. | Bắt buộc | Material 3; WCAG 2.2 SC 1.4.1 |
| 74 | UI-DA04 | Data table | Responsive | Bảng xử lý đúng ở màn hình hẹp | Kiểm tra cuộn ngang, sticky column, thu gọn cột hoặc chuyển dạng. | Không mất dữ liệu quan trọng; cơ chế xem thêm rõ ràng và có chủ đích. | Bắt buộc | WCAG 2.2 SC 1.4.10 |
| 75 | UI-MO01 | Modal/Dialog | Phân cấp thị giác | Dialog nổi bật rõ khỏi lớp nền | Kiểm tra backdrop, elevation, border và quan hệ với trang bên dưới. | Người dùng nhận biết được lớp đang hoạt động; nội dung nền không cạnh tranh thị giác. | Cơ bản | WAI-ARIA APG Dialog; File chuẩn dòng 63 |
| 76 | UI-MO02 | Modal/Dialog | Khoảng cách & Khoảng trắng | Nội dung dialog có khoảng cách hợp lý | Kiểm tra header, body, footer, close button và các nhóm nội dung. | Nội dung không sát viền; nhóm liên quan gần nhau hơn nhóm không liên quan. | Cơ bản | File chuẩn dòng 18, 60 |
| 77 | UI-MO03 | Modal/Dialog | Phân cấp thị giác | Action chính và phụ được phân biệt | Kiểm tra Submit, Cancel, destructive action và close action. | Một action chính nổi bật; thứ tự action tuân thủ Design System của nền tảng. | Cơ bản | WAI-ARIA APG; Material 3; Apple HIG |
| 78 | UI-MO04 | Modal/Dialog | Responsive | Dialog vừa viewport và không che action | Kiểm tra nội dung dài, scroll, mobile và bàn phím ảo. | Header hoặc action cần thiết vẫn truy cập được; dialog không tràn viewport. | Bắt buộc | WCAG 2.2 SC 1.4.10, 2.4.11 |
| 79 | UI-AL01 | Alert/Toast | Màu sắc & Tương phản | Trạng thái semantic được thể hiện nhất quán | Kiểm tra success, information, warning và error. | Màu, icon và label trạng thái nhất quán; không chỉ dựa vào màu. | Bắt buộc | WCAG 2.2 SC 1.4.1; File chuẩn dòng 62 |
| 80 | UI-AL02 | Alert/Toast | Trạng thái & Hiệu ứng | Thông báo xuất hiện và biến mất không gây gián đoạn thị giác | Kiểm tra animation, thời gian hiển thị, xếp chồng và vị trí. | Không nhấp nháy; nội dung đọc được; nhiều thông báo không che khuất action quan trọng. | Bắt buộc | WCAG 2.2 SC 2.2.1, 2.3.1, 4.1.3 |
| 81 | UI-CH06 | Chart/Data visualization | Màu sắc & Tương phản | Dữ liệu biểu đồ không chỉ phân biệt bằng màu | Kiểm tra series, legend, label, pattern và trạng thái highlight. | Các chuỗi dữ liệu phân biệt được bằng label, pattern, marker hoặc hình thức bổ sung; thành phần thiết yếu đạt contrast áp dụng. | Bắt buộc | WCAG 2.2 SC 1.4.1, 1.4.11 |

## Mẫu output khi tra cứu

| ID | Phần tử | Phân loại | Mô tả tiêu chí | Nội dung kiểm tra | Pass khi | Nhãn |
|---|---|---|---|---|---|---|
| UI-... | ... | ... | ... | ... | ... | ... |

## Mẫu câu lệnh

- `List toàn bộ checklist UI`
- `List checklist UI nhóm Layout`
- `Tìm checklist UI liên quan đến typography`
- `Lấy checklist UI áp dụng cho màn hình Login`
- `Tìm checklist UI có nhãn Bắt buộc`
- `Đánh giá màn hình theo toàn bộ checklist UI trong skill này`