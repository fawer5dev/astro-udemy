# Pokemon Static

A statically generated Pokémon website built with **Astro** and **Tailwind CSS v4**.
It consumes data from [PokeAPI](https://pokeapi.co/) at build time and generates pages for the first 151 Pokémon, including paginated listing pages and individual detail pages with official artwork and audio cries.

## About the Project

This project was built as part of an Astro course and demonstrates:

- **Static Site Generation (SSG)** — All pages are pre-rendered at build time.
- **PokeAPI Integration** — Pokémon names and URLs are fetched from PokeAPI at build time.
- **Pagination** — Static listing pages (20 per page) with previous/next navigation.
- **Root Redirect** — `/` redirects to `/pokemons/1`.
- **Dynamic Routes**:
  - `pokemon/[id].astro` — Detail page by Pokémon ID
  - `pokemons/[name].astro` — Detail page by Pokémon name
  - `pokemons/[page].astro` — Paginated list (20 items per page)
- **SEO & Open Graph** — `title`, `description`, and `og:image` metadata via `MainLayout`.
- **Tailwind CSS v4** — Styled with Tailwind via the `@tailwindcss/vite` Vite plugin.
- **View Transitions** — Enabled via CSS `@view-transition` in `MainLayout.astro`.

## Project Structure

```text
/
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── Welcome.astro
│   │   ├── pokemons/
│   │   │   └── PokemonCard.astro
│   │   └── share/
│   │       └── NavBar.astro
│   ├── consts/
│   │   └── site-info.ts
│   ├── interfaces/
│   │   └── pokemon-list.response.ts
│   ├── layouts/
│   │   ├── Layout.astro
│   │   └── MainLayout.astro
│   ├── pages/
│   │   ├── 404.astro
│   │   ├── index.astro
│   │   ├── pokemon/
│   │   │   └── [id].astro
│   │   └── pokemons/
│   │       ├── [name].astro
│   │       └── [page].astro
│   └── styles/
│       └── global.css
├── astro.config.mjs
├── package.json
├── pnpm-lock.yaml
└── tsconfig.json
```

## Getting Started

```bash
npm install
npm run dev       # Start dev server at http://localhost:4321
npm run build     # SSG build (requires network for PokeAPI)
npm run preview   # Preview production build locally
```