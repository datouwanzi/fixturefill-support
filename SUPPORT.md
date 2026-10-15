# Support

Applies to FixtureFill **0.1.2**, published by **Kynastro**.

## Troubleshooting

1. Confirm the installed FixtureFill version and your browser version. Start with a simple test page in Microsoft Edge; behavior in other Chromium browsers may vary.
2. Open a regular web page, then explicitly open FixtureFill and click **Fill form**. Browser settings pages, extension pages and protected browser pages cannot be filled. After navigating to another page, invoke FixtureFill again.
3. If the popup remains at **Loading settings…**, reopen it. For a developer-provided unpacked build, load the complete runtime directory containing `manifest.json` and its referenced scripts, not the full development project or an HTML file opened directly. Reload the extension after updating its files.
4. Check that the affected control is visible and editable. Passwords, file inputs, hidden, disabled and read-only controls are excluded. See [Known Issues](KNOWN-ISSUES.md) for unsupported controls and page structures.
5. Repeat with the same seed, mode, page and form structure. Use a disposable form: filling overwrites supported values, and the website may autosave in response to events.
6. For React/Vue problems, compare the visible control with the application's state after a re-render. Report a mismatch using a minimal example with synthetic values.
7. Check existing issues before opening a new report. Use the Bug report form for failures, Compatibility report for a particular website/framework/control, or Feature request for an improvement.

For local test files, the browser may require its per-extension **Allow access to file URLs** setting. Enable it only if you intend to test local files.

## What to include

- FixtureFill version.
- Microsoft Edge / Chrome version, or the exact Chromium browser and version.
- Operating system and version.
- Website or framework, only if safe to disclose. A framework name and a sanitized minimal example are sufficient; no private URL is required.
- Mode: Normal, Edge or Invalid.
- A non-sensitive seed that reproduces the issue. If the original seed is sensitive, substitute a synthetic seed and say whether the issue still occurs.
- Affected field/control type.
- Expected behavior and actual behavior, including any error text after redaction.
- Numbered reproduction steps and whether the issue occurs consistently.
- A screenshot if useful, with sensitive details removed before upload.

> Do not include passwords, authentication credentials, personal information, confidential production data, or other sensitive information in issue reports or screenshots.

Public issues and attachments are visible to others. Remove tokens, session IDs, private URLs and identifying information from examples, browser address bars and screenshots. Do not upload full page dumps or browser profiles. See [Security](SECURITY.md) for concerns that require a private channel.
