# AGENTS.md — Golden Rules for AI Coding Tools

This file is readable by any AI coding tool (Cursor, GitHub Copilot, Claude Code,
Windsurf, etc.).

Tool-specific versions of these same rules:
- Cursor: `.cursor/rules/golden-rules.mdc`
- GitHub Copilot: `.github/copilot-instructions.md`
- Claude Code: `CLAUDE.md`

---

## Project context

**Name**: a11yhood — Accessible Product Reviews for Assistive Technology  
**Stack**: React 19 · TypeScript · Vite · Tailwind CSS v4 · Radix UI · shadcn/ui · Supabase · TanStack Query · React Router DOM v7  
**Purpose**: Community platform for discovering, reviewing, and discussing open-source assistive technologies.

---

## 1. Golden rules (blocking errors)

1. NEVER modify protected files (see section 2 below). Breakage is catastrophic.
2. ALL interactive UI elements MUST have a visible `:focus-visible` ring, keyboard
   operability, and an accessible name.
3. Use design tokens for ALL colors, spacing, font sizes, and z-index values.
   Never hardcode visual values.
4. ALL animations MUST respect `prefers-reduced-motion: reduce`.
5. Prefer semantic HTML (`button`, `details/summary`, `fieldset/legend`) before ARIA.
6. Search for existing libraries and project modules before adding dependencies or
   writing new utility code.
7. Keep PRs small. One feature or fix per PR.
8. NEVER delegate comprehension-critical tasks (reading, analyzing, summarizing
   source documents) to subagents or lower-tier models. The model that reasons
   over source material must be the primary model in the session. Research that
   feeds a11yhood's development planning is too important to hand to a cheaper
   model.

## 2. Protected files (never modify)

These files MUST NOT be edited by AI agents:

- `LICENSE`
- `CNAME`
- `env.example`
- `.env`, `.env.local`, `.env.production.local`, and all `.env.*` files

## 3. Environment tool preference

This project uses **npm** as the package manager.

1. ALL commands MUST use `npm run <task>` (see `package.json` scripts)
2. NEVER generate standalone shell scripts for tasks that have a `package.json` equivalent
3. Check `package.json` `scripts` for existing tasks before constructing commands
4. If no matching task exists, suggest adding one to `package.json` rather than
   creating a standalone script

Exceptions: one-off file operations (mkdir, cp, mv), git commands, initial setup.

## 4. Commit convention

- Use conventional commit prefixes: `feat:`, `fix:`, `docs:`, `test:`, `chore:`
- Work from the `main` branch
- Feature branches: `feat/short-name`, `fix/short-name`, etc.

## 5. Accessibility requirements

- WCAG target: **WCAG 2.2 Level AA**
- Minimum touch target: 44×44px
- Icon-only buttons require `aria-label`
- All five system preference media queries must be respected:
  `prefers-color-scheme`, `prefers-reduced-motion`, `prefers-contrast`,
  `forced-colors`, `prefers-reduced-transparency`
- All Radix UI/shadcn components must retain their built-in accessibility attributes —
  do NOT strip `aria-*`, `role`, or `data-*` attributes from these components

## 6. Security boundaries

- NEVER remove or weaken security headers (COOP/COEP/CORP, CSP)
- NEVER add `unsafe-eval` or `unsafe-inline` to CSP
- NEVER lower dependency audit severity level
- NEVER commit secrets, credentials, or API keys
- NEVER expose Supabase service-role keys on the client side (only anon key via `VITE_SUPABASE_ANON_KEY`)
- Always use `DOMPurify` when rendering user-generated HTML content

## 7. Quality gates

Run before every PR:

- Lint: `npm run lint`
- Unit tests: `npm run test:run`
- Build: `npm run build`
