# a11yhood Contributor Onboarding Plan -- Revised 2026-02-22

## Provenance

- **Sources**: `.playbook/docs/PLAYBOOK.md`, `PROCESS_CADENCE.md`, `LESSONS_LEARNED.md`, `LEAD_DEVELOPER_CHOICES_NEEDED.md`, `AI_TASK_DELEGATION_RULES.md`, `TOKEN_ECONOMICS.md`, `SESSION_BOUNDARY_PROTOCOL.md`, `OSS_CONTRIBUTION_AI_GUIDE.md`, `COMMUNITY_FUNNEL.md`, `.playbook/checklists/ai-task-scoping.md`, project-root `AGENTS.md`, project-root `CLAUDE.md`, `DEVELOPMENT.md`, `package.json`, source tree scan, git state inspection, `A11yhood Analysis` research corpus (50 files across 6 directories). Previous plan: `bren-dev_branch_setup_plan_933d4b6f.plan.md`.
- **Delegation**: None. All reading, analysis, cross-checking, and writing performed by the primary model (claude-4.6-opus) in sessions on 2026-02-22.
- **Verification**: Verified by primary model against all source files read in this session.

---

## Why this plan replaces the previous one

The previous plan (`bren-dev_branch_setup_plan_933d4b6f`) was a well-constructed git workflow for creating a personal development branch. Its mechanical steps were correct. But cross-checking against the playbook's contributor funnel model (`COMMUNITY_FUNNEL.md`), the project's codebase gap analysis, the stakeholder-expressed priority of "vibe code safeguards, not product," and the empirical finding that narrow-scope plans complete at 8x the rate of broad plans -- the branch setup plan was the wrong *starting point*.

The project has no `CONTRIBUTING.md`, no PR template, no branch protection, no "good first issues," and no contributor onboarding documentation. Setting up a development branch before this infrastructure exists means coding against a project that has no formal process for receiving contributions. The corrected sequence: build the contributor infrastructure first, then set up the branch, then start coding.

---

## Plan structure

