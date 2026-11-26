# Mẫu đồ án tốt nghiệp PTIT – phiên bản pdfLaTeX/Overleaf

Project được dựng từ **ATTT-Mẫu đồ án TN.v1.0.docx** và **Mau-huong-dan-quyen-DA-TN.pdf** (có trong `tham_khao/`).

## Bắt đầu trên Overleaf

**Đã chuyển toàn bộ sang pdfLaTeX:** không dùng `fontspec`, `\setmainfont`, XeLaTeX, BibTeX hay Biber. Font chính là TeX Gyre Termes mã hóa T5 để hiển thị tiếng Việt. Không được copy lại phần `fontspec` vào project.



1. Truy cập [Overleaf](https://www.overleaf.com/) → **New Project** → **Upload Project**.
2. Chọn chính file `DoAnTotNghiep_PTIT_pdfLaTeX.zip` (không cần giải nén).
3. Trong **Menu** → **Compiler** chọn **pdfLaTeX** (mặc định); main document `main.tex`.
4. Mở file `thong-tin.tex` và điền các trường `\TenDeTai`, `\TenSinhVien`, `\MaSinhVien`, `\LopSinhVien`, `\TenGiangVien`...; thay cả ngày/tháng/năm cho đúng.
5. Viết nội dung trong thư mục `chapters/`, sửa danh sách từ viết tắt ở `frontmatter/tu-viet-tat.tex`, chỉnh nguồn ở `references.tex`.
6. Nhấn **Recompile**. pdfLaTeX xử lý mục lục, số hình và trích dẫn; **không cần bước BibTeX/Biber**.

## Các file cần sửa

| File | Mục đích |
| --- | --- |
| `thong-tin.tex` | Thông tin tên đề tài, sinh viên, GVHD, năm; bật/tắt các trang tùy chọn |
| `main.tex` | Thứ tự các trang/chương, chỉ cần chỉnh khi cấu trúc đồ án khác mẫu |
| `frontmatter/` | Bìa, lời cam đoan, cảm ơn, đề cương nhóm, phân công, bảng viết tắt |
| `chapters/00-mo-dau.tex` | Mở đầu và mục tiêu, phạm vi, tóm tắt bố cục |
| `chapters/01-*.tex` đến `03-*.tex` | Nội dung các chương |
| `chapters/04-ket-luan.tex` | Kết luận, kết quả, hạn chế, hướng phát triển |
| `references.tex` | Tài liệu tham khảo bằng `\bibitem{key}`; dẫn nguồn bằng `\cite{key}`; không cần BibTeX/Biber |
| `assets/` | Logo PTIT lấy từ file Word mẫu; bổ sung các hình của đồ án vào đây |
| `styles/ptit-thesis.sty` | Kiểu chữ, lề trang, tiêu đề, mục lục, header/footer |

## Lưu ý về hai tài liệu mẫu

- **Word ATTT**: bìa ghi **Khoa An toàn thông tin**, có logo PTIT; lời cam đoan, lời cảm ơn, mục lục, danh mục hình/bảng/từ viết tắt, mở đầu, 3 chương, kết luận, tài liệu tham khảo. Mẫu Word có lề gốc trái/phải/trên/dưới **25/18/20/20 mm**, nội dung đa phần chữ **14 pt**.
- **PDF hướng dẫn**: trang bìa, trang lót, đề cương nhóm, bảng phân công chi tiết, cam đoan mức độ tương đồng/Turnitin, mục lục, thuật ngữ viết tắt, nội dung và tài liệu tham khảo. PDF dùng ví dụ của **Khoa Viễn thông 1** và **đồ án nhóm**, nêu lề **30/20/25/25 mm**, chữ **Times New Roman 13 pt**, giãn dòng **1,15–1,3**, số trang La Mã cho phần viết tắt và số trang 1 từ Mở đầu.
- **Mặc định project** dùng **bìa/kết cấu mẫu ATTT** nhưng **cỡ chữ 13 pt và lề 30/20/25/25 mm theo PDF** để bám phần hướng dẫn trình bày. Font **TeX Gyre Termes (T5)** là phương án tương thích Times New Roman trên Overleaf và hỗ trợ tiếng Việt với pdfLaTeX. Font chữ có thể có chênh lệch nhỏ so với Times New Roman thực tế. Nếu trường yêu cầu đúng lề file Word ATTT, chuyển `\TheoLeMauWordtrue` trong `thong-tin.tex`; nếu yêu cầu chữ 14 pt như file Word, sửa `styles/ptit-thesis.sty`, tại định nghĩa `\normalsize`, đổi `{13pt}{16pt}` thành `{14pt}{18pt}`.
- **Không nên tự động áp dụng** quy định dành riêng cho đồ án nhóm Viễn thông vào đồ án cá nhân Khoa ATTT. Chỉ bật các trang bổ sung khi khoa/GVHD yêu cầu. Muốn bật, đổi các dòng trong `thong-tin.tex` từ `false` thành `true`: `\CoTrangLottrue`, `\CoDeCuongtrue`, `\CoPhanCongtrue`, `\CoCamDoanTurnitintrue`.
- PDF có ghi nội dung đồ án nhóm **80–100 trang** và yêu cầu mỗi sinh viên thể hiện đóng góp; đây là yêu cầu trong tài liệu hướng dẫn **đồ án nhóm**, không mặc định áp dụng cho tất cả đề tài/khoa.
- File `frontmatter/cam-doan-turnitin.tex` chỉ tạo **phần văn bản mẫu**; **không thay thế** báo cáo Turnitin có xác nhận. Điền tỷ lệ có thật và đính kèm bản kết quả theo yêu cầu khoa.
- PDF hướng dẫn cũng có mục tùy chọn header/footer. Bật bằng `\HienHeadertrue`.
- Phần lời cam đoan và cảm ơn đang là **bản nháp để cá nhân hóa**. Nội dung trong dấu `[ ... ]`, bảng minh họa và mục trích dẫn mẫu phải được thay hoặc xóa trước khi nộp.

## Cách chèn nội dung

Đoạn văn trực tiếp trong file `.tex`.

Tiêu đề:

```tex
\chapter{Tổng quan}
\section{Kiến trúc hệ thống}
\subsection{Các thành phần}
\subsubsection{Đặc điểm chi tiết}
```

Hình (copy vào `assets/` trước):

```tex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.85\linewidth]{assets/so-do.png}
  \caption{Sơ đồ hệ thống}
  \label{fig:so-do}
\end{figure}
Hình~\ref{fig:so-do} cho thấy ...
```

Tài liệu tham khảo: mở `references.tex` rồi thêm các mục:

```tex
\bibitem{key}
Tên tác giả, \textit{Tên tài liệu}, nhà xuất bản hoặc URL, năm.
```

Trong các chương, dẫn nguồn bằng `\cite{key}`. **Không cần chỉnh `.bib` hoặc dùng Biber**.

## Kiểm tra trước khi in/nộp

Kiểm tra kỹ yêu cầu của **chính khoa/ngành** về đúng bản mẫu, cỡ chữ, lề, trang phụ bắt buộc, ký xác nhận và tỷ lệ tương đồng. Tự kiểm tra số trang, mục lục, thứ tự hình/bảng, nguồn trích dẫn và lượng trang theo quy định cụ thể. LaTeX không tự xác thực nội dung hoặc chữ ký.

## Khắc phục sự cố

- Nếu thấy `Fatal Package fontspec Error`, Overleaf vẫn đang dùng bản project cũ: hãy tạo project từ ZIP pdfLaTeX mới này.
- Nếu lỗi `No PDF` sau khi chuyển, chọn **Menu → Recompile from scratch** và xác nhận `main.tex` là main document.
- Tài liệu tham khảo nằm ở `references.tex`, dùng `\bibitem{key}` và trích dẫn `\cite{key}`; **không có bước chạy BibTeX/Biber**.
- Với font khác như Times New Roman bản Windows, pdfLaTeX không thể dùng `\setmainfont` như XeLaTeX.
