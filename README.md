# MaxAgent

**AI assistant for Autodesk 3ds Max** — a native C++ plugin that brings a large-language-model chat panel into your 3ds Max session. Describe what you want in plain language and MaxAgent builds, edits, and inspects the scene for you: create and modify objects, analyze DWG/DXF plans, generate geometry, control materials, animation, and more.

> This repository is the **public distribution channel** for MaxAgent plugin binaries. It contains no source code — only released installers and release information. Download the ZIP matching your 3ds Max version from the [Releases](https://github.com/N4eem/MaxAgent/releases) page.

---

## Features

- **Natural-language scene control** — "build a room", "make an office chair", "move all cameras to this grid" — the model turns your request into 3ds Max operations.
- **CAD plan analysis** — import a DWG/DXF floor plan and MaxAgent builds the room geometry: walls, floor, roof panels with ridge/eave geometry, and furniture.
- **Scene inspection & editing** — objects, modifiers, materials, animation keys, splines, state sets, render settings, viewports, and scene units.
- **Multi-model support** — works with the model/router you configure (OpenAI-compatible endpoints, plus built-in free-tier support).
- **Streaming chat** — real-time streaming responses with network-loss retry and resume, so long operations survive connection hiccups.
- **94+ native tools** — a curated set of scene tools registered by the plugin, exposed to the model for reliable, deterministic scene edits.

## Supported 3ds Max versions

| 3ds Max | Download |
|---|---|
| 2020 | `MaxAgent-2020-vX.Y.Z.zip` |
| 2021 | `MaxAgent-2021-vX.Y.Z.zip` |
| 2022 | `MaxAgent-2022-vX.Y.Z.zip` |
| 2023 | `MaxAgent-2023-vX.Y.Z.zip` |
| 2024 | `MaxAgent-2024-vX.Y.Z.zip` |
| 2025 | `MaxAgent-2025-vX.Y.Z.zip` |
| 2026 | `MaxAgent-2026-vX.Y.Z.zip` |
| 2027 | `MaxAgent-2027-vX.Y.Z.zip` |

Each build is compiled against its own Autodesk SDK. **A `.gup` built for one 3ds Max version must not be used in another version's Plugins folder** — always download the ZIP matching your exact 3ds Max version.

## Installation

1. **Close 3ds Max.**
2. Go to the [Releases](https://github.com/N4eem/MaxAgent/releases) page and download the ZIP matching your 3ds Max version.
3. Extract the ZIP. You'll get:
   - `max_agent.gup` — the plugin binary
   - `WebView2Loader.dll` — Microsoft WebView2 loader
   - `How to install.txt` — install notes + version info
4. Copy these files into your 3ds Max **Plugins** folder, e.g.:
   ```
   C:\Program Files\Autodesk\3ds Max 2027\Plugins
   ```
5. Open 3ds Max. MaxAgent appears as a Global Utility — open the **Utilities** panel to find it.

### Requirements

- **Microsoft Edge WebView2 Runtime** (usually pre-installed on Windows 11; on Windows 10 install it from [Microsoft's site](https://developer.microsoft.com/en-us/microsoft-edge/webview2/)).
- An active internet connection to reach the AI provider configured in the panel.

## Updating

1. Download the newest ZIP for your 3ds Max version from [Releases](https://github.com/N4eem/MaxAgent/releases).
2. Close 3ds Max, replace the files in your Plugins folder, restart 3ds Max.

The panel footer shows the installed plugin version and bridge protocol version so you can confirm what's running.

## Uninstall

Close 3ds Max and delete these files from your Plugins folder:
```
max_agent.gup
WebView2Loader.dll
```

## Versioning & compatibility

MaxAgent uses independent versions for three components (see each release's notes for exact values):

- **Plugin version** — the C++ plugin binary (`plugin-vX.Y.Z` releases).
- **Frontend version** — the web panel UI (updated independently).
- **Bridge protocol version** — the contract between the panel UI and the plugin.

If the panel reports a **bridge protocol mismatch** or **plugin update required**, download the latest release for your 3ds Max version — your installed plugin is incompatible with the panel version you're running.

## Release information

Each release includes:

- 8 ZIP installers (one per supported 3ds Max version)
- **What's New / Fixes** — user-facing changelog from the commit history
- **Compatibility** — supported 3ds Max versions, plugin version, bridge protocol version
- `manifest.json` — SHA-256 checksums for every installer ZIP

## License & source

MaxAgent's source code is **closed and private** — it is not published here. This repository exists solely to distribute the compiled plugin binaries and release notes.

## Support

- For bugs or feature requests, open an issue (maintainer review required).
- Persian & English supported.

---

*MaxAgent — AI-assisted 3ds Max workflow.*
