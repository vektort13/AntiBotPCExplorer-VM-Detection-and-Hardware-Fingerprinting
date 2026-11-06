# Features

[Home](../README.md) · [Installation](installation.md) · [FAQ](faq.md) · [Privacy and local data](privacy.md)

AntiBotPCExplorer brings device identity, hardware inventory and Windows platform security into one local inspector. It runs in user mode, uses the existing Windows interfaces and needs no kernel driver.

## Four explainable scores

The Overview shows a score from 0 to 100 for each area, with the contributing items displayed beneath it.

| Score | What it describes |
| --- | --- |
| Device identity | Available hardware and installation anchors, including TPM, firmware, storage and network identifiers |
| Platform integrity | Boot and kernel protection evidence: TPM, Secure Boot, VBS, HVCI, IOMMU and related settings |
| Driver trust | The signing classes of running kernel drivers and the system's code integrity settings |
| Physical PC Confidence | Virtualization evidence, source availability and the independent evidence groups behind the result |

The scores use weighted rules, and each page exposes the underlying observations and checks.

## VM Detection

The dedicated VM Detection page organizes guest and cloud infrastructure evidence into categories. Each executed check includes a status, weight, score contribution and technical detail. The page also contains a catalog of 100 methods and ten weak heuristics, with their implementation status and links to relevant executed checks.

The model groups related observations so correlated firmware or device signals do not repeatedly contribute the same evidence. Hyper-V or VBS running on a physical host is interpreted in its host context. Remote sessions and passive debugger, Sandboxie, Comodo and Wine checks are shown as context with zero VM score weight.

## Hardware and system inventory

| Page | Highlights |
| --- | --- |
| Identifiers | Discovered identifiers, their uniqueness scope, weight, identity group and source |
| CPU & FPU | CPU features, logical processor topology, caches and deterministic floating-point profiles |
| Firmware | SMBIOS, ACPI, firmware update information, Secure Boot certificates and boot configuration |
| Storage | Disk and controller identifiers, multiple storage query paths, partitions and volumes |
| Network | Current and permanent MAC addresses, interface IDs, known networks, Bluetooth devices and mobile modem information |
| Display & power | Graphics adapters, connected displays, EDID, display modes and batteries |
| PnP devices | Device identifiers, drivers, PCIe link information, audio endpoints, biometric sensors, smart-card readers and printers |
| TPM | TPM properties, endorsement keys and certificates, PCRs, Measured Boot log and Windows provisioning records |
| Platform security | Secure Boot, VBS/HVCI, code integrity, IOMMU and Security Center product state |
| Microsoft & cloud | Windows licensing status, Microsoft service identifiers, Entra join, MDM/Intune and Autopilot information |
| Kernel drivers | Running kernel drivers, signature classifications and publisher summaries |
| Windows | Installation identifiers, OS information, upgrade lineage, user profile metadata and machine certificates |
| Raw JSON | The current local snapshot, with sensitive values following the interface's reveal setting |

Available detail depends on the hardware, Windows configuration and access rights. Unavailable sources have explicit status messages in the interface.

## Independent cross-checks

The application compares observations obtained through different sources. Examples include CPU information against firmware, graphics adapters against device inventory, current and permanent network addresses, storage serials across query methods, and TPM information against firmware and Windows records. Measured Boot events can be replayed against current PCR values. Disagreements appear alongside the observations.

## Compare snapshots

Load two saved JSON reports, or use the current scan in either slot. The application compares identity groups such as TPM, motherboard, storage, network, graphics, firmware, CPU, Windows installation and memory.

The result includes a matching score and a breakdown by group. Built-in simulation scenarios let you explore how a Windows reinstall, component upgrade or hardware replacement affects the comparison. A button opens the same pair in Report diff.

## Report diff

Compare two reports field by field: report metadata, scores and contributing items, cross-checks, identifiers and tables. Red highlights mark changed fields and rows present in only one report. Filters can show differences only and ignore volatile fields such as scan time or uptime. Section links jump directly to the relevant comparison table.

You can load reports with a file picker or drag a JSON file onto a slot. Sensitive values remain hidden until you choose **Show identifiers**. Reports using the same local key can compare their protected identifiers; values protected with different keys are marked as not comparable.

## Reports and languages

Export a privacy-safe JSON report with sensitive fields replaced by HMAC tags, or a raw JSON report with the collected original values. Both formats can be loaded back into the comparison tools. Collection and export also work from the [command line](installation.md#export-without-opening-a-window).

The executable contains the full interface and nine languages: English, Russian, Vietnamese, Simplified Chinese, Traditional Chinese, Spanish, Brazilian Portuguese, French and German.

## Optional TPM key demonstration

The TPM page can create a non-exportable ECDSA P-256 demonstration key, sign and verify a fresh challenge, and delete the key. These actions run only when requested. The `--selftest` command performs a separate temporary-key round trip and removes its test key afterward.

## Version 1.4.0

This release introduces Physical PC Confidence and the dedicated VM Detection page, expands virtualization diagnostics and their translations, improves high-DPI window sizing and navigation, and updates privacy masking for Hyper-V information. See the [changelog](../CHANGELOG.md) and [release notes](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/tag/v1.4.0).
