# Privacy and data handling

**Publisher:** Kivoraft  
**Product:** FixtureFill — Deterministic Form Filler for QA  
**Applies to:** Version 0.1.0  
**Last updated:** October 3, 2026

## Local operation

FixtureFill does not collect personal data for Kivoraft, or transmit, sell or share personal data. It has no analytics or telemetry, requires no account, and uses no remote servers, external APIs (including AI APIs) or remote code. The extension does not send page content, generated values or settings to Kivoraft or another service.

Local-only does not mean that the extension never accesses page information. When explicitly invoked to fill a form, FixtureFill processes the current authorized page's field types, names, labels, options and constraints locally. It uses the page's origin, path and hash route to generate repeatable values; query parameters are excluded from that page identity. For local files, the path can affect the result. These details may contain personal or private information, so use authorized test pages and synthetic data.

FixtureFill does not run continuous page monitoring or fill other tabs automatically. Password field values are not read or filled.

## Local settings

The seed and selected mode are saved in the browser's extension-local storage when **Fill form** is clicked, and restored when the popup is reopened. FixtureFill does not use browser sync storage. Do not put passwords, tokens or other secrets in a seed.

FixtureFill does not persist page URLs, existing form contents or generated personas. Replace the seed/mode and click Fill form on an authorized test page to replace the saved settings. Removing the extension removes its extension-local settings.

## Page events

FixtureFill changes supported editable fields and may dispatch standard `input` and `change` events. Checkbox/radio updates may also dispatch a generic `click` event for framework compatibility; Invalid mode preserves radio groups without dispatching these events to them.

FixtureFill never automatically submits forms. Websites may independently react to the dispatched events, autosave values, make network requests or perform other actions under their own policies. FixtureFill cannot prevent those website behaviors.

## Permissions

| Permission | Purpose |
| --- | --- |
| `activeTab` | Temporary access to the current page following a user action. |
| `scripting` | Execute the extension's bundled local detection and filling code on that authorized page. |
| `storage` | Save the seed and mode locally. |

FixtureFill does not request permanent access to all websites.

## Support reports

This policy describes the extension. Information you deliberately submit to a GitHub issue is a separate support interaction: public issues and attachments can be read by Kivoraft and other people and are hosted by GitHub under [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). Do not submit personal or sensitive information. Follow [SECURITY.md](SECURITY.md) for private security/privacy concerns and [SUPPORT.md](SUPPORT.md) for ordinary troubleshooting.
