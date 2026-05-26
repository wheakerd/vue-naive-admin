---
type: report
title: Documentation Gaps - Loop 00001
created: 2026-05-26
tags:
  - readme-accuracy
  - documentation-gaps
  - vue-naive-admin
related:
  - '[[LOOP_00001_FEATURE_INVENTORY]]'
  - '[[2_FIND_GAPS]]'
---

# Documentation Gaps - Loop 00001

## Summary

- **Total Gaps Found:** 12
- **MISSING (undocumented features):** 9
- **STALE (removed features still documented):** 1
- **INACCURATE (wrong descriptions):** 2
- **INCOMPLETE (needs more detail):** 0

---

## Gap List

### GAP-001: Authentication Screens

- **Type:** MISSING
- **Feature:** Login, register, reset password, and code login flows
- **Code Location:** `src/pages/login.vue`, `src/components/modules/login/*`, `src/hooks/business/auth.ts`
- **README Location:** Not mentioned
- **Description:**
  The app includes multiple authentication screens and related auth behavior, but the README only describes the project as an admin template and does not tell users that these auth flows exist.
- **Evidence:**
  - Code: `src/pages/login.vue` and `src/components/modules/login/*` implement password login, code login, registration, and password reset UI.
  - README: No authentication screen or login-flow description appears in the intro, usage, or features sections.
- **User Impact:** New users evaluating the template cannot tell that common auth screens are already included.

### GAP-002: System Management Pages and APIs

- **Type:** MISSING
- **Feature:** User management, role management, user detail, and system-management API client
- **Code Location:** `src/pages/manage/*`, `src/components/modules/manage/*`, `src/service/api/system-manage.ts`
- **README Location:** Not mentioned directly
- **Description:**
  Concrete admin management pages and APIs exist, but README only says "rich page components" and does not name the management features.
- **Evidence:**
  - Code: `src/pages/manage/user.vue`, `src/pages/manage/role.vue`, and `src/pages/manage/user-detail.[id].vue` provide management workflows.
  - README: Lines 99-100 mention generic page/layout/theme components but do not identify user or role management.
- **User Impact:** Users looking for a starter admin system may miss that user and role management examples are already available.

### GAP-003: Dashboard, User Center, About, and Documentation Pages

- **Type:** MISSING
- **Feature:** Dashboard/home workbench, user center, about page, and documentation link pages
- **Code Location:** `src/pages/home.vue`, `src/pages/user-center.vue`, `src/pages/about.vue`, `src/pages/document*`
- **README Location:** Not mentioned directly
- **Description:**
  Several core template pages are present in code but not listed in the README.
- **Evidence:**
  - Code: The page tree includes `home.vue`, `user-center.vue`, `about.vue`, and Vue/Vite/UnoCSS/Naive UI document pages.
  - README: No section names these pages or explains what the bundled app demonstrates after login.
- **User Impact:** Readers cannot quickly understand the visible application surface before running it.

### GAP-004: Plugin and Component Demo Suite

- **Type:** MISSING
- **Feature:** Audio, video, clipboard, icons, maps, PDF, signature, swiper, typewriter, charts, Excel, flow, Gantt, JSON, table, and guide demos
- **Code Location:** `src/pages/plugin/*`, `src/components/modules/plugin/*`
- **README Location:** Not mentioned directly
- **Description:**
  The application contains a substantial plugin demo section, but README only uses broad language about components.
- **Evidence:**
  - Code: `src/pages/plugin/*` includes demos for media, charts, tables, maps, PDF export/preview, Excel export, flows, Gantt charts, JSON editors, and guided tours.
  - README: The features section does not enumerate plugin demos or the supported third-party integrations.
- **User Impact:** This is one of the largest user-facing feature areas and a likely selling point, but users cannot discover it from README.

### GAP-005: Route and Navigation UX

- **Type:** MISSING
- **Feature:** Breadcrumbs, generated menus, multi-level menu demos, hidden child routes, KeepAlive route caching, page transitions, and external route links
- **Code Location:** `src/layouts/modules/global-breadcrumb/index.vue`, `src/layouts/modules/global-menu/*`, `src/pages/multi-menu/*`, `src/pages/function/hide-child*`, `src/layouts/modules/global-content/index.vue`
- **README Location:** Partially covered by "Automated file routing system"
- **Description:**
  README documents route generation but omits the user-facing route/navigation behaviors built around it.
- **Evidence:**
  - Code: Layout modules and route demo pages implement breadcrumbs, menu generation, nested menu behavior, hidden child routes, route cache, and transitions.
  - README: Lines 97-98 describe automated file routing and permission routing, but not the navigation UX examples.
- **User Impact:** Users may assume the project only generates routes, not that it includes production-style navigation patterns.

