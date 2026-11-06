# Changelog

The latest executable is available in [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).

## 1.4.0 — 2026-11-05

### Added

- **VM Detection** page with grouped checks, five result statuses, evidence weights, score contributions and detailed explanations.
- **Physical PC Confidence**, the fourth diagnostic score on the Overview page.
- Expanded virtualization diagnostics covering CPU and topology, firmware, PCI/PnP devices, storage, network adapters, graphics, displays and guest integration components.
- A reference catalog covering 100 methods and 10 additional heuristics, including implementation status and links to available checks.
- Passive context checks for debugger, sandbox compatibility layers, Wine and remote sessions, kept separate from the VM score.
- New diagnostic results in exported reports and all nine interface languages.

### Improved

- Evidence grouping accounts for related signals, unavailable sources, physical-host adapters and cloud bare-metal configurations.
- Hyper-V and VBS on a physical host are distinguished from guest VM evidence.
- TPM reading and boot-log parsing, including clearer error classification.
- Embedded translation packaging within WebView2 page-size limits.

### Fixed

- Long navigation labels, sidebar scrolling and access to bottom navigation items.
- Initial and minimum window sizing on high-DPI monitors; toolbar wrapping and dropdown placement in narrow windows.
- Masking of Hyper-V VM identifiers, VM names and generation identifiers in privacy-safe reports.
- Chinese interface strings with damaged encoding.

This is the first version distributed through this public product repository.
