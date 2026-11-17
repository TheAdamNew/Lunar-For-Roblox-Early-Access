# Lunar for Roblox — Early Access

> **Status: Early Access (indefinite).** The official package servers are retired.
> The setup still installs offline. The vibes remain.

Unofficial archive of the **Lunar for Roblox 1.0.16** Windows x64 installer, its
application package, and the decompiled application source.

Lunar for Roblox is a Roblox launcher by **Moonsworth, LLC** (the team behind
Lunar Client). The official distribution was taken down and the official package
server no longer serves this version. The installer here is the original, signed
Moonsworth binary, and it installs **fully offline** as long as the `.nsis.7z`
package sits next to it.

## Contents

| File | Size (bytes) | Where | SHA-256 |
| --- | ---: | --- | --- |
| `lunar-for-roblox-1.0.16-setup.exe` | 1,195,832 | repo + release | `293D56328BB70CD5121BF6BEB95A586030CEAF7BDE4BAAAE94A91169B2973F27` |
| `lunar-for-roblox-1.0.16-x64.nsis.7z` | 127,164,340 | release only¹ | `64EAFC222C3712F1903A48ADAFE77840B1BD63E2D2CF15C3EF257D228ED257FF` |
| `src/` | 9.98 MB | repo | decompiled app source (main / preload / renderer) |

¹ GitHub rejects files over 100 MB in a normal repository, so the package is
attached to the [latest release](../../releases/latest). Keep it next to
`setup.exe` when installing.

SHA-512 of the package (the value hardcoded in `setup.exe` for verification):

```
97C042A7F202992D6448DF2D586A9298E9ACA94B650757A68278E428A54F4AB4F6125594AF6EABF96DAEAE2797EB0AA89FE7D5DCD640D60DD8F06F64A184F923
```

## Install

1. Download both binaries from the [latest release](../../releases/latest) into
   the **same folder**.
2. Run `lunar-for-roblox-1.0.16-setup.exe`.
3. The installer finds the local package, verifies its SHA-512 against the
   expected value, and installs without downloading anything. No admin rights
   needed.

- Default install location: `%LOCALAPPDATA%\Programs\lunar-for-roblox`
- Uninstaller: `Uninstall LunarForRoblox.exe` in that folder (also listed in
  Settings → Apps as "Lunar for Roblox")
- Silent install: `lunar-for-roblox-1.0.16-setup.exe /S`

**Important:** if the `.7z` is missing, renamed, or modified, the installer
ignores it, tries the official update server (which is gone), and the
installation fails.

## Verification

- `setup.exe` — Authenticode status **Valid**, signer `CN="Moonsworth, LLC"`
  (Sectigo EV code signing), countersigned by DigiCert timestamping.
- `LunarForRoblox.exe` inside the package — same Moonsworth signer.
- Package SHA-512 matches the constant embedded in the installer.
- Windows Defender scan of both binaries and the installed folder: no detections.

## Source (`src/`)

Decompiled application source (`main`, `preload`, `renderer` bundles and
`package.json`) from the public mirror
[`chiikabu/lunar-for-roblox-decompiled`](https://github.com/chiikabu/lunar-for-roblox-decompiled).
It is not official and is not required to install the app.

## Notes

- The app still performs normal runtime network activity (update checks,
  Overwolf packages, telemetry). Since the distribution was shut down, some
  online features may not work.
- The installer is signed, but the app itself is **beta and discontinued** —
  treat it accordingly. It is, after all, still in Early Access.

## Legal

Unofficial mirror, provided for preservation and compatibility. "Lunar for
Roblox", the application, and its source are © Moonsworth, LLC. This project is
not affiliated with or endorsed by Moonsworth, LLC or Roblox Corporation.
Redistribution of the binaries requires permission from the rights holder; this
archive will be removed at the rights holder's request.
