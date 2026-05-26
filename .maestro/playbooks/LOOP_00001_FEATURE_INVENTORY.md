---
type: report
title: Feature Inventory - Loop 00001
created: 2026-05-26
tags:
  - readme-accuracy
  - feature-inventory
  - vue-naive-admin
related:
  - '[[1_ANALYZE]]'
---

# Feature Inventory - Loop 00001

## README Analysis

### README Location
`D:\projects\personal\loicduong\vue-naive-admin/README.md`

### README Structure
| Section | Description | Line Numbers |
|---------|-------------|--------------|
| Vue Naive Admin | Project title, badges, logo, and admin template summary | 1-9 |
| Table of Contents | Links to the main README sections | 11-19 |
| Install | Git, Node, and pnpm requirements plus clone/install commands | 21-35 |
| Usage | pnpm command examples for dev, build, lint, preview, commit hooks, release, cleanup, typecheck, and package updates | 37-86 |
| Features | High-level template capabilities and tooling claims | 89-106 |
| Browser Support | Latest Chrome recommendation and browser support matrix | 108-114 |
| Maintainer | Maintainer profile link | 116-118 |
| Contributing | Link to contribution guide | 120-122 |
| License | MIT license reference | 124-125 |

### Features Documented in README
| Feature | Section | Description in README |
|---------|---------|----------------------|
| Vue 3 admin template stack | Intro, Features | Vue 3, Vite 6, TypeScript, Naive UI, Pinia, and UnoCSS admin template |
| Built-in theme configuration | Intro, Features | Rich theme configuration integrated with UnoCSS |
| Component library foundation | Intro, Features | Built-in rich components and page components |
| Automated file routing | Intro, Features | Automatically generated route imports, declarations, and types |
| ApiFox mock data | Intro | Online mock data solution based on ApiFox |
| pnpm workspace/monorepo | Features | Clear pnpm monorepo project architecture |
| Strict code specifications | Features | Antfu ESLint config plus simple-git-hooks |
| TypeScript strict checking | Features, Usage | Type checking support through `pnpm typecheck` |
| Internationalization | Features | Built-in multi-language support |
| Permission routing | Features | Static frontend routing and backend dynamic routing support |
| Error/layout/theme pages | Features | 403, 404, 500 pages, layout, tags, and theme components |
| Command line tooling | Usage, Features | Git commit, delete file, release, cleanup, update package, build, lint, preview commands |
| Mobile adaptation | Features | Adaptive layout for mobile terminals |
| Components auto import | Features | `unplugin-vue-components` and `unplugin-icons` |
| APIs auto import | Features | `unplugin-auto-import` for APIs |
| Vercel deployment | Features | Zero-config Vercel deployment |
| standard-readme compliance | Features | Applies standard-readme style |
| PWA | Features | Progressive web app support |
| Browser support | Browser Support | Latest two versions of Edge, Firefox, Chrome, and Safari; IE unsupported |

---

## Codebase Analysis

### Project Type
- **Language/Framework:** TypeScript, Vue 3, Vite, Naive UI, UnoCSS, Pinia, Vue Router
- **Application Type:** Frontend admin web app/template with a workspace package architecture
- **Survey Note:** CodeGraph was unavailable because `.codegraph/` is not initialized, so this inventory used README, `package.json`, route/page files, stores, API modules, Vite plugins, environment files, and layout/theme components.

