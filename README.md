專案內容說明

此 Notebook 主要包含以下部分：

環境測試與初始設定

建立簡單的變數與輸出（a = 1）。

使用 !ls 查看當前 Colab 目錄內容。

嘗試使用 google-drive-ocamlfuse 掛載 Google Drive

嘗試安裝 google-drive-ocamlfuse 並進行 OAuth 驗證。

不過因為 Colab 版本限制及憑證問題，該方法會產生錯誤（invalid_client）。

改用官方方式掛載 Google Drive

最後成功使用 from google.colab import drive 進行掛載：

from google.colab import drive
drive.mount("/content/drive")


掛載成功後，可以透過 /content/drive/MyDrive 路徑存取 Google Drive 檔案。

⚙️ 執行步驟

打開此 Notebook：


執行前兩個測試區塊：

步驟1:
添加代碼塊
我們就可以在代碼框中輸入一些代碼，如果我們直接輸入代碼，系統會當作是Python代碼執行。例如我們輸入：
![image](1.jpg)


若需掛載 Google Drive，使用以下正確方法：

from google.colab import drive
drive.mount("/content/drive")


驗證成功後，即可在 Colab 中看到：

Mounted at /content/drive


可用以下指令確認掛載結果：

!ls /content/drive/MyDrive

🧩 注意事項

不建議在 Colab 使用 google-drive-ocamlfuse，因為 Colab 內建的 Google Drive 掛載方式更穩定且簡單。

若出現 invalid_client 或 OAuth 失敗訊息，表示使用了不相容的驗證流程。

掛載後，請確保路徑 /content/drive/MyDrive/ 為正確目錄。
