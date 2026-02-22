# Project Rules for Claude Code

These rules apply to all AI-assisted work in this project. They match the rules
in `AGENTS.md`, formatted for Claude Code.

## Project context

**Name**: a11yhood — Accessible Product Reviews for Assistive Technology  
**Stack**: React 19 · TypeScript · Vite · Tailwind CSS v4 · Radix UI · shadcn/ui · Supabase · TanStack Query · React Router DOM v7  
**Purpose**: Community platform for discovering, reviewing, and discussing open-source assistive technologies.

## Golden rules (blocking errors)

1. NEVER modify protected files: `LICENSE`, `CNAME`, `env.example`, `.env*`
2. ALL interactive UI must have `:focus-visible` ring, keyboard operability, accessible name.
3. Use design tokens — never hardcode colors, spacing, font sizes, z-index.
4. ALL animations must respect `prefers-reduced-motion: reduce`.
5. Semantic HTML before ARIA (`button`, `details/summary`, `fieldset/legend`).
6. Search for existing implementations before writing new code or adding dependencies.
7. Keep PRs small. One feature or fix per PR.
8. NEVER delegate comprehension-critical tasks (reading, analyzing, summarizing
   source documents) to subagents or lower-tier models. The model that reasons
   over source material must be the primary model in the session. Research that
   feeds a11yhood's development planning is too important to hand to a cheaper
   model.

## Protected files

Do NOT edit these files under any circumstances:
- `LICENSE`
- `CNAME`
- `env.example`
- `.env`, `.env.local`, `.env.production.local`, and all `.env.*` files

## Environment tool

This project uses **npm**. ALL commands MUST use `npm run <task>`.  
Check `package.json` `scripts` before constructing any command.  
If no matching task exists, suggest adding one to `package.json` rather than writing a script.

Exceptions: file operations, git commands, initial setup.

## Commit convention

- Prefixes: `feat:`, `fix:`, `docs:`, `test:`, `chore:`
- Base branch: `main`
- Branch naming: `feat/short-name`, `fix/short-name`

## Accessibility requirements

- Target: **WCAG 2.2 Level AA**
- Touch targets: 44×44px minimum
- Icon-only buttons: require `aria-label`
- Respect all system preferences: `prefers-color-scheme`, `prefers-reduced-motion`,
  `prefers-contrast`, `forced-colors`, `prefers-reduced-transparency`
- Do NOT strip `aria-*`, `role`, or `data-*` attributes from Radix UI/shadcn components

## Security boundaries

- NEVER weaken security headers (COOP/COEP/CORP, CSP)
- NEVER add `unsafe-eval` or `unsafe-inline` to CSP
- NEVER lower audit severity level
- NEVER commit secrets or credentials
- NEVER expose the Supabase service-role key on the client (only `VITE_SUPABASE_ANON_KEY`)
- Always use `DOMPurify` when rendering user-generated HTML content

## Quality gates

Before every PR:
- Lint: `npm run lint`
- Unit tests: `npm run test:run`
- Build: `npm run build`
