# Security

## Supported release

Security reports are accepted for the latest published release, currently **1.4.0**. Download it from [GitHub Releases](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/releases/latest).

## Report a vulnerability

Use [GitHub's private vulnerability reporting form](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/security/advisories/new) to send a report to the maintainers.

Include the application version, Windows version, steps to reproduce, the observed impact and a minimal example where possible. Attach only the data needed to demonstrate the issue. Use the private report for vulnerability details and sensitive attachments.

For ordinary bugs and usage questions, use [Issues](https://github.com/vektort13/AntiBotPCExplorer-VM-Detection-and-Hardware-Fingerprinting/issues).

## Verify a download

Official release executables are digitally signed by **Vektor T13 Technologies B.V.** The release includes `SHA256SUMS.txt`; the [installation guide](docs/installation.md) explains how to compare the SHA-256 hash and inspect the Windows signature.

## Diagnostic data

The application collects diagnostics locally. Identifiers are hidden in the interface by default, and the standard JSON export uses HMAC tags. Raw exports contain the original values. See [Privacy and reports](docs/privacy.md) for local storage, export options and sharing reports.
