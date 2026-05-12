# Pokemon Static

A statically generated Pokémon website built with **Astro** and **Tailwind CSS v4**.  
It consumes data from [PokeAPI](https://pokeapi.co/) at build time and generates pages for the first 151 Pokémon, including paginated listing pages and individual detail pages with official artwork and audio cries.


## About the Project

This project was built as part of an Astro course and demonstrates:

- **Static Site Generation (SSG)** — Pages are pre-rendered at build time.
- **PokeAPI Integration** — Pokémon names and URLs are fetched from PokeAPI.
- **Pagination** — Static list pages with previous/next navigation.
- **Root Redirect** — The homepage (`/`) automatically redirects to `/pokemons/1` to show the first page of Pokémon.
- **Dynamic Routes** — Generated routes for:
  - `pokemon/[id].astro` (detail by ID, currently used by cards)
  - `pokemons/[name].astro` (detail by name)
  - `pokemons/[page].astro` (paginated listing)
- **SEO & Open Graph Metadata** — `title`, `description`, and `og:image` via `MainLayout`.
- **Tailwind CSS v4** — Styling via Tailwind + Vite plugin.
- **View Transitions** — Astro built-in transitions for smoother navigation.

## Project Structure

```text
/
├── public/                          # Static assets
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── Welcome.astro
│   │   └── pokemons/
│   │       └── PokemonCard.astro    # Reusable Pokemon card (links to /pokemon/[id])
│   ├── consts/
│   │   └── site-info.ts
│   ├── interfaces/
│   │   └── pokemon-list.response.ts
│   ├── layouts/
│   │   ├── Layout.astro
│   │   └── MainLayout.astro
│   ├── pages/
│   │   ├── 404.astro                # Custom 404 page
│   │   ├── index.astro              # Redirects to /pokemons/1
│   │   ├── pokemon/
│   │   │   └── [id].astro           # Pokemon detail by ID
│   │   └── pokemons/
│   │       ├── [name].astro         # Pokemon detail by name
│   │       └── [page].astro         # Paginated list (20 per page)
│   └── styles/
│       └── global.css
├── astro.config.mjs                 # Root redirect configured here
├── package.json
├── pnpm-lock.yaml
└── tsconfig.json