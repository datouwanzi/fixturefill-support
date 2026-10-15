# Known issues and compatibility limits

Applies to FixtureFill **0.1.2**.

| Area | Current behavior |
| --- | --- |
| Shadow DOM | Unsupported; shadow roots are not traversed. |
| Iframes | Unsupported; only the main document is processed. |
| Custom components | No dedicated support for custom elements, ARIA-only widgets or custom component state APIs. Native controls exposed in the main document may work, but compatibility is not guaranteed. |
| Invalid radio clearing | Controlled radios can retain framework state after visual clearing. Version 0.1.2 therefore preserves and skips **all** radio groups in Invalid mode, including native groups. Normal/Edge selection remains available. |
| Controlled selects | Invalid clearing is verified for common React/Vue single-select controls with an existing empty-value option. Other cases may be normalized or overridden by the application. |
| Page event handlers | Websites may respond to `input`/`change`, and checkable-control compatibility events, by autosaving or performing other actions. FixtureFill does not automatically submit forms. |
| Validation | Native constraints and custom business validation differ. Browser-enforced values may prevent an intended Invalid case; Normal values are not guaranteed to satisfy every website rule. |

Password, file, hidden, disabled and read-only inputs are intentionally excluded. The extension cannot fill browser-internal or other protected pages. Filling happens once per invocation; dynamically inserted controls may require another invocation.

For a compatibility issue, include browser/framework versions, the control type, mode, a non-sensitive seed, and a minimal example using synthetic values. Compare the DOM and framework state after a re-render when relevant. Follow the disclosure precautions in [Support](SUPPORT.md).

These limitations describe current behavior, not a commitment to implement additional features.
