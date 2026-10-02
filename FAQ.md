# Frequently asked questions

## What does deterministic mean?

With the same seed, page identity, mode, field structure and generator version, FixtureFill reproduces the same generated test data. Page identity includes origin, path and hash route, but not query parameters. Changing controls, their order or constraints can change the output. Skipped controls retain their existing values.

## What does the Seed do?

The seed selects a repeatable data variant. Reuse a non-sensitive seed to reproduce a test, or change it to try a different variant. It is not a password or secret. The seed and mode are stored locally when you click Fill form.

## What is the difference between Normal, Edge and Invalid?

- **Normal:** typical synthetic data matched to supported fields and native constraints where possible.
- **Edge:** supported length/numeric boundaries and Unicode values. It does not exercise every possible boundary.
- **Invalid:** missing or malformed values where supported. Browser normalization or website logic may prevent some invalid values. All radio groups are preserved and skipped in 0.1.0.

None of these modes guarantees that a website's custom business validation will accept or reject every generated value.

## Does FixtureFill send data to a server?

No. It uses no telemetry, remote server, external API or remote code. The website being tested may independently react to field changes and send its own requests. See [Privacy](PRIVACY.md).

## Does it fill passwords?

No. Password field values are neither read nor filled.

## Does it submit forms?

No. It never clicks a submit button or calls a form submission method. Website event handlers may still trigger autosave or other page behavior.

## Why was a radio group skipped in Invalid mode?

Clearing a radio visually may leave a framework's internal value unchanged. FixtureFill 0.1.0 conservatively skips **all radio groups** in Invalid mode because controlled ownership cannot be reliably identified through the DOM. Their original state is preserved and the result reports the skip. Normal and Edge can still select radio options.

## Does it support React/Vue?

Common native controls managed by React/Vue are supported on a best-effort basis using native setters and standard events. Compatibility is not universal. Invalid select clearing has been verified for common controlled single-select controls with an existing empty-value option. Custom components and application-specific handlers may behave differently. Use the Compatibility report form for a sanitized reproduction.

## Does it support Shadow DOM or iframes?

No. Version 0.1.0 targets the main document. It does not traverse shadow roots or fill iframe contents.

## Why did a field remain unchanged?

It may be excluded, unsupported, non-editable, or modified again by the website. Password, file, hidden, disabled and read-only inputs are skipped. Check [Known Issues](KNOWN-ISSUES.md) and the popup's result before reporting a failure.

## Does closing the popup save my changes?

Seed and mode are saved when Fill form is clicked. Merely editing them and closing the popup does not save those edits.
