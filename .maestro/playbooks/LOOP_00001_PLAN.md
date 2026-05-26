# Documentation Fix Plan - Loop 00001

## Summary

- **Total Gaps:** 12
- **Auto-Fix (PENDING):** 7
- **Needs Review:** 4
- **Won't Do:** 1

## Current README Accuracy: 62%

## Target README Accuracy: 90%

---

## PENDING - Ready for Auto-Fix

### DOC-001: Remove Missing Usage Scripts

- **Status:** `PENDING`
- **Gap ID:** GAP-010
- **Type:** STALE
- **User Importance:** CRITICAL
- **Fix Effort:** EASY
- **README Section:** Usage
- **Fix Description:**
  Remove documented commands that are not present in `package.json`: `pnpm cleanup`, `pnpm release`, and `pnpm update-pkg`.
- **Proposed Content:**

  ```text
  # Start project
  pnpm dev

  # Build project on production environment
  pnpm build

  # Build project on development environment
  pnpm build:dev

  # Build project on testing environment
  pnpm build:tst

  # Check format of commit message
  pnpm commit

  # Start project on testing environment
  pnpm dev:tst

  # Start project on production environment
  pnpm dev:prd

  # Lint
  pnpm lint

  # Lint & auto fix
  pnpm lint:fix

  # Install & configure simple-git-hooks
  pnpm prepare

  # Preview project
  pnpm preview

  # Check type
  pnpm typecheck
  ```

### DOC-002: Update Vite Version References

- **Status:** `PENDING`
- **Gap ID:** GAP-011
- **Type:** INACCURATE
- **User Importance:** HIGH
- **Fix Effort:** EASY
- **README Section:** Intro and Features
- **Fix Description:**
  Replace README references to Vite 6 with Vite 8 to match `package.json`.
- **Proposed Content:**

  ```text
  A fresh and elegant admin template, based on Vue 3, Vite 8, TypeScript, Naive UI and UnoCSS.

  `VueNaiveAdmin` is a clean, elegant, beautiful and powerful admin template, based on the latest front-end technology stack, including Vue 3, Vite 8, TypeScript, Pinia and UnoCSS.

  - Cutting-edge technology application: using the latest popular technology stack such as Vue 3, Vite 8, TypeScript, Pinia and UnoCSS.
  ```

### DOC-003: Update pnpm Requirement

- **Status:** `PENDING`
- **Gap ID:** GAP-012
- **Type:** INACCURATE
- **User Importance:** HIGH
- **Fix Effort:** EASY
- **README Section:** Install
- **Fix Description:**
  Align package manager guidance with project metadata. `package.json` declares `pnpm@11.1.1`; Volta pins `pnpm@10.26.2`.
- **Proposed Content:**
  ```text
  - [pnpm](https://pnpm.io) >= 10.26.2, recommended 11.1.1.
  ```

### DOC-004: Add Environment Configuration Section

- **Status:** `PENDING`
- **Gap ID:** GAP-008
- **Type:** MISSING
- **User Importance:** HIGH
- **Fix Effort:** MEDIUM
- **README Section:** New "Configuration" section after Usage
- **Fix Description:**
  Document the primary `.env` options users need for local development, routing, proxying, builds, and deployment.
- **Proposed Content:**

  ```text
  ## Configuration

  Core runtime options live in `.env` and environment-specific overrides such as `.env.development`, `.env.testing`, and `.env.production`.

  Common options:

  | Variable | Description |
  | --- | --- |
  | `VITE_BASE_URL` | Base path for deploying under a subdirectory. |
  | `VITE_AUTH_ROUTE_VISIBLE` | Shows or hides the demo authentication route. |
  | `VITE_ROUTER_HISTORY_MODE` | Router mode: `hash`, `history`, or `memory`. |
  | `VITE_HTTP_PROXY` | Enables the development HTTP proxy. |
  | `VITE_SERVICE_BASE_URL` | Backend service base URL for the current environment. |
  | `VITE_SERVICE_SUCCESS_CODES` | Service response codes treated as successful. |
  | `VITE_SERVICE_LOGOUT_CODES` | Service response codes that trigger logout. |
  | `VITE_SERVER_PORT` | Local development server port. |
  | `VITE_PREVIEW_PORT` | Local preview server port. |
  | `VITE_SOURCE_MAP` | Enables or disables build source maps. |
  | `VITE_STORAGE_PREFIX` | Prefix used to isolate local storage keys. |
  | `VITE_AUTOMATICALLY_DETECT_UPDATE` | Enables update detection in the running app. |
  ```

### DOC-005: Document Authentication Screens

- **Status:** `PENDING`
- **Gap ID:** GAP-001
- **Type:** MISSING
- **User Importance:** HIGH
- **Fix Effort:** EASY
- **README Section:** Features
- **Fix Description:**
  Add a concise feature bullet describing the bundled login, code login, registration, and password reset screens.
