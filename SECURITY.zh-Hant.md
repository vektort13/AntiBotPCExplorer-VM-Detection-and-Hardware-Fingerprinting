# 安全性

## 支援的版本

接受針對最新公開版本的安全性回報，目前為 **1.4.0**。請從 [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest) 下載。

## 回報弱點

請使用 [GitHub 私密弱點回報表單](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/security/advisories/new)，將報告傳送給維護者。

請提供應用程式版本、Windows 版本、重現步驟、觀察到的影響，並盡可能附上最小範例。僅附上展示問題所需的資料。弱點細節與敏感附件請透過私密回報提交。

一般錯誤與使用問題，請使用 [Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues)。

## 驗證下載檔案

官方版本的執行檔由 **Vektor T13 Technologies B.V.** 進行數位簽章。版本附件包含 `SHA256SUMS.txt`；[安裝指南](docs/zh-Hant/installation.md)說明如何比對 SHA-256 雜湊值與檢查 Windows 簽章。

## 診斷資料

應用程式在本機收集診斷資料。介面預設隱藏識別碼，標準 JSON 匯出則使用 HMAC 標記。原始匯出包含原始數值。本機儲存、匯出選項與分享報告的說明，請參閱[隱私權與報告](docs/zh-Hant/privacy.md)。
