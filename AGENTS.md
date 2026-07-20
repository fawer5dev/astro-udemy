# AGENTS.md

## Repo Structure

This is **not** a monorepo workspace. Each numbered directory (`01-foundation/`, `02-pokemon-static/`, etc.) is an independent Astro project with its own `package.json`, lockfile, and `node_modules`. Always `cd` into the target project before running commands.

## Commands

No lint, typecheck, or test scripts exist. Available scripts per project:

```
npm run dev      # dev server
npm run build    # SSG build (fetches PokeAPI at build time — requires network)
npm run preview  # preview built output
```

Both `pnpm-lock.yaml` and `package-lock.json` are present. Use whichever the user prefers; do not delete one without asking.

## 02-pokemon-static

- **Astro 5** + **Tailwind CSS v4** via `@tailwindcss/vite` Vite plugin (not `@astrojs/tailwind`)
- **SSG only** — all pages pre-rendered at build time using PokeAPI data
- Path aliases in `tsconfig.json`: `@components/*`, `@interfaces/*`, `@layouts/*`, `@styles/*`
- Root `/` redirects to `/pokemons/1` (configured in `astro.config.mjs` `redirects`)
- View transitions enabled via CSS `@view-transition { navigation: auto }` in `MainLayout.astro`, not the `<ViewTransitions />` component (commented out)
- Dynamic routes: `pokemon/[id].astro` (by ID), `pokemons/[name].astro` (by name), `pokemons/[page].astro` (paginated list)
