# 中山網路書店

[![GitHub release](https://img.shields.io/github/release/Text-Analytics-and-Retrieval/db_class2023)](https://github.com/Text-Analytics-and-Retrieval/db_class2023/releases/latest)
[![GitHub license](https://img.shields.io/github/license/Text-Analytics-and-Retrieval/db_class2023)](https://github.com/Text-Analytics-and-Retrieval/db_class2023/main/LICENSE)

一套使用Flask開發的網路書店系統，後端使用Postgres資料庫

## 功能

- 提供CRUD範例，並搭配資料分析功能。
- 以MVC架構開發。
- 一般消費者可以瀏覽、搜尋、購買商品，並查看訂單狀態。
- 後台管理者可以編輯商品，並檢視每筆訂單以及商品銷售圖表。

## 介面範例
![image](https://user-images.githubusercontent.com/52253495/226426951-b1ef62d0-56ae-443f-9483-c06524b5fb12.png)
> 點選以下連結體驗系統功能: https://bookstore.tarflow.com/
## 安裝

### 0. 進入終端機

### 1. 取得原始碼

```bash
# 從 Github 拉取原始碼
git clone https://github.com/Text-Analytics-and-Retrieval/DB_CLASS_2025.git
cd DB_CLASS_2025/
```

### 2. 建立環境
注意：請先安裝 [anaconda](https://www.anaconda.com/download) 再進行後續的步驟
```bash!
# 1. `db-2025` 可改為自訂的環境名稱
# 2. 同學也可以自訂 `python=...` 的版本，但要注意3.11版會有版本衝突的問題，不建議使用
conda create -n db-2025 python=3.10

# 3. 啟動 conda 環境
conda activate db-2025

# 4. 這時候可以在終端機看到類似 
# (db-2025) user@userMacBook-Pro directory %
```

### 3. 安裝環境

##### 安裝python套件

```bash
# 1. 請確認已啟動 conda 環境
# 2. 請確認 `requirements.txt` 檔案位於當前目錄
pip install -r requirements.txt
```

##### 修改連線資訊
首先，執行以下指令，把 .env.example 這個檔案複製一份，並取名叫 .env
> 執行以下指令以後，根目錄下將會有 2 份內容相同的檔案(`.env.example`, `.env`)，我們要修改的是手動新增的 `.env` 檔
```bash
cp .env.example .env
```

接著，在 .env 檔案內填入 PostgreSQL 連線資訊。
> 各組的連線資訊存放在網路大學的，
> 分組學習 ➔專案分組 ➔進入小組 ➔討論 ➔組內討論 ➔資料庫連線資訊
```bash
# .env 檔案中對應的環境參數範例
DB_USER=project_x
DB_PASSWORD=c8763xxx
DB_HOST=140.117.xxx
DB_PORT=12xx
DB_NAME=project_x
```


### 4. 匯入SQL
> 參考資料: [Link](https://learningsky.io/use-postgresql-databases-with-the-pgadmin/)
- 打開 ebook.sql
- 將 SQL 檔裡面的程式碼 貼到 自己組別的資料庫內執行(在自己組別的資料庫點右鍵選Query Tool)並執行

### 5. 啟動程式

```bash
python app.py
倘若遇到 OSError: [Errno 98] Address already in use  像這樣的錯誤代表有重複執行的問題
請輸入 lsof -i :5000 查看是哪個PID使用中，並再輸入kill -9 <該執行中的PID> 刪除
```

## 使用

- 輸入點選running on後面的網址，進入首頁。![2024-10-12 13-30-04 的螢幕擷圖](https://github.com/user-attachments/assets/da1cb799-b40d-4604-8035-10294bf8867c)
- 首次使用請點選註冊按鈕，並註冊帳號。
- 註冊後，點選登入即可進入頁面。
