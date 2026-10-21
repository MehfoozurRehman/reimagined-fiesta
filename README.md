# reimagined-fiesta

An electron-vite starter for a desktop app that renders React in an Electron window.

**Status:** Starter. The renderer still shows the electron-vite template screen, and there is no app-specific feature beyond the template's IPC ping and version display.

## The problem

The code does not yet solve a problem. It is the electron-vite template, set up as the starting point for a desktop app.

## What it does

- Starts an Electron app with a main process (`src/main/index.js`) and a preload script (`src/preload/index.js`).
- Renders a React page (`src/renderer/src/App.jsx`) with the template's text and links.
- Has a "Send IPC" link that sends a `ping` message from the renderer to the main process.
- Includes a `Versions` component in the renderer.
- Configures builds for Windows, macOS and Linux through `electron-builder`, with `electron-updater` listed as a dependency.

## How it's built

- electron-vite with Electron 28, React 18, Vite 5, and `electron-builder` for packaging.
- The renderer is a standard Vite React app under `src/renderer/`. The main and preload processes are built separately.
- ESLint and Prettier are configured through the `.eslintrc.cjs` and `.prettierrc.yaml` files.

## Running it locally

The repo includes a `pnpm-lock.yaml`, so install with pnpm:

```bash
pnpm install
pnpm dev
```

`pnpm dev` runs `electron-vite dev`. To package the app, run `pnpm build`, then `pnpm build:win`, `pnpm build:mac` or `pnpm build:linux`.

## What's left

- The renderer still shows the template text ("Powered by electron-vite") and the template's links.
- No application features exist beyond the template.
- There are no tests.
- The packaging targets have not been checked from this repository.
