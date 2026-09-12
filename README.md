<img src="docs/icon.png" width="88" alt="MouseTuner">

# MouseTuner

[English](README.md) · [简体中文](README.zh-CN.md)

A menu bar app that gives any mouse on macOS the behavior the system leaves out.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/scroll-dark.webp">
  <img alt="The Scrolling panel, showing the Scroll Curve, its parameters and a live preview" src="docs/shots/scroll-light.webp">
</picture>

The Scrolling panel: the Scroll Curve, its five parameters, and a preview that reacts while you drag.

## What it does

- **Smooth scrolling.** Replaces the discrete steps of a wheel mouse with pixel-level inertial scrolling. Trackpads and the Magic Mouse pass through untouched.
- **Scroll inversion.** Flips wheel direction on its own, independently of the system's natural scrolling, so a mouse and a trackpad no longer have to agree.
- **Scroll curve editor.** Tune minimum step, gain, duration and decay, and feel the change as you drag.
- **Button mapping.** A trigger can be a click, a double click, a long press, a four-way drag, a chord of two buttons, or hold plus scroll. An action can send a keyboard shortcut, run a system action, open an app or a URL, or run a script.
- **Modifier hold.** Hold a mouse button to hold a modifier key such as Fn, and release it on button up. This is the hardware half of push-to-talk dictation.
- **Pan while held.** Turn pointer movement into scrolling while a button is down, the way a hand tool works in a map or a canvas.
- **Per-app overrides.** Scroll curves and button mappings can change with the frontmost app.
- **Input source switching.** Switch input sources automatically by app, or by the domain of the current browser tab.
- **Logitech hardware control.** On a recognized device, read and write DPI, SmartShift and battery level over HID++, the protocol the vendor's own software speaks. No vendor software has to be running.

Smooth scrolling and button mapping work with any mouse. The hardware controls need a device MouseTuner recognizes.

## Screens

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/buttons-dark.webp">
  <img alt="The Button Mapping panel, showing triggers and the actions they fire" src="docs/shots/buttons-light.webp">
</picture>

Button Mapping: a button holds a list of triggers, and every trigger points at exactly one action. Both can be overridden per app.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/device-dark.webp">
  <img alt="The Device panel, showing DPI, SmartShift and battery for a recognized mouse" src="docs/shots/device-light.webp">
</picture>

Device: DPI, SmartShift and battery level, read and written over HID++ on a mouse MouseTuner recognizes.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/shots/inputsource-dark.webp">
  <img alt="The Input Source panel, showing per-app and per-domain rules" src="docs/shots/inputsource-light.webp">
</picture>

Input sources: switch by app, or by the domain of the current browser tab.

## Requirements

macOS 13.3 or later. Universal binary for Apple silicon and Intel.

## Install

Download [MouseTuner.dmg](https://github.com/mousetuner/mousetuner/releases/latest/download/MouseTuner.dmg) — signed with a Developer ID and notarized, under 4 MB — or install it with Homebrew:

```
brew install --cask mousetuner/tap/mousetuner
```

On first launch MouseTuner asks for Accessibility permission. Scrolling and button mapping cannot work without it, because both rely on intercepting system input events. Input Monitoring is *not* required.

## Price

$9.90 once, or ¥68 in China. Not a subscription.

One license key activates up to 3 machines and includes updates for the life of the license. Before buying there is a 30-day trial with every feature unlocked, no account and no payment method. Refunds are 14 days, no questions asked.

## Privacy

No account. No analytics. No crash reporter.

The app makes exactly four network requests of its own: registering the trial on first launch, activating a license, one revocation check per day, and deactivating. Each request body contains only a license key hash and a machine fingerprint hash — never an account, never anything about how you use the app. The full list, with the trigger and payload of each, is published at [mousetuner.com/privacy](https://mousetuner.com/privacy) so it can be checked against a packet capture.

## Compared with Logi Options+

MouseTuner covers the hardware controls most people install Options+ for — DPI, SmartShift, battery, thumb buttons — and adds smooth scrolling and per-app overrides, which Options+ does not do. It also works on non-Logitech mice, which Options+ structurally cannot.

It does **not** replace Flow (one mouse across several computers), firmware updates, Logitech keyboards, or the Actions Ring. If you need any of those, keep Options+ — the two run side by side.

Side-by-side table: [mousetuner.com/logi-options-plus-alternative](https://mousetuner.com/logi-options-plus-alternative)

## Supported mice

Smooth scrolling and button mapping work with **any** mouse macOS can see. Only the HID++ hardware controls need a recognized device.

The current list covers 16 Logitech models (MX Master, MX Anywhere, MX Ergo, MX Vertical, M720 and others). Their model names and product IDs come from libratbag, the open-source Linux device database — that proves a device speaks HID++, but not which capabilities it exposes, so every row is marked *recognized, hardware controls not yet verified*. Verifying them needs captures from real hardware; if you have one of these mice, a capture is the most useful thing you can contribute.

Current list: [mousetuner.com/compatibility](https://mousetuner.com/compatibility)

## Links

- Website: [mousetuner.com](https://mousetuner.com)
- Documentation — every trigger and action, the settings panels, the glossary: [mousetuner.com/docs](https://mousetuner.com/docs)
- Changelog: [mousetuner.com/changelog](https://mousetuner.com/changelog)
- Bug reports and device captures: [Issues](https://github.com/mousetuner/mousetuner/issues)

The app ships in English, Simplified Chinese, Traditional Chinese, Japanese, Korean, German, French and Spanish.
