# 安裝與首次執行

[首頁](../../README.zh-Hant.md) · [功能介紹](features.md) · [常見問題](faq.md) · [隱私權與本機資料](privacy.md)

## 系統需求

| 元件 | 需求 |
| --- | --- |
| 作業系統 | Windows 10 或 Windows 11，64 位元 x64 |
| 應用程式 | 單一可攜式執行檔；無須安裝程式或 .NET |
| 圖形介面 | Microsoft Edge WebView2 Runtime |
| 權限 | 一般檢視使用標準使用者帳戶；可選擇提升權限以存取更多資料來源 |

介面與全部九種介面語言的翻譯均內嵌於執行檔中。Windows 11 已包含 WebView2 Runtime。若介面提示 WebView2 無法啟動，請至 [Microsoft 的 WebView2 下載頁面](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)安裝 x64 Evergreen Runtime，然後重新開啟應用程式。

## 下載與執行

1. 開啟[最新版本](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest)。
2. 從 **Assets** 下載 `AntiBotPCExplorer-1.4.0-x64.exe`，並將其放入您選擇的資料夾。
3. 按兩下執行檔。資料收集會自動開始，掃描完成後即顯示總覽。
4. 使用側邊欄瀏覽硬體、系統識別碼、平台安全性、驅動程式與虛擬機器偵測資訊。

[下載執行檔](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest/download/AntiBotPCExplorer-1.4.0-x64.exe) · [所有版本](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases)

應用程式會在本機收集資料。執行掃描無須產品帳戶或網際網路連線。

## 驗證下載檔案

請一併下載該版本的 SHA-256 總和檢查碼檔案與執行檔。在 PowerShell 中計算已下載檔案的雜湊值：

```powershell
Get-FileHash .\AntiBotPCExplorer-1.4.0-x64.exe -Algorithm SHA256
```

將結果與總和檢查碼檔案中相同檔名的項目比對。

執行檔由 **Vektor T13 Technologies B.V.** 進行數位簽章。您可以在 PowerShell 中檢查簽章：

```powershell
Get-AuthenticodeSignature .\AntiBotPCExplorer-1.4.0-x64.exe | Format-List Status,SignerCertificate
```

Windows 應回報 `Valid`。您也可以開啟檔案的**內容 → 數位簽章**索引標籤。

## 介面操作

| 操作 | 控制方式 |
| --- | --- |
| 變更介面語言 | 頂端工具列中的旗幟按鈕，或「關於」頁面 |
| 搜尋目前頁面 | `Ctrl+F`；可搜尋英文標籤及其翻譯 |
| 收集新快照 | `F5` |
| 顯示敏感識別碼 | **Show identifiers（顯示識別碼）**，然後確認 |
| 儲存報告 | **Export（匯出）** → **Privacy-safe report（隱私保護報告）** 或 **Raw diagnostic report（原始診斷報告）** |
| 讀取更多受保護的資料來源 | 應用程式中的 **Restart as administrator（以系統管理員身分重新啟動）** |

語言選單提供英文、俄文、越南文、簡體中文、繁體中文、西班牙文、巴西葡萄牙文、法文與德文。首次啟動時會依照 Windows 語言設定選擇語言，之後則會記住您的選擇。

提升權限後，可存取 UEFI 安全開機變數、開機組態、ATA Identify、Autopilot 硬體雜湊與已知網路歷程等資料來源。若無法讀取某個受保護的資料來源，其他區段仍可使用；該項目會顯示原因。

## 不開啟視窗即可匯出

下列命令使用原生資料收集功能，無須 WebView2。由於執行檔屬於 GUI 應用程式，`Start-Process -Wait` 可讓 PowerShell 等待報告寫入完成。

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export','report.json' -Wait -NoNewWindow
```

若要匯出含有原始識別碼數值的原始報告：

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export-raw','raw.json' -Wait -NoNewWindow
```

若未提供絕對路徑，輸出路徑會相對於處理程序的工作目錄。請使用可寫入的位置。若路徑包含空格，請在引數字串中以引號括住路徑：

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export "C:\Reports Folder\report.json"' -Wait -NoNewWindow
```

以指定語言開啟介面：

```powershell
.\AntiBotPCExplorer-1.4.0-x64.exe --lang zh-Hant
```

支援的語言代碼：`en`、`ru`、`vi`、`zh-Hans`、`zh-Hant`、`es`、`pt`、`fr`、`de`。

## 更新或移除

若要更新，請關閉應用程式，並從 Releases 下載新版執行檔。本機設定與執行檔分開儲存，因此替換程式時會保留所選語言，以及用於比較受保護識別碼的金鑰。

若要移除程式，請刪除執行檔。若也要移除本機設定與 WebView2 設定檔，請先關閉程式，再刪除 `%LOCALAPPDATA%\AntiBotPCExplorer`。這也會重設報告比較金鑰。重設前後匯出的報告，無法比對其受 HMAC 保護的識別碼。完整的已儲存檔案清單與選用 TPM 示範金鑰的說明，請參閱[隱私權與本機資料](privacy.md)。