### GAP-006: Header Actions and Runtime Controls

- **Type:** MISSING
- **Feature:** Language switcher, theme schema switcher, reload button, full-content toggle, user avatar, and logout entry
- **Code Location:** `src/layouts/modules/global-header/*`, `src/components/common/lang-switch.vue`, `src/components/common/theme-schema-switch.vue`, `src/components/common/reload-button.vue`, `src/layouts/default.vue`
- **README Location:** Not mentioned directly
- **Description:**
  The header includes multiple app controls that are absent from the README.
- **Evidence:**
  - Code: Header components expose language, theme, reload, fullscreen/content mode, user menu, and logout-related interactions.
  - README: No header controls or runtime app actions are described.
- **User Impact:** Users cannot judge the completeness of the shell and day-to-day admin UX from the documentation.

### GAP-007: Detailed Theme Drawer Capabilities

- **Type:** MISSING
- **Feature:** Theme drawer appearance, layout, general settings, copy config, and reset config
- **Code Location:** `src/layouts/modules/theme-drawer/*`, `src/store/modules/theme/index.ts`
- **README Location:** Partially covered by "Rich theme configuration"
- **Description:**
  README says theme configuration exists but omits the specific configurable controls.
- **Evidence:**
  - Code: Theme drawer modules expose color, radius, light/dark/system scheme, layout mode, header/sider/footer/content options, config copy, and reset.
  - README: Lines 95 and 99 mention theme configuration generically.
- **User Impact:** Users evaluating customization effort cannot see how much theming is available without running or reading code.

### GAP-008: Environment and Runtime Configuration Options

- **Type:** MISSING
- **Feature:** Dynamic title, auth visibility, router history mode, proxy controls, service codes, ports, source maps, storage prefix, and update detection
- **Code Location:** `.env`, `.env.development`, `.env.testing`, `.env.production`, `vite.config.ts`, `build/config/proxy.ts`
- **README Location:** Not mentioned
- **Description:**
  The project exposes many runtime and build-time environment flags, but README only gives install and command usage.
- **Evidence:**
  - Code: `.env` documents settings such as `VITE_AUTH_ROUTE_VISIBLE`, `VITE_ROUTER_HISTORY_MODE`, `VITE_HTTP_PROXY`, `VITE_SERVICE_SUCCESS_CODES`, `VITE_SERVER_PORT`, and `VITE_AUTOMATICALLY_DETECT_UPDATE`.
  - README: No environment variable or configuration section exists.
- **User Impact:** Users cannot configure deployment, proxying, routing mode, or auth demo behavior from README alone.

### GAP-009: Workspace Packages

- **Type:** MISSING
- **Feature:** Reusable workspace packages for axios, color, hooks, materials, and utils
- **Code Location:** `packages/*`, `package.json`
- **README Location:** Partially covered by "pnpm monorepo architecture"
- **Description:**
  README mentions monorepo architecture but not the actual internal packages users can reuse.
- **Evidence:**
  - Code: `package.json` depends on `@sa/axios`, `@sa/color`, `@sa/hooks`, `@sa/materials`, and `@sa/utils` via `workspace:*`.
  - README: Line 92 mentions pnpm monorepo architecture only at a high level.
- **User Impact:** Developers extending the project may miss existing internal libraries and duplicate utilities.

### GAP-010: Removed or Missing Usage Scripts

- **Type:** STALE
- **Feature:** `pnpm cleanup`, `pnpm release`, and `pnpm update-pkg`
- **Code Location:** `package.json`
- **README Location:** Usage section, lines 52-53, 76-77, and 85-86
- **Description:**
  README lists commands that are not available in the current `package.json` scripts.
- **Evidence:**
  - Code: `package.json` scripts include `build`, `build:dev`, `build:tst`, `commit`, `dev`, `dev:prd`, `dev:tst`, `lint`, `lint:fix`, `prepare`, `preview`, and `typecheck`; no `cleanup`, `release`, or `update-pkg` script is defined.
  - README: Usage examples instruct users to run `pnpm cleanup`, `pnpm release`, and `pnpm update-pkg`.
- **User Impact:** Users following README commands will get script-not-found failures.

### GAP-011: Vite Version Claim

- **Type:** INACCURATE
- **Feature:** Vite version in project description and feature list
- **Code Location:** `package.json`
- **README Location:** Intro lines 7 and 9; Features line 91
- **Description:**
  README says the template is based on Vite 6, but the installed Vite dependency is Vite 8.
- **Evidence:**
  - Code: `package.json` has `"vite": "8.0.12"` and `@vitejs/plugin-vue` `6.0.6`.
  - README: Lines 7, 9, and 91 all say "Vite 6".
- **User Impact:** Users may install or reason about the project with the wrong Vite compatibility assumptions.

