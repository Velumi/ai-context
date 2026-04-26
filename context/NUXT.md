# Velumi — Nuxt Conventions

Shared conventions for all Velumi Nuxt 4 apps (dashboard, website, login, docs-app).

## shadcn-vue

- Components auto-imported with `Ui` prefix — `UiButton`, `UiCard`, etc.
- **Never modify files in `app/components/ui/`** — managed by shadcn CLI
- To add missing components: `npx shadcn-vue@latest add <component>`

## i18n

- i18n keys for all visible text — no hardcoded strings in templates
- Use `useTypedI18n()` instead of `useI18n()` for type-safe key validation
- `localePath()` for internal links

## Local Dev TLS

Server-side `$fetch` to `*.local.velumi.com` fails with cert errors — set `NODE_TLS_REJECT_UNAUTHORIZED=0` in `.env` for local dev only.

## Patterns

- State: `useState()` composables (no Pinia/Vuex)
- Forms: Vee-validate + Zod schemas
- Fetch: `useFetch()` for GETs (cached), `$fetch()` for mutations
