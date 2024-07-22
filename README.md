使用的套件：
PDFPlumber：用於從 PDF 文件中提取表格和文本數據。
Pandas：用於處理數據和將提取的表格轉換成 DataFrame 對象，以及進行數據操作和保存。
使用的方法：
提取表格數據：
使用 pdfplumber.open() 打開 PDF 文件。
遍歷每一頁，使用 page.extract_table() 方法提取每頁的表格數據。
將提取的表格數據轉換為 Pandas DataFrame。
處理和保存數據：
遍歷包含所有表格的列表 all_tables，每個元素轉換為一個 DataFrame。
動態調整循環次數以匹配 all_tables 列表的長度，確保能遍歷每一個表格。
使用 DataFrame.to_csv() 方法將數據保存到 CSV 文件。
最終結果：
成功從 PDF 文件中提取表格數據，並將每個表格存儲為 DataFrame。
每個 DataFrame 被逐一打印出來以供檢查，表格數據被保存到一個名為 "output.csv" 的文件中。
使用循環確保了所有表格都被處理，且無索引越界的錯誤。
