# FixtureFill

**FixtureFill — Deterministic Form Filler for QA** · Published by **Kivoraft** · Version **0.1.0**

FixtureFill is a Manifest V3 browser extension for repeatable form testing in Microsoft Edge and compatible Chromium browsers. It is intended for developers and QA engineers working on their own or authorized test pages.

The same seed, page identity, mode and field structure reproduce the same generated test data within the same generator version. Changing the seed creates a different variant. Changes to the page or its controls can change the result.

| Mode | Purpose |
| --- | --- |
| Normal | Generate typical synthetic values within supported native constraints. |
| Edge | Exercise supported length limits, numeric bounds and Unicode handling. |
| Invalid | Attempt missing or malformed values. Radio groups are preserved and skipped for safety in 0.1.0. |

FixtureFill runs locally, requires no account, and uses no telemetry, external API or remote code. It does not read or fill password fields and never submits forms automatically. Websites may independently react to field changes, including autosaving.

## Documentation and support

- [Support and troubleshooting](SUPPORT.md)
- [Privacy and data handling](PRIVACY.md)
- [Frequently asked questions](FAQ.md)
- [Known issues and compatibility limits](KNOWN-ISSUES.md)
- [Security and privacy concerns](SECURITY.md)

To report a problem, first check Support and Known Issues, then open this repository's **Issues → New issue** and choose Bug report or Compatibility report. Use Feature request for proposed improvements. Include a minimal reproduction with synthetic data; never post sensitive information.

This repository contains public support documentation and issue forms. It is **not** the FixtureFill source-code repository and does not contain extension builds or development dependencies.
