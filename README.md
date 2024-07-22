# PDF表格內容轉文字

## 使用的套件

1. **PDFPlumber**：用於從 PDF 文件中提取表格和文本數據。
2. **Pandas**：用於處理數據和將提取的表格轉換成 DataFrame 對象，以便進行數據操作和保存。

## 使用的方法

### 提取表格數據

- 使用 `pdfplumber.open()` 打開 PDF 文件。
- 跑每一頁，使用 `page.extract_table()` 方法提取每頁的表格數據。
- 將提取的表格數據轉換為 Pandas DataFrame。
- 刪去表格中的 '\n'

## 最終結果

- 成功從 PDF 文件中提取表格數據，並將每個表格存儲為 DataFrame。
- 每個 DataFrame 逐一印出來以供檢查。
