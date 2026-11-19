# HW09｜兩場活動報名整理器

- **作業編號**：HW09
- **作業名稱**：兩場活動報名整理器
- **姓名**：趙苡昕
- **學號**：D1446537

## 程式用途與執行方式
本程式用來整理「桌遊體驗」與「電影欣賞」兩場活動的原始報名文字，透過字串處理（去半形空白、轉小寫、`split(",")`）建立保留重複項目的串列，再使用集合（`set`）進行去重、交集、聯集與差集比較，最後搭配字典（`dict`）與切片計算人數、報名人次、前兩位通知名單與各場應收費用[span_3](start_span)[span_3](end_span)[span_4](start_span)[span_4](end_span)[span_5](start_span)[span_5](end_span)[span_6](start_span)[span_6](end_span)。

### 如何在 Google Colab 開啟並執行
1. 在 Google Colab 開啟本筆記本（`activity_signup_你的學號.ipynb`）[span_7](start_span)[span_7](end_span)[span_8](start_span)[span_8](end_span)。
2. 依序執行「測試一」「測試二」「測試三」三個儲存格，確認每個儲存格下方都顯示完整輸出結果[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span)。

## 三組實測摘要
| 測試組別 | 桌遊人數 | 電影人數 | 共同人數 | 總不重複人數 | 報名人次 | 總應收 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| 測試一（原始資料） | 3 | 3 | 1 | 5 | 6 | 600.00 元 |
| 測試二（新增 Frank） | 3 | 4 | 1 | 6 | 7 | 680.00 元 |
| 測試三（兩場去重相同） | 3 | 3 | 3 | 3 | 6 | 600.00 元 |

## 個人回答

### 問題一：測試一桌遊串列有 4 筆資料但費用以 3 人算；拆成 `list` 與轉成 `set` 各保留了什麼、失去了什麼？
測試一的桌遊串列整理後是 `['amy', 'ben', 'amy', 'cora']` 共 4 筆，但因為同一個人同場只算一位參加者、只收一次費用，所以是以 3 人計算[span_11](start_span)[span_11](end_span)[span_12](start_span)[span_12](end_span)[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span)。轉成 `list` 時保留了原本的先後順序與重複出現的紀錄（例如 `'amy'` 出現兩次），但不能直接拿來算人數或收費；轉成 `set` 後保留了不重複的參加者名單（3 人），卻失去了原本的順序與重複報名的次數資訊[span_15](start_span)[span_15](end_span)[span_16](start_span)[span_16](end_span)[span_17](start_span)[span_17](end_span)。

### 問題二：測試三兩場只有 3 位不同的人，為什麼是 6 人次、總應收仍是 600 元？請用集合關係與算式說明。
測試三兩場去重後都是 `{'amy', 'ben', 'cora'}`，所以聯集元素個數（總不重複人數）是 `3` 人[span_18](start_span)[span_18](end_span)[span_19](start_span)[span_19](end_span)。但「報名人次」是兩場各自去重人數相加，算式為 `3 + 3 = 6` 人次（因為這 3 人各報了兩場）[span_20](start_span)[span_20](end_span)[span_21](start_span)[span_21](end_span)[span_22](start_span)[span_22](end_span)[span_23](start_span)[span_23](end_span)。費用則是兩場分開計費：桌遊 `3 × 120 = 360` 元，電影 `3 × 80 = 240` 元，總應收為 `360 + 240 = 600` 元[span_24](start_span)[span_24](end_span)[span_25](start_span)[span_25](end_span)[span_26](start_span)[span_26](end_span)[span_27](start_span)[span_27](end_span)。

## AI 使用紀錄
- **使用工具**：Gemini[span_28](start_span)[span_28](end_span)
- **主要提示詞**：提供 HW09 兩場活動報名整理器作業截圖，請協助依規定完成三組測試程式、Colab 儲存與下載方式，以及 GitHub 繳交準備[span_29](start_span)[span_29](end_span)[span_30](start_span)[span_30](end_span)[span_31](start_span)[span_31](end_span)。
- **親自修改與驗證**：在 Colab 分別建立並執行測試一、測試二、測試三，確認三組實際輸出皆顯示在筆記本中，並核對人數、人次、名單排序與應收金額是否正確，再下載 `.ipynb` 檔準備上傳 GitHub[span_32](start_span)[span_32](end_span)[span_33](start_span)[span_33](end_span)[span_34](start_span)[span_34](end_span)。
