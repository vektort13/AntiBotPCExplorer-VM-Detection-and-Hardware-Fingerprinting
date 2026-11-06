# 常見問題

[首頁](../../README.zh-Hant.md) · [安裝指南](installation.md) · [功能介紹](features.md) · [隱私權與本機資料](privacy.md)

## AntiBotPCExplorer 有哪些功能？

程式可檢查用於描述 Windows 電腦的硬體與系統識別碼、顯示平台安全性與驅動程式簽章資訊、分析虛擬化證據，並比較裝置快照。完整的介面導覽請參閱[功能指南](features.md)。

## 支援哪些 Windows 版本？

支援 x64 系統上的 Windows 10 與 Windows 11。圖形介面使用 Microsoft Edge WebView2 Runtime。執行檔為可攜式，內含介面與翻譯，無須安裝 .NET。

## 在哪裡下載？

請從 [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest) 下載執行檔。同一版本頁面也提供版本說明與 SHA-256 總和檢查碼。首次執行與驗證步驟請參閱[安裝指南](installation.md)。

## 為什麼介面顯示 WebView2 無法啟動？

請至 [Microsoft 的 WebView2 頁面](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)安裝 x64 Evergreen Runtime，再重新啟動應用程式。您也可以使用 `--export report.json` 在不開啟圖形介面的情況下收集 JSON 報告；此模式不使用 WebView2。

## 需要系統管理員權限嗎？

一般檢視可在標準使用者帳戶下執行。部分資料來源需要提升權限，包括 UEFI 變數、開機組態、ATA Identify、Autopilot 硬體雜湊與已知網路歷程。介面會標示無法取得的資料來源，並可透過 **Restart as administrator（以系統管理員身分重新啟動）**，以提升的權限重新啟動檢視工具。

## 程式會變更電腦的識別碼或安全性設定嗎？

掃描會讀取現有資料，不會修改硬體識別碼、韌體、開機設定或 Windows 安全性原則，也不會安裝核心驅動程式。選用的 TPM 金鑰示範，會在您要求執行相關動作時建立或刪除其專用金鑰。應用程式也會儲存本機比較金鑰、所選語言與 WebView2 設定檔，並將匯出的報告寫入您選擇的位置。

## 程式會上傳掃描結果或使用雲端服務嗎？

資料收集、分析、報告比較與匯出皆在本機執行。應用程式不會發出網路要求。**anti.bot** 與 **detect.expert** 按鈕會在預設瀏覽器中開啟對應網站。請參閱[隱私權與本機資料](privacy.md)。

## 為什麼有些數值會隱藏？

序號、UUID、MAC 位址、金鑰指紋與其他標示為敏感的欄位，預設會被遮蔽。請點選 **Show identifiers（顯示識別碼）** 並確認，即可顯示這些數值。「原始 JSON」頁面也遵循相同的顯示設定。

## 兩種匯出格式有何不同？

隱私保護報告會以使用金鑰產生的 HMAC 標記取代敏感欄位，並省略不包含在安全匯出中的表格。原始診斷報告則包含收集到的原始數值。兩者皆保留報告的診斷結構。變更畫面上的顯示設定，不會改變所選的匯出格式。

## 隱私保護報告仍可比較嗎？

可以。使用同一本機 HMAC 金鑰匯出的報告，可在不揭露原始數值的情況下比對受保護的識別碼。若金鑰不同，工具會比較可讀取的數值，並將受保護的欄位標示為無法比較。刪除應用程式的本機資料夾會重設此金鑰。

## 「比較快照」與「報告差異」有何不同？

**Compare snapshots（比較快照）**會計算裝置身分資訊群組之間的加權吻合度，並提供硬體變更模擬。**Report diff（報告差異）**則顯示個別變更的欄位、分數、檢查與表格資料列。比較頁面可將其中的兩份報告直接傳送至「報告差異」。

## 啟用 Hyper-V 或 VBS，就表示這台電腦是客體虛擬機器嗎？

虛擬機器模型會依情境評估觀察結果，並將相關證據分組。在實體 Windows 主機上執行 Hyper-V 或 VBS，不會被當作該電腦為客體虛擬機器的獨立證據。虛擬機器偵測頁面會顯示構成實體電腦可信度的檢查項目與分數貢獻。

## 如何變更語言？

請使用工具列中的旗幟按鈕，或「關於」頁面的語言選項。您也可以在啟動時使用 `--lang en`、`--lang ru`、`--lang vi` 或 `--lang zh-Hant`。其他代碼為 `zh-Hans`、`es`、`pt`、`fr` 與 `de`。

## 設定儲存在哪裡？如何移除？

預設資料夾為 `%LOCALAPPDATA%\AntiBotPCExplorer`，備用位置為 `%TEMP%\AntiBotPCExplorer`。其中包含 HMAC 金鑰、所選語言與 WebView2 設定檔。刪除資料夾前請先關閉應用程式。選用的 TPM 示範金鑰需另外在 TPM 頁面使用 **Delete key（刪除金鑰）** 移除。

## 如何回報問題或提出功能建議？

請使用 [GitHub Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues)。請附上應用程式版本、Windows 版本、發生問題的頁面、重現步驟與預期結果。[貢獻指南](../../CONTRIBUTING.zh-Hant.md)說明意見回饋流程，[安全性政策](../../SECURITY.zh-Hant.md)則說明弱點回報方式。產品網站：[detect.expert](https://detect.expert)、[anti.bot](https://anti.bot) 與 [antidetect.com](https://antidetect.com)。