- **Proposed Content:**
  ```text
  - Authentication flows: includes login, code login, registration, and password reset screens for admin-template demos.
  ```

### DOC-006: Document System Management Pages

- **Status:** `PENDING`
- **Gap ID:** GAP-002
- **Type:** MISSING
- **User Importance:** HIGH
- **Fix Effort:** EASY
- **README Section:** Features
- **Fix Description:**
  Name the concrete user and role management examples included in the admin app.
- **Proposed Content:**
  ```text
  - System management examples: includes user management, role management, and user detail pages with matching API client examples.
  ```

### DOC-007: Document Plugin and Component Demo Suite

- **Status:** `PENDING`
- **Gap ID:** GAP-004
- **Type:** MISSING
- **User Importance:** HIGH
- **Fix Effort:** MEDIUM
- **README Section:** Features
- **Fix Description:**
  Replace generic component wording with a concrete summary of the larger demo suite.
- **Proposed Content:**
  ```text
  - Plugin demos: includes audio, video, clipboard, icon, map, PDF, signature, swiper, typewriter, chart, Excel, flow, Gantt, JSON editor, table, and guide examples.
  ```

---

## PENDING - NEEDS REVIEW

### DOC-008: Route and Navigation UX

- **Status:** `PENDING - NEEDS REVIEW`
- **Gap ID:** GAP-005
- **User Importance:** MEDIUM
- **Fix Effort:** MEDIUM
- **Questions:**
  - Should README expand the file-routing feature into a broader app-shell/navigation section?
  - Should advanced examples such as hidden child routes and KeepAlive caching be documented in README or left to in-app demos?

### DOC-009: Detailed Theme Drawer Capabilities

- **Status:** `PENDING - NEEDS REVIEW`
- **Gap ID:** GAP-007
- **User Importance:** MEDIUM
- **Fix Effort:** MEDIUM
- **Questions:**
  - Should README enumerate individual theme drawer controls, or keep the current concise theme feature bullet?
  - Should copy/reset configuration behavior be documented for end users?

### DOC-010: Dashboard, User Center, About, and Documentation Pages

- **Status:** `PENDING - NEEDS REVIEW`
- **Gap ID:** GAP-003
- **User Importance:** LOW
- **Fix Effort:** EASY
- **Questions:**
  - Should README include a full page inventory, or only major user-facing modules?
  - Are these pages important enough for README, given they are discoverable after running the app?

### DOC-011: Header Actions and Runtime Controls

- **Status:** `PENDING - NEEDS REVIEW`
- **Gap ID:** GAP-006
- **User Importance:** LOW
- **Fix Effort:** EASY
- **Questions:**
  - Should shell controls such as language switching, reload, full-content mode, avatar, and logout be documented in README?
  - Would these be better grouped under a concise "Application shell" bullet?

---

## WON'T DO

### DOC-012: Workspace Packages

- **Status:** `WON'T DO`
- **Gap ID:** GAP-009
- **Reason:** The package list is primarily useful to maintainers and extenders. README already mentions the pnpm monorepo architecture, and documenting every internal workspace package risks duplicating implementation details that may change often.

---

## Fix Order

Recommended sequence based on importance and dependencies:

1. **DOC-001** - Remove missing usage scripts (CRITICAL, commands currently fail)
2. **DOC-002** - Update Vite version references (HIGH, core stack version)
3. **DOC-003** - Update pnpm requirement (HIGH, install guidance)
4. **DOC-004** - Add environment configuration section (HIGH, setup/deployment guidance)
5. **DOC-005** - Document authentication screens (HIGH, common admin workflow)
6. **DOC-006** - Document system management pages (HIGH, common admin workflow)
7. **DOC-007** - Document plugin and component demo suite (HIGH, major feature area)
8. **DOC-008** - Route and navigation UX (MEDIUM, review scope first)
9. **DOC-009** - Detailed theme drawer capabilities (MEDIUM, review scope first)
10. **DOC-010** - Dashboard, user center, about, and documentation pages (LOW, review scope first)
11. **DOC-011** - Header actions and runtime controls (LOW, review scope first)

## README Section Updates Needed

| Section       | Gaps to Fix                        | Action Needed                                      |
| ------------- | ---------------------------------- | -------------------------------------------------- |
| Install       | DOC-003                            | Update pnpm version guidance                       |
| Usage         | DOC-001                            | Remove unavailable scripts                         |
| Configuration | DOC-004                            | Add new environment variable section               |
| Intro         | DOC-002                            | Update Vite version references                     |
| Features      | DOC-002, DOC-005, DOC-006, DOC-007 | Add or update feature bullets                      |
| Features      | DOC-008, DOC-009, DOC-010, DOC-011 | Review whether additional detail belongs in README |
