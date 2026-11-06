# Frequently asked questions

[Home](../README.md) · [Installation](installation.md) · [Features](features.md) · [Privacy and local data](privacy.md)

## What does AntiBotPCExplorer do?

It inspects the hardware and system identifiers that describe a Windows PC, shows platform security and driver signing information, analyzes virtualization evidence, and compares device snapshots. See the [feature guide](features.md) for the full interface tour.

## Which Windows versions can run it?

Windows 10 and Windows 11 on x64 systems. The graphical interface uses Microsoft Edge WebView2 Runtime. The executable is portable and contains its interface and translations; no .NET installation is needed.

## Where do I download it?

Download the executable from [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest). The same release provides its release notes and SHA-256 checksum. See [Installation](installation.md) for the first run and verification steps.

## Why does the interface say WebView2 could not start?

Install the x64 Evergreen Runtime from [Microsoft's WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and launch the application again. You can also collect a JSON report without the graphical interface using `--export report.json`; this mode does not use WebView2.

## Do I need administrator rights?

Normal inspection runs under a standard user account. Some sources require elevation, including UEFI variables, boot configuration, ATA Identify, the Autopilot hardware hash and known network history. The interface identifies unavailable sources, and its **Restart as administrator** action can restart the inspector with elevation.

## Does it change the computer's identifiers or security settings?

Scanning reads existing data. It does not modify hardware identifiers, firmware, boot settings or Windows security policies, and it does not install a kernel driver. The optional TPM key demonstration creates or deletes its own key when you request those actions. The application also stores its local comparison key, language selection and WebView2 profile, and writes exported reports to the location you select.

## Does it upload scans or use a cloud service?

Collection, analysis, report comparison and export run locally. The application makes no network requests. The **anti.bot** and **detect.expert** buttons open those websites in your default browser. See [Privacy and local data](privacy.md).

## Why are some values hidden?

Serial numbers, UUIDs, MAC addresses, key fingerprints and other fields marked sensitive are masked by default. Click **Show identifiers** and confirm to reveal them. The Raw JSON page follows the same reveal setting.

## What is the difference between the two export formats?

A privacy-safe report replaces sensitive fields with keyed HMAC tags and omits tables that are not included in safe exports. A raw diagnostic report includes the collected original values. Both retain the report's diagnostic structure. Changing the on-screen reveal setting does not change the chosen export format.

## Can privacy-safe reports still be compared?

Yes. Reports exported with the same local HMAC key can match their protected identifiers without revealing the original values. When keys differ, the tools compare readable values and mark protected fields as not comparable. Deleting the application's local data folder resets that key.

## How do Compare snapshots and Report diff differ?

**Compare snapshots** calculates a weighted match between device identity groups and provides hardware change simulations. **Report diff** shows individual changed fields, scores, checks and table rows. The comparison page can pass its two reports directly to Report diff.

## Does enabling Hyper-V or VBS automatically mean the PC is a guest VM?

The VM model evaluates observations in context and groups related evidence. Hyper-V or VBS on a physical Windows host is not treated as independent proof that the machine is a guest. The VM Detection page shows the checks and contributions behind Physical PC Confidence.

## How do I change the language?

Use the flag button in the toolbar or the language choices on About. You can also launch with `--lang en`, `--lang ru`, `--lang vi` or `--lang zh-Hant`. Additional codes are `zh-Hans`, `es`, `pt`, `fr` and `de`.

## Where are settings stored, and how do I remove them?

The default folder is `%LOCALAPPDATA%\AntiBotPCExplorer`; the fallback is `%TEMP%\AntiBotPCExplorer`. It contains the HMAC key, language selection and WebView2 profile. Close the application before deleting the folder. An optional TPM demonstration key is removed separately with **Delete key** on the TPM page.

## How do I report an issue or suggest a feature?

Use [GitHub Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues). Include the application version, Windows version, the affected page, reproduction steps and the result you expected. The [contribution guide](../CONTRIBUTING.md) describes the feedback workflow, and the [security policy](../SECURITY.md) describes vulnerability reporting. Product websites: [detect.expert](https://detect.expert), [anti.bot](https://anti.bot) and [antidetect.com](https://antidetect.com).
