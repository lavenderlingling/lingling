# PDF 文本內容抓取及字典表格

## 目錄
- 

## 功能介紹
1. **提取文本**
  - 從指定的 PDF 檔案中提取所有頁面的文本內容。
2. **提取表格**
  - 從指定的 PDF 檔案中提取所有頁面的表格資料，並將轉換為字典格式。
3. **合併結果**
  - 將提取的文本和表格資料合併成一個字典並返回。

## 使用的套件

- **pdfPlumber**：專門用來處理 PDF 中的文本數據及表格資料庫，能將表格數據轉換為易於處理的Pandas DataFrame。
- **PyMuPDF('fitz')**：用於從 PDF 檔案中提取文本內容，能夠精準地提取文本、圖像等內容。
- **Pandas**：用於處理數據和將提取的表格轉換成 DataFrame 對象，以便進行數據操作和保存。

## 使用的方法--程式邏輯

1. 提取文本的函數 (`extract_text_from_pdf`):
    - 開啟指定路徑的PDF檔案。
    - 迭代PDF檔案中的每一頁，提取每一頁的文本內容並追加到變數`text`中。
    - 關閉PDF檔案。
    - 返回提取的文本內容。

2. 提取表格的函數 (`extract_tables_from_pdf`):
    - 開啟指定路徑的PDF檔案。
    - 初始化一個空列表`all_tables`以儲存所有頁面的表格資料。
    - 迭代PDF檔案中的每一頁，提取每一頁的表格資料。
    - 如果當前頁面有表格資料，將其轉換為Pandas DataFrame，並替換換行符為空格。
    - 將處理過的表格數據轉換為字典格式並加入到`all_tables`列表中。
    - 關閉PDF檔案。
    - 返回包含所有表格的字典。

3. 合併文本和表格資料的函數 (`extract_text_and_tables_from_pdf`):
    - 調用`extract_text_from_pdf`函數提取文本內容。
    - 調用`extract_tables_from_pdf`函數提取表格資料。
    - 將提取的文本和表格資料合併成一個字典`result`。
    - 返回合併結果。


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