### Features Found in Code
| Feature | Location | Type | User-Facing? |
|---------|----------|------|--------------|
| App shell with Naive UI providers | `src/App.vue`, `src/components/common/app-provider.vue`, `src/plugins/app.tsx` | UI | Yes |
| Dashboard/home workbench | `src/pages/home.vue`, `src/components/modules/home/*` | UI | Yes |
| Login, register, reset password, and code login screens | `src/pages/login.vue`, `src/components/modules/login/*`, `src/hooks/business/auth.ts` | UI/Auth | Yes |
| Token-based auth state | `src/store/modules/auth/index.ts`, `src/service/api/auth.ts` | Auth/API | Yes |
| Route guard with login redirects and 403 handling | `src/router/guard/route.ts` | Routing/Auth | Yes |
| Role-filtered permission routing | `src/store/modules/route/shared.tsx`, `src/pages/manage.vue` | Routing/Auth | Yes |
| File-based route generation | `build/plugins/router.ts`, `src/router/routes/index.ts` | Routing | Yes |
| Dynamic document titles | `src/router/guard/title.ts`, `.env` | UI/Config | Yes |
| Menu generation from routes | `src/store/modules/route/shared.tsx`, `src/layouts/modules/global-menu/*` | UI/Routing | Yes |
| Breadcrumbs | `src/layouts/modules/global-breadcrumb/index.vue` | UI | Yes |
| Collapsible and mixed side navigation | `src/layouts/modules/global-sider/index.vue`, `src/layouts/modules/global-menu/*` | UI | Yes |
| Multi-level menu demo | `src/pages/multi-menu/*` | UI | Yes |
| Hidden child route demo | `src/pages/function/hide-child*` | UI/Routing | Yes |
| Theme drawer | `src/layouts/modules/theme-drawer/index.vue` | UI/Config | Yes |
| Light/dark/system theme scheme | `src/store/modules/theme/index.ts`, `src/components/common/theme-schema-switch.vue` | UI/Config | Yes |
| Theme color and radius controls | `src/layouts/modules/theme-drawer/modules/appearance/*` | UI/Config | Yes |
| Layout, header, sider, footer, content settings | `src/layouts/modules/theme-drawer/modules/layout/*` | UI/Config | Yes |
| Copy/reset theme configuration | `src/layouts/modules/theme-drawer/modules/config-operation.vue` | UI/Config | Yes |
| English and Vietnamese i18n | `src/locales/langs/en-us.ts`, `src/locales/langs/vi-vn.ts` | UI/i18n | Yes |
| Locale switcher | `src/components/common/lang-switch.vue`, `src/store/modules/app/index.ts` | UI/i18n | Yes |
| Responsive/mobile layout behavior | `src/store/modules/app/index.ts`, `src/layouts/modules/theme-drawer/index.vue` | UI | Yes |
| Page reload button and route cache reset | `src/components/common/reload-button.vue`, `src/store/modules/app/index.ts` | UI | Yes |
| Full content toggle | `src/store/modules/app/index.ts`, `src/layouts/default.vue` | UI | Yes |
| KeepAlive route caching and page transitions | `src/layouts/modules/global-content/index.vue`, `src/store/modules/route/shared.tsx` | UI/Routing | Yes |
| User center entry | `src/pages/user-center.vue`, `src/layouts/modules/global-header/components/user-avatar.vue` | UI | Yes |
| System management parent section | `src/pages/manage.vue` | UI/Auth | Yes |
| User management table and drawer | `src/pages/manage/user.vue`, `src/components/modules/manage/user/*` | UI/API | Yes |
| User detail route | `src/pages/manage/user-detail.[id].vue` | UI/Routing | Yes |
| Role management with menu/button authorization modals | `src/pages/manage/role.vue`, `src/components/modules/manage/role/*` | UI/API/Auth | Yes |
| System management API client | `src/service/api/system-manage.ts` | API | Yes |
| Document links/pages for Vue, Vite, UnoCSS, Naive UI | `src/pages/document*` | UI/Docs | Yes |
| About page with package/build details | `src/pages/about.vue`, `build/config/info.ts` | UI | Yes |
| Exception pages | `src/pages/403.vue`, `src/pages/404.vue`, `src/pages/500.vue`, `src/components/common/exception-base.vue` | UI | Yes |
| Audio visualization demo | `src/pages/plugin/audio.vue`, `src/assets/audio/boundless-skies.mp3` | UI/Plugin | Yes |
| Video player demo | `src/pages/plugin/video.vue` | UI/Plugin | Yes |
| Copy-to-clipboard demo | `src/pages/plugin/copy.vue` | UI/Plugin | Yes |
| Icon and custom SVG icon demos | `src/pages/plugin/icon.vue`, `src/assets/svg-icon/*` | UI/Plugin | Yes |
| Map and Google Map demo | `src/pages/plugin/map*` | UI/Plugin | Yes |
| PDF link and HTML preview/export demos | `src/pages/plugin/pdf*`, `src/workers/print-html.ts` | UI/Plugin | Yes |
| Signature pad export demo | `src/pages/plugin/signature.vue` | UI/Plugin | Yes |
| Swiper carousel demo | `src/pages/plugin/swiper.vue` | UI/Plugin | Yes |
| Typewriter text demo | `src/pages/plugin/typeit.vue` | UI/Plugin | Yes |
| Chart demos for AntV, D3, ECharts, and VChart | `src/pages/plugin/charts*`, `src/components/modules/plugin/charts/*` | UI/Plugin | Yes |
| Excel export demo | `src/pages/plugin/excel.vue` | UI/Plugin | Yes |
| Flow chart / Vue Flow demo | `src/pages/plugin/flow*`, `src/components/modules/plugin/flow/vue-flow/*` | UI/Plugin | Yes |
| Gantt demos for dhtmlxGantt and VTableGantt | `src/pages/plugin/gantt*`, `src/components/modules/plugin/gantt/*` | UI/Plugin | Yes |
| JSON editor and JSON pretty demos | `src/pages/plugin/json*` | UI/Plugin | Yes |
| VTable and AG Grid table demos | `src/pages/plugin/tables*`, `src/components/modules/plugin/tables/*` | UI/Plugin | Yes |
| Guided tour/onboarding demo | `src/pages/plugin/guide.vue` | UI/Plugin | Yes |
| PWA manifest and service worker plugin | `build/plugins/pwa.ts`, `public/pwa-*.png` | PWA | Yes |
| Auto-imported Vue APIs, hooks, stores, components, and icons | `build/plugins/unplugin.ts` | Build/Developer UX | Yes |
| Local SVG icon collection | `build/plugins/unplugin.ts`, `src/assets/svg-icon/*` | Build/UI | Yes |
| Environment-based build/dev configuration | `.env`, `.env.development`, `.env.testing`, `.env.production`, `vite.config.ts` | Config | Yes |
| API proxy configuration | `build/config/proxy.ts`, `.env` | Config/API | Yes |
| Vercel configuration | `vercel.json` | Deployment | Yes |
| Monorepo packages for axios, color, hooks, materials, utils | `packages/*` | Library/Architecture | Yes |
| pnpm scripts for dev/build/lint/typecheck/preview/prepare/commit | `package.json` | CLI | Yes |