This plan is organized as **five independent phases**. Each phase is narrow-scope, has its own acceptance criteria, and can be completed in a single session (30-90 minutes per the playbook's session boundary rules). Phases 0-1 are non-code. Phases 2-3 involve environment setup and first code. Phase 4 establishes the ongoing cadence.

Per `LESSONS_LEARNED.md`: narrow-scope plans complete at 50%, broad plans at 6%, sprint plans at 7%. Each phase below is independently completable and independently valuable. If any phase stalls, the others still stand.

---

## Phase 0: Orientation -- research

### Scope

- Files affected: None (reading only)
- Estimated size: Narrow
- Cadence phase: Pre-cycle

### Context

Before contributing code or even non-code infrastructure, the contributor needs to understand the project's current state, governance model, priorities, and stakeholder expectations. This phase is comprehension-critical and cannot be delegated.

### Acceptance criteria

- [ ] Read project-root `AGENTS.md` (8 golden rules, 7 sections)
- [ ] Read project-root `CLAUDE.md` (same rules, Claude format)
- [ ] Read `.playbook/docs/PLAYBOOK.md` (capstone, 25 sections)
- [ ] Read `.playbook/docs/PROCESS_CADENCE.md` (build/refactor/stabilize cycle)
- [ ] Read `.playbook/docs/AI_TASK_DELEGATION_RULES.md` (what AI may not do)
- [ ] Read `.playbook/docs/LESSONS_LEARNED.md` (what works, what fails)
- [ ] Understand the CSUN March deadline and its Priority 1 showstoppers
- [ ] Understand Tony's guardrail framework: gold standard first, test-first, one function at a time, complexity removal as progress
- [ ] Understand the graduated AI contribution model (AIL-0/1/2) from `COMMUNITY_FUNNEL.md`

### Delegation guardrail

- **Comprehension-critical**: All reading in this phase. Understanding project norms, governance, priorities, and stakeholder expectations is the foundation for every subsequent phase. Must not be delegated or summarized by AI.
- **Delegation-safe**: None. This phase is entirely comprehension.

### Status note

If you have already completed the research analysis that produced the `A11yhood Analysis` corpus, much of this orientation is already done. Verify by spot-checking: can you name the project's 8 golden rules, the CSUN Priority 1 items, and Tony's core directive without looking them up? If yes, mark this phase complete.

---

## Phase 1: Non-code infrastructure contributions -- docs

### Scope

- Files affected: GitHub Issues (11 new), GitHub Discussion (1 new), possibly `CONTRIBUTING.md` (new file)
- Estimated size: Medium (but each sub-task is narrow)
- Cadence phase: Pre-cycle (infrastructure that enables the BUILD phase)

### Context

The codebase gap analysis identifies five full gaps in development workflow: no branch protection, no PR template, no "good first issues," no `CONTRIBUTING.md`, no contributor onboarding docs. These gaps make structured contribution impossible. This phase fills the most impactful gaps using non-code contributions -- the on-ramp the playbook's contributor funnel model prescribes for new contributors.

This phase also aligns with the contributor's documented role (AT specialist, community liaison, project manager, GitHub issue authoring) and the prioritized backlog items assigned to Brennen.

### Sub-tasks

Each sub-task is independently completable. Work on them in order, but any subset is valuable.

#### 1a. File the 11 GitHub issues from meeting outcomes

**Scope**: Narrow (one batch of related issues)
**Backlog reference**: Priority 4 — "File 11 GitHub issues from meeting outcomes (Brennen, drafts ready)"
**AI assistance**: AIL-0 (human-authored). Issue content derives from research analysis. AI must not draft issue text from the sensitive research data.

Before filing:
- [ ] Review each draft for accidental personal detail leakage (per `_SECURITY_README.md`: no health info, addresses, phone numbers, private opinions)
- [ ] Use the project's issue template format if templates exist; if not, use plain format with clear title, context, and acceptance criteria
- [ ] Search existing open AND closed issues first (`OSS_CONTRIBUTION_AI_GUIDE.md`: "do a quick check to make sure your idea hasn't been discussed elsewhere")
- [ ] One issue, one problem -- do not bundle

**Acceptance criteria**:
- [ ] All 11 issues filed on the upstream repository
- [ ] Each issue has a clear title, context, and at least one acceptance criterion
- [ ] No private meeting details or personal information in any issue
- [ ] Each issue is labeled appropriately using existing labels

#### 1b. Post the GitHub Discussion on tagging

**Scope**: Narrow (one discussion post)
**Backlog reference**: Priority 4 — "Post GitHub Discussion on tagging (Brennen, draft ready)"
**AI assistance**: AIL-0

- [ ] Post to GitHub Discussions (or Issues if Discussions is not enabled)
- [ ] Frame as a question/RFC, not a decision — invite community input
- [ ] Sanitize: no private meeting quotes or participant details

**Acceptance criteria**:
- [ ] Discussion posted
- [ ] Invites community input on tagging approach
- [ ] No private content

#### 1c. Coordinate with lead developer on contributor infrastructure

**Scope**: Narrow (communication, not code)
**AI assistance**: Not applicable (human-to-human)

Before creating CONTRIBUTING.md or PR templates, confirm with Tony:
- [ ] What are the current CSUN-blocking priorities? (Validate against research backlog)
- [ ] Is branch protection on `main` planned? When?
- [ ] Is a PR template with accessibility checklist wanted? What should it include?
- [ ] What are the 3-5 issues suitable for "good first issue" labeling?
- [ ] What is the AI disclosure policy? (Open decision OQ-2 from `LEAD_DEVELOPER_CHOICES_NEEDED.md`)
- [ ] What is the first-contribution threshold for AI-generated work? (Open decision OQ-2)

This step prevents creating infrastructure that doesn't match maintainer expectations. Per `OSS_CONTRIBUTION_AI_GUIDE.md`: "Respect community decisions."

**Acceptance criteria**:
- [ ] Lead developer has confirmed or adjusted the contributor infrastructure scope
- [ ] AI disclosure policy decision is recorded (even if "defer for now")
- [ ] At least 3 issues identified as "good first issue" candidates

#### 1d. Draft CONTRIBUTING.md

**Scope**: Narrow (one file)
**Backlog reference**: Codebase gap analysis — "Contributor workflow doc: full gap"
**AI assistance**: AIL-1 at most (human writes core content; AI may help with formatting only). The content of CONTRIBUTING.md encodes project understanding, making it comprehension-critical per `AI_TASK_DELEGATION_RULES.md`.

Content should cover:
- How to set up the development environment (reference `DEVELOPMENT.md` with Windows/PowerShell notes)
- How to find work (issue labels, "good first issue")
- How to submit changes (fork model, branch naming, PR expectations)
- Quality gates (`npm run lint`, `npm run build`)
- Accessibility requirements (WCAG 2.2 AA, focus-visible, touch targets, system preferences)
- AI usage policy (per lead developer decision from 1c)
- Code of conduct reference

**Acceptance criteria**:
- [ ] `CONTRIBUTING.md` exists in project root
- [ ] Covers environment setup, finding work, submitting changes, quality gates, accessibility, AI policy
- [ ] Matches project tone (warm, human -- not corporate; per `LESSONS_LEARNED.md` doc audit finding)
- [ ] Reviewed by lead developer before merge
- [ ] No AI doc bloat patterns (per `.playbook/checklists/ai-doc-bloat-scan.md`)

#### 1e. Label "good first issues"

**Scope**: Narrow
**Depends on**: 1a (issues filed) and 1c (issues identified)

- [ ] Apply "good first issue" label to 3-5 issues confirmed with lead developer
- [ ] Verify each is genuinely beginner-friendly: clear end condition, limited scope, no architectural knowledge required
- [ ] Per `COMMUNITY_FUNNEL.md`: "Keep 'good first issue' real — maintain a small, curated set of truly beginner-friendly issues; close or relabel when they stop being beginner-friendly"

**Acceptance criteria**:
- [ ] 3-5 issues labeled "good first issue"
- [ ] Each has clear context and acceptance criteria
- [ ] Each can be completed without deep codebase knowledge

### Delegation guardrail (Phase 1 overall)

- **Comprehension-critical**: Drafting issue content, writing CONTRIBUTING.md content, identifying good first issues. All require understanding of project context, stakeholder expectations, and accessibility requirements.
- **Delegation-safe**: Formatting, label application, markdown structure.
- **Verification**: [ ] All issue content and CONTRIBUTING.md prose written by the human contributor, not generated by AI.

---

## Phase 2: Development environment setup -- feature

### Scope

- Files affected: `.env.local` (created, not committed). No source modifications.
- Estimated size: Narrow (0 source files changed)
- Cadence phase: Pre-cycle

### Context

With contributor infrastructure in place (Phase 1), the development environment can now be set up with a clear purpose: to begin narrow-scope code contributions aligned with the project's stated priorities. This phase corresponds to the git workflow from the previous `bren-dev` plan, corrected for the actual workspace state.

### Current workspace state

The workspace (`a11yhood.github.io-main`) contains the full source tree but has an unborn `master` branch, no commits, no remotes, and no git history. This is consistent with a GitHub ZIP extraction. A fresh clone is recommended over re-initialization.

### Steps

**Step 2a: Fork the upstream repository on GitHub**

- Navigate to `https://github.com/a11yhood/a11yhood.github.io`
- Fork to your personal GitHub account
- Success: `https://github.com/<username>/a11yhood.github.io` exists

**Step 2b: Clone the fork locally (fresh start)**

Back up any local work from the current directory, then:

```powershell
git clone https://github.com/<username>/a11yhood.github.io.git
cd a11yhood.github.io
```

Verify: `git branch` shows `* main`.

**Step 2c: Configure upstream remote as fetch-only**

```powershell
git remote add upstream https://github.com/a11yhood/a11yhood.github.io.git
git remote set-url --push upstream no_push
git remote -v
```

Verify: four lines showing origin (fork, fetch+push) and upstream (a11yhood, fetch only, push = `no_push`).

**Step 2d: Sync and create bren-dev**

```powershell
git fetch upstream
git checkout main
git merge upstream/main
git checkout -b bren-dev
git push -u origin bren-dev
```

Verify on GitHub: branch dropdown shows `bren-dev`.

Note on branch naming: `bren-dev` intentionally deviates from the `feat/fix` convention because it is a personal integration branch, not a PR-ready topic branch. PR submissions come from single-purpose `feat/` or `fix/` branches created off `bren-dev`. Never open a PR from `bren-dev` directly.

**Step 2e: Install dependencies and verify quality gates**

```powershell
npm ci
npm run lint
npm run build
```

Note: `npm run build` executes `CI=true npm run test:run && tsc -b --noCheck && vite build`, so tests and TypeScript checking are included. A separate `npm run test:run` is redundant but harmless for early feedback.

Success: All commands exit 0.

**Step 2f: Set up local environment**

```powershell
Copy-Item env.example .env.local
```

Edit `.env.local` with required values:

```
VITE_SUPABASE_URL=<your-value>
VITE_SUPABASE_ANON_KEY=<your-value>
VITE_ENV=development
VITE_LOG_LEVEL=debug
```

Do NOT modify `env.example` (protected file per `AGENTS.md` section 2).

Verify: `git status` does NOT show `.env.local` as untracked (it's gitignored).

**Step 2g: Verify dev server**

```powershell
npm run dev
```

Verify Vite starts. Ctrl+C to stop.

### Acceptance criteria

- [ ] Local repo is a proper git clone with full history
- [ ] `main` tracks `upstream/main`
- [ ] `bren-dev` exists locally and on the fork
- [ ] `upstream` push URL = `no_push`
- [ ] `npm run lint` exits 0
- [ ] `npm run build` exits 0
- [ ] `.env.local` exists, gitignored, dev server starts
- [ ] No source files were modified

### Delegation guardrail

- **Comprehension-critical**: None. All steps are mechanical.
- **Delegation-safe**: All git commands, npm commands, file operations. AI may assist with troubleshooting if commands fail.

---

## Phase 3: First code contribution -- bug fix

### Scope

- Files affected: 1-3 files (narrow)
- Estimated size: Narrow
- Cadence phase: BUILD (first iteration)
- AI assistance: AIL-0 or AIL-1 only (human-first, per graduated contribution model)

### Context

The first code contribution should be a narrow-scope bug fix or accessibility fix drawn from CSUN Priority 1 or Quality Infrastructure Priority 2. Per `LESSONS_LEARNED.md`, bug fixes have the highest completion rate (50%) because they have clear end conditions.

The specific task should be selected based on the outcome of Phase 1c (coordination with lead developer). Candidates from the prioritized backlog:

**CSUN Priority 1 candidates** (accessibility fixes):
- Fix non-descriptive alt text (filenames + "image") — WCAG 1.1.1
- Fix language labeling on scraped non-English products — WCAG 3.1.2
- Fix error messages overlapping and auto-dismissing — WCAG 3.3.1
- Fix text resize breaking layout at 200% zoom — WCAG 1.4.4

**Quality Infrastructure Priority 2 candidates**:
- Create PR template with accessibility checklist (non-code, but creates workflow infrastructure)
- Add branch protection configuration (if maintainer agrees)

### Pre-task checklist (from `.playbook/checklists/ai-task-scoping.md`)

Before starting the code task:
- [ ] Task is one function or component (not a whole feature)
- [ ] Gold standard implementation exists for this pattern (or this IS the gold standard)
- [ ] Tests exist that define the expected behavior (or will be written first)
- [ ] Input files and output expectations are explicit
- [ ] Task runs inside the project environment tool (`npm run`)
- [ ] Task is on the AI-appropriate list (bug fix with clear end condition = appropriate)

### Workflow

1. Create a topic branch from `bren-dev`:

```powershell
git checkout bren-dev
git checkout -b fix/<short-description>
```

2. Write or verify tests exist for the behavior being fixed
3. Make the fix (1-3 files, narrow scope)
4. Run quality gates:

```powershell
npm run lint
npm run build
```

5. Rebase onto upstream/main before PR:

```powershell
git fetch upstream
git rebase upstream/main
git push -u origin fix/<short-description>
```

6. Open PR from `<username>:fix/<short-description>` to `a11yhood:main`
7. PR description must include: what problem it solves, how it was tested, accessibility impact

### Acceptance criteria

- [ ] One bug fix or accessibility fix completed
- [ ] Tests pass (existing + any new tests for the fix)
- [ ] `npm run lint` passes
- [ ] `npm run build` passes
- [ ] PR is scoped to one fix
- [ ] PR description explains the why, not just the what
- [ ] Commit uses conventional prefix (`fix:`)
- [ ] No protected files modified
- [ ] All interactive UI changes have `:focus-visible` ring, keyboard operability, accessible name
- [ ] Design tokens used (no hardcoded values)

### Delegation guardrail

- **Comprehension-critical**: Understanding the bug, reading the relevant component code, understanding the accessibility requirement being fixed. Writing the PR description.
- **Delegation-safe**: Running commands, formatting, mechanical code changes with explicit instructions.
- **Verification**: [ ] The fix was understood and verified by the human contributor, not blindly generated by AI.

---

## Phase 4: Establish the cadence -- docs

### Scope

- Files affected: None (process, not code)
- Estimated size: Narrow
- Cadence phase: Transition into the repeating BUILD/REFACTOR/STABILIZE cycle

### Context

After the first code contribution lands, establish the ongoing development rhythm. Per `PROCESS_CADENCE.md`: 50% build, 25% refactor, 25% stabilize. For a solo/small contributor, a 2-week cycle works: Week 1 build, 2 days refactor, 3 days stabilize.

### What this phase looks like

- **Select next task from the prioritized backlog** — always CSUN Priority 1 first, then Priority 2, then Priority 3
- **Scope each task narrowly** — one function or component, not a whole feature
- **Run the ai-task-scoping checklist** before every AI-assisted task
- **Follow the session boundary protocol** — 30-90 min sessions, break between sessions, re-read source material at session start if resuming
- **Run quality gates before every commit** — `npm run lint`, `npm run build`
- **Track completed work** — update issue status, close PRs, note what was learned

### Ongoing sync workflow

```powershell
git checkout bren-dev
git fetch upstream
git rebase upstream/main
git push --force-with-lease origin bren-dev
```

Force-push is ONLY safe for `bren-dev` (your personal branch). Topic branches with open PRs must NOT be force-pushed.

### Acceptance criteria

- [ ] Second code contribution submitted (demonstrates repeatable workflow)
- [ ] Contributor is comfortable with the fork → branch → PR → review → merge cycle
- [ ] Session length stays within 30-90 minutes
- [ ] Quality gates run before every commit

---

## Open decisions for lead developer

These items from `LEAD_DEVELOPER_CHOICES_NEEDED.md` and the research data's open questions directly affect this plan:

### OQ-2: First-contribution threshold for AI-generated work

**Question**: How many human-first contributions are required before AIL-2 work is accepted?
**Impact**: Determines when (if ever) Phase 3+ tasks can use AI-generated code.
**Options**: 1 / 3 / scaffolded complexity.
**Default if no decision**: No threshold enforced. Playbook recommends at least 1.

### OQ-2: AI disclosure model

**Question**: Three-level (AIL-0/1/2) or binary (human / AI-assisted)?
**Impact**: Determines disclosure format in PRs and commits from Phase 3 onward.
**Default if no decision**: Three-level model (already in playbook issue templates).

### Gap: Project-root AGENTS.md incomplete vs. playbook template

The project-root `AGENTS.md` has 8 golden rules; the playbook template has 9 (missing: "Give AI one function or component at a time"). Also missing: AI disclosure requirements, test-first rule, gold standard pattern, complexity-removal metric. Lead developer should decide whether to update project-root rule files.
**Default if no decision**: Project-root files remain as-is; playbook is supplementary.

### Open question #14 from research: "Good first issues" completed by AI without learning

**Question**: How should the project handle contributors who use AI to complete "good first issues" without actually learning the codebase?
**Impact**: Affects how Phase 1e issues are scoped and labeled.
**Default if no decision**: The graduated contribution model (human-first contributions before AIL-2) addresses this implicitly.

---

## Risks and guardrails

### Risk 1: Filing issues that expose private meeting content

**Risk**: The 11 drafted GitHub issues derive from the research analysis, which itself derives from private meeting transcripts. Personal details could leak into public issues.
**Guardrail**: Phase 1a includes explicit pre-filing review against `_SECURITY_README.md` rules. Each issue must be checked for personal health info, addresses, phone numbers, and private opinions before filing.
**Playbook enforcement**: `_SECURITY_README.md` — "No GitHub issues or PRs should be created that reference content from this analysis without explicit review and sanitization first."

### Risk 2: CONTRIBUTING.md doesn't match maintainer expectations

**Risk**: Drafting contributor docs without lead developer input could produce guidelines that conflict with Tony's guardrail framework.
**Guardrail**: Phase 1c (coordinate with lead developer) is sequenced BEFORE Phase 1d (draft CONTRIBUTING.md). The document is not filed until reviewed by the lead developer.
**Playbook enforcement**: `OSS_CONTRIBUTION_AI_GUIDE.md` — "Respect community decisions."

### Risk 3: Scope escape from narrow bug fix into broad refactor

**Risk**: The contributor starts a Phase 3 bug fix and discovers deeper issues, expanding scope. Per `LESSONS_LEARNED.md`, this is anti-pattern #1 (scope overload) and #3 (feature completion drift).
**Guardrail**: Phase 3 pre-task checklist requires "task is one function or component." If the fix reveals deeper issues, file a new issue and keep the PR narrow.
**Playbook enforcement**: `PROCESS_CADENCE.md` no-scope-escape rule — "Work outside the assigned plan is forbidden until the plan's exit criteria are confirmed."

### Risk 4: Stale workspace from ZIP extraction

**Risk**: The current workspace has no git history. Starting work from it would lack upstream tracking and merge capability.
**Guardrail**: Phase 2b explicitly starts with a fresh clone. The existing directory should be backed up then replaced.
**Playbook enforcement**: `LESSONS_LEARNED.md` success pattern #5 — "Forensic audits before building."

### Risk 5: AI-generated first contribution undermines trust

**Risk**: If the first PR contains AI-generated code, it undermines the graduated contribution model and may not demonstrate genuine understanding of the codebase.
**Guardrail**: Phase 3 is explicitly scoped as AIL-0 or AIL-1 (human-first). The contributor should demonstrate understanding of the fix, not just generate a passing solution.
**Playbook enforcement**: `COMMUNITY_FUNNEL.md` graduated first-contribution restriction.

### Risk 6: CSUN deadline pressure causes quality shortcuts

**Risk**: The March CSUN conference creates time pressure that could push contributors toward broad, rushed changes instead of narrow, verified ones.
**Guardrail**: Each phase has independent acceptance criteria. A narrow fix that ships is better than a broad fix that stalls. Per `LESSONS_LEARNED.md`: 50% of narrow plans complete vs. 6% of broad plans.
**Playbook enforcement**: `LESSONS_LEARNED.md` — "Narrow-scope plans complete at 8x the rate of broad-scope plans."

### Risk 7: Session boundary context loss

**Risk**: If any phase spans multiple AI sessions, carried-over context may produce confident but inaccurate work.
**Guardrail**: Each phase has explicit acceptance criteria that can be verified at the start of a resumed session. Re-read source documents before producing derivatives.
**Playbook enforcement**: `SESSION_BOUNDARY_PROTOCOL.md` — re-read before rewrite rule.

---

## Safety checklist (for ongoing use from Phase 3 onward)

### Pre-commit

- [ ] No protected files modified (`LICENSE`, `CNAME`, `env.example`, `.env*`)
- [ ] No secrets or `.env` files staged
- [ ] Commits use conventional prefixes (`feat:`, `fix:`, `docs:`, `test:`, `chore:`)

### Pre-PR (quality gates per AGENTS.md section 7)

- [ ] `npm run lint` passes
- [ ] `npm run build` passes (includes tests + TypeScript check + Vite build)
- [ ] Branch is rebased on latest `upstream/main`
- [ ] PR is scoped to one feature or fix

### Accessibility (per AGENTS.md section 5)

- [ ] All interactive UI has `:focus-visible` ring
- [ ] All interactive UI is keyboard operable
- [ ] All interactive UI has an accessible name
- [ ] Touch targets: 44x44px minimum
- [ ] Icon-only buttons have `aria-label`
- [ ] Design tokens used for all colors, spacing, font sizes, z-index
- [ ] Animations respect `prefers-reduced-motion: reduce`
- [ ] All five system preference media queries respected
- [ ] Radix UI/shadcn `aria-*`, `role`, `data-*` attributes preserved
- [ ] Semantic HTML before ARIA

### Security (per AGENTS.md section 6)

- [ ] Security headers not weakened
- [ ] No `unsafe-eval` or `unsafe-inline` in CSP
- [ ] DOMPurify used when rendering user-generated HTML
- [ ] Only `VITE_SUPABASE_ANON_KEY` exposed client-side

### AI usage (per playbook)

- [ ] AI bloat scan passed (no narrating comments, no hallucinated imports, no phantom dependencies)
- [ ] Comprehension-critical tasks not delegated
- [ ] AI-generated code has pre-existing or human-written tests (test-first rule)
- [ ] Post-AI-edit verification completed

---

## Phase sequence summary

| Phase | Type | Scope | AI level | Depends on | Est. time |
|-------|------|-------|----------|------------|-----------|
| 0: Orientation | Research | Narrow | N/A | Nothing | 60-90 min |
| 1a: File 11 issues | Docs | Narrow | AIL-0 | Phase 0 | 60-90 min |
| 1b: Post tagging discussion | Docs | Narrow | AIL-0 | Phase 0 | 15-30 min |
| 1c: Coordinate with lead dev | Communication | Narrow | N/A | Phase 0 | 30 min |
| 1d: Draft CONTRIBUTING.md | Docs | Narrow | AIL-0/1 | Phase 1c | 60-90 min |
| 1e: Label good first issues | Docs | Narrow | AIL-0 | Phase 1a + 1c | 15 min |
| 2: Environment setup | Infrastructure | Narrow | Delegation-safe | Phase 0 | 30-45 min |
| 3: First code contribution | Bug fix | Narrow | AIL-0/1 | Phase 2 + 1c | 60-90 min |
| 4: Establish cadence | Process | Narrow | Varies | Phase 3 | Ongoing |

Phases 1 and 2 are independent of each other and can run in parallel. Phase 3 requires both.

---

## Key playbook findings informing this plan

| Finding | Source | How it shaped this plan |
|---------|--------|------------------------|
| Narrow plans: 50% completion. Broad plans: 6%. | `LESSONS_LEARNED.md` | Every phase is independently narrow |
| Sprint plans: 7% completion | `LESSONS_LEARNED.md` | Plan is phased, not a single sprint |
| Bug fixes: 50% completion (highest) | `LESSONS_LEARNED.md` | First code contribution is a bug fix |
| "Vibe code safeguards, not product" | `ai-coding-guardrails.md` (research) | Phases 1-2 build infrastructure before features |
| Contributor funnel: user -> casual -> repeat -> maintainer | `COMMUNITY_FUNNEL.md` | Non-code contributions before code |
| First contributions should be human-first | `COMMUNITY_FUNNEL.md` | Phase 3 scoped as AIL-0/1 |
| AI sessions: 30-90 min max | `PROCESS_CADENCE.md` | Each phase estimated within bounds |
| Written rules achieve ~30% AI compliance | `PROCESS_CADENCE.md` | Safety checklist as manual enforcement |
| Comprehension delegation poisons research base | `AI_TASK_DELEGATION_RULES.md` | Orientation and CONTRIBUTING.md marked comprehension-critical |
| Session boundary = delegation to lower tier | `SESSION_BOUNDARY_PROTOCOL.md` | Each phase has verifiable acceptance criteria for session resumption |
| No contributor onboarding docs exist | `codebase-gap-analysis.md` (research) | Phase 1 creates this infrastructure |
| 11 issues drafted, ready to file | `prioritized-backlog.md` (research) | Phase 1a uses existing work |
