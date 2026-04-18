# HelloWord

Minimal local-packaging desktop app built with `Tauri + React + pnpm`.

Current scope:

- Minimal page that only shows `HelloWord`
- Frontend powered by `Vite + React`
- Desktop shell powered by `Tauri v2`
- Windows target: `.exe` via NSIS
- macOS target: `Apple Silicon .dmg`
- Icon source file: `./logo.png`

## Requirements

Recommended versions based on the official docs:

- Node.js `20.19+`
- `pnpm`
- Rust `stable-msvc`
- Microsoft C++ Build Tools on Windows
- WebView2 on Windows

References:

- [Tauri prerequisites](https://v2.tauri.app/start/prerequisites/)
- [Tauri Vite integration](https://v2.tauri.app/start/frontend/vite/)
- [Tauri icons](https://v2.tauri.app/develop/icons/)
- [Vite Getting Started](https://vite.dev/guide/)

## Install dependencies

```powershell
corepack enable
corepack prepare pnpm@latest --activate
pnpm install
```

If Rust is not installed yet:

```powershell
winget install --id Rustlang.Rustup
rustup default stable-msvc
```

## Generate app icons

Desktop packaging usually needs platform icon files such as `icon.ico` for
Windows and `icon.icns` for macOS. This project uses `./logo.png` as the icon
source.

After installing dependencies, run:

```powershell
pnpm run icons
```

That generates icon assets into `src-tauri/icons/`.

## Run locally

```powershell
pnpm tauri dev
```

## Run tests

```powershell
pnpm test
```

## Build locally

```powershell
pnpm tauri build
```

Common output folders:

- Windows: `src-tauri/target/release/bundle/nsis/`
- macOS: `src-tauri/target/release/bundle/dmg/`

Notes:

- On Windows, you can normally build only the Windows installer locally.
- The `Apple Silicon .dmg` must be built on a macOS Apple Silicon machine.
- `src-tauri/tauri.conf.json` already targets `nsis + dmg`, so the same config
  can later be reused in GitHub Actions.
