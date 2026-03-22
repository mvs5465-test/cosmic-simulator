# AGENTS.md

Instructions for human + AI contributors in this repository.

## Product

- `cosmic-simulator` is a browser-based gravity sandbox with cinematic space-physics effects.
- The app is intentionally static and browser-first: no backend, no bundler, no framework.

## Architecture

- `index.html` is the main browser entrypoint.
- `sim-core.js` contains the shared simulation logic.
- `sim.js` owns browser rendering, UI wiring, and runtime behavior.
- `run-tests.js` runs the Node regression suite for the shared core.
- `test.html` and `test.js` are browser smoke checks for the runtime adapter.

## Working Rules

- Keep the fast static-file workflow intact.
- Prefer changing the shared core in `sim-core.js` when the behavior should match across runtime and tests.
- Keep visual and effect polish grounded in performance; this project has explicit performance and animation notes already in-repo.
- Avoid adding build tooling unless there is a clear concrete need.

## Verification

- Run `node run-tests.js` for shared-core regressions.
- Open `index.html` or `test.html` in a browser after runtime or UI changes.
