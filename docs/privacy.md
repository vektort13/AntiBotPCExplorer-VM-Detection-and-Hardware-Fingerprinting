# Privacy and local data

[Home](../README.md) · [Installation](installation.md) · [Features](features.md) · [FAQ](faq.md)

## Local operation

AntiBotPCExplorer collects and analyzes data on the computer where it runs. Its interface is embedded in the executable. Scanning, comparisons, signature checks and report export do not make network requests. The embedded WebView2 interface blocks navigation to other pages; its background networking and crash-report uploads are disabled. The two product website buttons open [anti.bot](https://anti.bot) or [detect.expert](https://detect.expert) in the default browser.

The scan runs in user mode without a kernel driver. Normal collection reads existing data. The optional TPM key actions, exported report files and local application data are described below.

## On-screen values

The interface hides fields marked sensitive until **Show identifiers** is selected and confirmed. These include serial numbers, hardware UUIDs, MAC addresses, key fingerprints and selected personal or network information. The Raw JSON page follows the same setting.

System context, model names, security state, diagnostic results and fields not marked sensitive remain readable. Revealing values on screen does not change the export mode.

## Report formats

| Export | Contents |
| --- | --- |
| Privacy-safe report | Sensitive fields replaced by HMAC-SHA256 tags; tables excluded from safe export are omitted |
| Raw diagnostic report | Original collected values, including sensitive identifiers |

The privacy-safe format preserves useful diagnostic context and permits comparisons through consistent tags. It includes system information and identifiers that are not marked sensitive. A report is saved only when you choose an export action or supply a command-line output path.

The HMAC key is generated locally. Two reports using the same key can compare their protected values. When reports use different keys, the comparison tools mark those values as not comparable.

## Stored files

The default local data directory is:

```text
%LOCALAPPDATA%\AntiBotPCExplorer
```

If that directory is unavailable, the application uses `%TEMP%\AntiBotPCExplorer`.

| File or folder | Purpose |
| --- | --- |
| `hmac.key` | Local key used to create stable tags for sensitive report values |
| `language.txt` | Saved interface language |
| `WebView2\` | Embedded interface's browser profile |

JSON reports are written to the path chosen in the Save dialog or supplied on the command line. They are separate from the settings directory.

To reset local application data, close the program and delete its data directory. This resets the language and HMAC key. Protected values in reports exported before and after the reset can no longer be matched through their tags. If an existing key file cannot be read, it is left in place and the current session uses a temporary key.

## Optional TPM keys

The TPM page creates the non-exportable demonstration key `AntiBotPCExplorer-DeviceKey` only when you choose the create action. **Delete key** removes it. Deleting the executable or the local data directory does not remove that TPM key.

The `--selftest` command uses a separate temporary key, signs and verifies a challenge, and removes its test key afterward.

## Data not collected

The inspector does not read Windows product keys, BitLocker data, Windows Hello key containers, TPM owner authorization or cellular subscriber identifiers such as IMSI and ICCID. Windows licensing information is limited to descriptive status and identifiers, without product keys. OneDrive inspection reads relevant device identifiers rather than account contents.

## Feedback and security reports

For reproducible application issues, follow [CONTRIBUTING.md](../CONTRIBUTING.md). For vulnerability reporting, follow [SECURITY.md](../SECURITY.md).