---

## Feature Summary

### Totals
- **Features in README:** 19
- **Features in Code:** 55
- **Potential Gaps:** 36 code features are more specific than the README currently documents
- **Potential Stale:** 5 README claims appear stale or only partially supported by current code/config

### Quick Classification

#### Likely Undocumented (in code, not in README)
1. Login variants: password login, code login, register, and reset password screens.
2. Concrete admin pages: dashboard, user management, role management, user detail, user center, about.
3. Header actions: language switcher, theme schema switcher, theme drawer, reload, user avatar, logout.
4. Theme drawer details: appearance, layout, general tabs; color/radius/schema; header/sider/footer/content controls; copy/reset config.
5. Concrete plugin demos: audio, video, copy, icon, map, PDF, signature, swiper, typeit, chart libraries, Excel export, flow charts, Gantt charts, JSON editors, table libraries, and guided tour.
6. Route UX: breadcrumbs, menu generation, multi-level menu demo, hidden child routes, keep-alive route cache, page transitions, external route links.
7. API surface: auth endpoints and system-management endpoints for users, roles, menus, pages, and menu trees.
8. Environment options: auth visibility, dynamic title, router mode, proxy, service codes, ports, source maps, storage prefix, update detection.
9. Workspace packages: reusable axios, color, hooks, materials, and utils packages.

#### Possibly Stale (in README, not found in code)
1. `pnpm cleanup` - listed in README Usage but absent from `package.json` scripts.
2. `pnpm release` - listed in README Usage but absent from `package.json` scripts, despite `release.config.cjs` existing.
3. `pnpm update-pkg` - listed in README Usage but absent from `package.json` scripts.
4. Vite 6 claim - README says Vite 6, while `package.json` uses `vite` 8.0.12 and `@vitejs/plugin-vue` 6.0.6.
5. Recommended pnpm version - README recommends pnpm 8.x, while `package.json` declares `packageManager` pnpm 11.1.1 and Volta pnpm 10.26.2.

#### Confirmed Documented (in both)
1. Vue 3 + TypeScript + Naive UI + Pinia + UnoCSS stack - present in dependencies and code.
2. Theme configuration - implemented through `src/theme/*`, Pinia theme store, and theme drawer UI.
3. Internationalization - implemented for English and Vietnamese.
4. File-based routing - implemented through `vue-router/vite` and `vite-plugin-vue-layouts-next`.
5. Permission routing - implemented through route guards and role filtering.
6. Error pages - 403, 404, and 500 pages exist.
7. Mobile adaptation - responsive app store behavior collapses and restores layout.
8. Auto importing - implemented for Vue APIs, hooks, stores, components, Naive UI, and icons.
9. PWA - implemented with `vite-plugin-pwa` and web app icons.
10. Vercel deployment - `vercel.json` is present.
11. Standard README - README includes a standard-readme badge and common sections.
