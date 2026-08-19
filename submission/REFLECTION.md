# Reflection

Kết quả trên 50 truy vấn cho thấy hybrid đạt Precision@10 trung bình cao nhất (78,6%), nhỉnh hơn BM25 (77,8%) và semantic (73,2%). Hybrid hiệu quả nhất với truy vấn mixed vì kết hợp được tín hiệu khớp từ khóa và độ tương đồng ngữ nghĩa; trong thí nghiệm, hybrid đạt 100% ở nhóm này. BM25 mạnh với truy vấn exact (96,7%) do các từ khóa quan trọng xuất hiện trực tiếp trong tài liệu. Semantic đáng lẽ phù hợp với paraphrase, nhưng kết quả hiện tại chỉ đạt 24%, thấp hơn BM25 và hybrid. Nguyên nhân có thể là mô hình `bge-small-en-v1.5` chủ yếu tối ưu cho tiếng Anh, trong khi corpus và truy vấn là tiếng Việt; cần cân nhắc mô hình đa ngôn ngữ như BGE-M3.

Tôi sẽ không dùng hybrid khi truy vấn exact đã đủ tốt, khi yêu cầu latency rất thấp, hoặc khi chi phí duy trì đồng thời BM25 và vector index lớn hơn lợi ích chất lượng. Với hệ thống có quy tắc lọc chặt hoặc dữ liệu nhỏ, một retriever đơn giản cũng dễ vận hành và giải thích hơn.
