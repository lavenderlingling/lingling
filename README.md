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


# Excel表格轉字典
## 功能

此程式碼的主要功能是從 Excel 檔案中讀取數據並將其轉換成 Python 字典格式。該檔案可能包含關於農產品訂單的信息，如訂單編號、項目名稱、商店、類別、單位、單價等，並將其轉換成字典。

## 使用技術

- **Pandas 庫**：這是 Python 中用於數據處理和分析的一個強大工具，它提供了讀取和管理多種檔案格式的功能，包括 CSV 和 Excel。
- **Excel 處理**：利用 Pandas 的 `read_excel` 函數來讀取 Excel 檔案，並通過 `to_dict` 方法將數據轉換成字典格式，方便進行數據處理。

## 程式碼說明

1. 引入 Pandas 庫。
2. 定義一個函數 `read_excel_to_dict`，接受一個檔案路徑作為參數。
3. 使用 `pd.read_excel()` 讀取 Excel 檔案。
4. 使用 `df.to_dict(orient='list')` 將 DataFrame 轉換為字典，其中每個鍵對應一列，並將列值作為列表。
5. 打印出讀取的數據字典。

## 最終成果
- 將從指定的 Excel 檔案中成功讀取數據。
- 數據將被轉換成字典格式，使得每一個列（如訂單編號、項目名稱、商店、類別等）都被映射為一個鍵。
- 其相應的值則是包含該列所有數據的列表，例如篩選、排序或應用於各種數據分析框架中。

