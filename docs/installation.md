# Installation and first run

[Home](../README.md) · [Features](features.md) · [FAQ](faq.md) · [Privacy and local data](privacy.md)

## Requirements

| Component | Requirement |
| --- | --- |
| Operating system | Windows 10 or Windows 11, 64-bit x64 |
| Application | One portable executable; no installer or .NET requirement |
| Graphical interface | Microsoft Edge WebView2 Runtime |
| Permissions | A standard user account for normal inspection; optional elevation for additional sources |

The interface and all nine interface translations are embedded in the executable. WebView2 Runtime is included with Windows 11. If the interface reports that WebView2 could not start, install the x64 Evergreen Runtime from [Microsoft's WebView2 download page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and open the application again.

## Download and run

1. Open the [latest release](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).
2. Download `AntiBotPCExplorer-1.4.0-x64.exe` from **Assets** and place it in a folder of your choice.
3. Double-click the executable. Collection starts automatically, and the Overview opens when the scan finishes.
4. Use the sidebar to explore hardware, system identifiers, platform security, drivers and VM detection.

[Download the executable](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest/download/AntiBotPCExplorer-1.4.0-x64.exe) · [All releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases)

The application collects data locally. It does not need a product account or an internet connection to run a scan.

## Verify the download

Download the release's SHA-256 checksum file alongside the executable. In PowerShell, calculate the downloaded file's hash:

```powershell
Get-FileHash .\AntiBotPCExplorer-1.4.0-x64.exe -Algorithm SHA256
```

Compare the result with the entry for the same file in the checksum file.

The executable is digitally signed by **Vektor T13 Technologies B.V.** To inspect its signature in PowerShell:

```powershell
Get-AuthenticodeSignature .\AntiBotPCExplorer-1.4.0-x64.exe | Format-List Status,SignerCertificate
```

Windows should report `Valid`. You can also open the file's **Properties → Digital Signatures** tab.

## Navigate the interface

| Action | Control |
| --- | --- |
| Change the interface language | Flag button in the top toolbar, or the About page |
| Search the current page | `Ctrl+F`; searches English labels and their translations |
| Collect a new snapshot | `F5` |
| Reveal sensitive identifiers | **Show identifiers**, then confirm |
| Save a report | **Export** → **Privacy-safe report** or **Raw diagnostic report** |
| Read additional protected sources | **Restart as administrator** in the application |

The language menu offers English, Russian, Vietnamese, Simplified Chinese, Traditional Chinese, Spanish, Brazilian Portuguese, French and German. The first launch follows Windows language settings, and later launches remember your selection.

Elevation adds access to sources such as UEFI Secure Boot variables, boot configuration, ATA Identify, the Autopilot hardware hash and known network history. Other sections remain available when a protected source cannot be read; its row shows the reason.

## Export without opening a window

These commands use the native collector and do not require WebView2. Because the executable is a GUI application, `Start-Process -Wait` makes PowerShell wait until the report has been written.

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export','report.json' -Wait -NoNewWindow
```

For a raw report containing original identifier values:

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export-raw','raw.json' -Wait -NoNewWindow
```

The output path is relative to the process's working directory unless an absolute path is supplied. Use a writable location. For a path containing spaces, include quotes around the path inside the argument string:

```powershell
Start-Process .\AntiBotPCExplorer-1.4.0-x64.exe -ArgumentList '--export "C:\Reports Folder\report.json"' -Wait -NoNewWindow
```

Open the interface in a chosen language:

```powershell
.\AntiBotPCExplorer-1.4.0-x64.exe --lang zh-Hant
```

Supported language codes: `en`, `ru`, `vi`, `zh-Hans`, `zh-Hant`, `es`, `pt`, `fr`, `de`.

## Update or remove

To update, close the application and download the new executable from Releases. Local settings are stored separately from the executable, so replacing the program preserves the selected language and the key used to compare protected identifiers.

To remove the program, delete the executable. To remove its local settings and WebView2 profile as well, close the program and delete `%LOCALAPPDATA%\AntiBotPCExplorer`. This also resets the report comparison key. Reports exported before and after the reset cannot match their HMAC-protected identifiers. See [Privacy and local data](privacy.md) for the complete list of stored files and the optional TPM demonstration key.
