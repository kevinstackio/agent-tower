# HelloWord Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a minimal `pnpm + React + Tauri` desktop app that renders only `HelloWord` and can be packaged locally.

**Architecture:** Use a Vite-powered React SPA for the frontend and a minimal Tauri v2 Rust shell for desktop packaging. Keep the UI deliberately tiny and push packaging guidance into `README.md` so local setup stays clear.

**Tech Stack:** React, Vite, Vitest, Tauri v2, Rust, pnpm

---

### Task 1: Create the frontend shell

**Files:**
- Create: `package.json`
- Create: `index.html`
- Create: `vite.config.js`
- Create: `src/main.jsx`
- Create: `src/App.jsx`
- Create: `src/styles.css`

- [ ] Step 1: Write the failing UI test for the `HelloWord` heading.
- [ ] Step 2: Run the test to verify it fails because the component does not exist yet.
- [ ] Step 3: Implement the smallest React app that renders `HelloWord`.
- [ ] Step 4: Run the test to verify it passes.

### Task 2: Add desktop packaging

**Files:**
- Create: `src-tauri/Cargo.toml`
- Create: `src-tauri/build.rs`
- Create: `src-tauri/src/main.rs`
- Create: `src-tauri/capabilities/default.json`
- Create: `src-tauri/tauri.conf.json`

- [ ] Step 1: Configure Tauri to use the Vite dev server and built frontend output.
- [ ] Step 2: Add the minimal Rust entrypoint and default capability.
- [ ] Step 3: Configure bundle targets for `nsis` and `dmg`.
- [ ] Step 4: Verify the config files are internally consistent.

### Task 3: Document local setup

**Files:**
- Create: `README.md`
- Create: `.gitignore`

- [ ] Step 1: Document Node, pnpm, Rust, and Windows prerequisites.
- [ ] Step 2: Document icon generation from `logo.png`.
- [ ] Step 3: Document local dev, test, and build commands.