### GAP-012: Recommended pnpm Version

- **Type:** INACCURATE
- **Feature:** pnpm installation requirement/recommendation
- **Code Location:** `package.json`
- **README Location:** Install section, line 27
- **Description:**
  README recommends pnpm 8.x, while project metadata pins newer pnpm versions.
- **Evidence:**
  - Code: `package.json` declares `"packageManager": "pnpm@11.1.1"` and Volta pins pnpm `10.26.2`.
  - README: Line 27 says pnpm `>= 8.7.0`, recommended `8.14.0` or higher.
- **User Impact:** Contributors may use an older pnpm than the project metadata expects, causing install or lockfile churn.

---

## Gaps by Type

### MISSING Features

| Gap ID  | Feature                                       | Code Location                                                                                   | User Impact                                                                  |
| ------- | --------------------------------------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| GAP-001 | Authentication screens                        | `src/pages/login.vue`, `src/components/modules/login/*`                                         | Users cannot see bundled auth flows from README.                             |
| GAP-002 | System management pages and APIs              | `src/pages/manage/*`, `src/service/api/system-manage.ts`                                        | Users miss concrete admin management examples.                               |
| GAP-003 | Dashboard/user center/about/docs pages        | `src/pages/home.vue`, `src/pages/user-center.vue`, `src/pages/about.vue`, `src/pages/document*` | Users cannot preview the app surface from documentation.                     |
| GAP-004 | Plugin and component demo suite               | `src/pages/plugin/*`                                                                            | Users miss major integrated demos and libraries.                             |
| GAP-005 | Route and navigation UX                       | `src/layouts/modules/global-*`, `src/pages/multi-menu/*`, `src/pages/function/hide-child*`      | Users may underestimate navigation capabilities.                             |
| GAP-006 | Header actions and runtime controls           | `src/layouts/modules/global-header/*`, `src/components/common/*switch.vue`                      | Users miss shell-level controls.                                             |
| GAP-007 | Detailed theme drawer capabilities            | `src/layouts/modules/theme-drawer/*`                                                            | Users cannot judge customization depth.                                      |
| GAP-008 | Environment and runtime configuration options | `.env`, `vite.config.ts`, `build/config/proxy.ts`                                               | Users lack setup guidance for routing, proxy, ports, and auth demo behavior. |
| GAP-009 | Workspace packages                            | `packages/*`, `package.json`                                                                    | Developers may duplicate existing package utilities.                         |

### STALE Documentation

| Gap ID  | Feature       | README Section | What Changed                                                                                  |
| ------- | ------------- | -------------- | --------------------------------------------------------------------------------------------- |
| GAP-010 | Usage scripts | Usage          | `cleanup`, `release`, and `update-pkg` are documented but absent from `package.json` scripts. |

### INACCURATE Documentation

| Gap ID  | Feature             | What's Wrong                | Correct Behavior                                                   |
| ------- | ------------------- | --------------------------- | ------------------------------------------------------------------ |
| GAP-011 | Vite version        | README says Vite 6.         | `package.json` uses Vite 8.0.12.                                   |
| GAP-012 | pnpm recommendation | README recommends pnpm 8.x. | Project metadata declares pnpm 11.1.1 and Volta pins pnpm 10.26.2. |

### INCOMPLETE Documentation

| Gap ID | Feature | What's Missing                                                                                  |
| ------ | ------- | ----------------------------------------------------------------------------------------------- |
| None   | N/A     | No separate incomplete-only gaps were identified beyond the missing and inaccurate items above. |

---

## Priority Indicators

### High Priority Gaps

Features or claims that new users immediately encounter or rely on:

1. GAP-010: Removed or missing usage scripts - README commands fail when run.
2. GAP-011: Vite version claim - core stack version is wrong.
3. GAP-012: Recommended pnpm version - package manager guidance conflicts with project metadata.
4. GAP-008: Environment and runtime configuration options - users need these settings to run, proxy, and deploy the app correctly.

### Medium Priority Gaps

Features regular users would evaluate when choosing the template:

1. GAP-001: Authentication screens - common admin starter functionality.
2. GAP-002: System management pages and APIs - core admin workflows.
3. GAP-004: Plugin and component demo suite - large user-facing feature area.
4. GAP-007: Detailed theme drawer capabilities - important customization surface.
5. GAP-005: Route and navigation UX - important app-shell behavior.

### Low Priority Gaps

Advanced features or deeper implementation details:

1. GAP-003: Dashboard, user center, about, and documentation pages - useful but mostly discoverable after running the app.
2. GAP-006: Header actions and runtime controls - helpful shell details, not blocking setup.
3. GAP-009: Workspace packages - mainly relevant to maintainers and extenders.
