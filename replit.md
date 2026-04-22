# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Artifacts

### Break the Stigma (`artifacts/break-the-stigma`)
- **Type**: React + Vite web app
- **Preview Path**: `/`
- **Description**: Psychology website covering 6 psychological disorders and therapies
- **Theme**: Beige minimalistic with Playfair Display serif + Lato sans-serif fonts
- **Pages**:
  - `/` — Homepage with 4 sections: Pinboard, Instagram Carousel, FAQs, Resources
  - `/disorder/:slug` — Individual disorder pages with full info and interactive elements
- **Disorders covered**: GAD, Mood Disorders, PTSD, Eating Disorders, Psychotic Disorders, Addictions
- **Key components**:
  - `src/data/disorders.ts` — All disorder data and types
  - `src/components/Navbar.tsx` — Fixed navigation bar
  - `src/components/PinboardSection.tsx` — Cork pinboard with disorder cards
  - `src/components/InstagramCarousel.tsx` — Image carousel using attached carousel images
  - `src/components/FAQSection.tsx` — Accordion FAQ section
  - `src/components/ResourcesSection.tsx` — UAE mental health resources (HOPE, SAKINA, EHS)
  - `src/pages/HomePage.tsx` — Composes all sections
  - `src/pages/DisorderPage.tsx` — Individual disorder detail pages
- **Special**: PTSD page has an embedded Mentimeter interactive element

### API Server (`artifacts/api-server`)
- Standard Express 5 API server on `/api`

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
