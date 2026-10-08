# Import & Setup: "folio" (Expo / React Native)

Bring your existing GitHub project into this workspace, get all dependencies installed, and
run it live on the Expo preview without changing what the app does or how it looks.

## Who it's for
You — the owner of the `folio` repo — who wants your existing Expo/React Native app running
in this environment so you can keep building on it here.

## Core features and experience
This is an import, not a new product. The goal is a faithful, working copy of your current app:
- Clone `folio` (branch `main`) and bring its code into the workspace.
- Install every dependency the project declares, matched to this environment's Expo SDK.
- Wire the project into this environment's conventions so it actually runs: backend URL via
  environment variables (not hardcoded), API routes reachable, app served on the preview.
- Launch it and confirm it loads — your existing screens, navigation, and features intact.

What I will NOT do in this pass: redesign screens, rename features, or add new functionality.
Only the minimal adjustments needed to make your existing code run here.

## User flow
1. Repo is cloned and its structure is inspected (Expo app, any backend, config files).
2. Dependencies are installed and version-aligned to the environment's Expo SDK.
3. Project config is adapted to this environment (env vars, ports, routing) where required.
4. The app is started and the preview is opened to confirm it renders.
5. You get a short report of what was imported, what was adjusted, and anything that needs you.

## UI/UX feel
Whatever your repo already ships. No visual or structural changes are made in this import.

## Implementation phases

**Phase 1 — Import & run (built now)**
- Clone `folio` / `main` into the workspace.
- Detect the stack and reconcile it with the environment (Expo Router, SDK version, backend if present).
- Install all dependencies.
- Apply the minimum environment adaptations needed to run (env-based backend URL, correct ports,
  `/api` route prefix if a backend exists), without altering app behavior.
- Start the app and verify the preview loads.

**Phase 2 — Stabilize (later)**
- Fix any runtime errors, broken screens, or missing assets surfaced after import.
- Resolve dependency conflicts or deprecated Expo packages flagged during install.

**Phase 3 — Continue building (later)**
- New features, redesigns, or integrations you want on top of the imported app.

## Assumptions
- The repo is private. Access will be provided via a GitHub Personal Access Token (PAT), which
  you confirmed as the method. The actual token must be pasted at the start of the build, since
  the repo URL currently returns a 404 to anonymous access and cannot be cloned without it. The
  token is used once to clone and is not stored in the app.
- Repo URL is `https://github.com/tetukuidn/folio.git`, confirmed unchanged.
- Branch to import is `main`, as stated.
- The project is Expo / React Native, as you confirmed.
- If the repo contains its own backend, it will be adapted to this environment's FastAPI + MongoDB
  conventions and `/api` routing; if it calls an external backend, that URL is moved into env vars.
- If the repo's structure differs from this environment (e.g. not Expo Router, custom entry point,
  different env/port setup), it will be adapted minimally to run here — app features kept unchanged.
- Any API keys, secrets, or external services the app needs are not included in the public repo and
  will be requested from you if the app fails to run without them.
- This import does not include deploying or generating device builds.
