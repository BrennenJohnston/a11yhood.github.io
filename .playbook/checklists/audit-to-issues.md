# Audit Finding to GitHub Issue Checklist

Run this checklist when converting accessibility audit findings into individual
GitHub issues. Each audit finding should become one issue with clear acceptance
criteria, scope guard, and severity mapping.

## Steps

| # | Step | Detail | Done? |
| --- | --- | --- | --- |
| 1 | Read audit finding | Record: severity, WCAG criterion, affected component, reproduction steps. | [ ] |
| 2 | Check for existing issue | Search GitHub issues (open AND closed) for the same component + criterion combination. If a closed issue exists, determine whether it was actually fixed or just closed. | [ ] |
| 3 | Create issue from template | Use the `accessibility_issue.md` template. Fill in all sections. | [ ] |
| 4 | Map severity | Audit "Severe" → P0, Audit "Moderate" → P1, Audit "Minor" → P2. | [ ] |
| 5 | Add scope guard | Identify allowed files (components that need to change) and out-of-scope files (components that must not be touched). | [ ] |
| 6 | Write acceptance criteria | Convert the audit's expected behavior into a testable condition: "This issue is fixed when [specific, measurable outcome]." | [ ] |
| 7 | Add labels | Apply labels: `a11y` + severity (`P0` / `P1` / `P2`) + component area (e.g., `nav`, `forms`, `content`). Add `good first issue` if the fix is scoped to CSS or a single HTML attribute change. | [ ] |

## Copy-paste checklist

```markdown
### Audit-to-issue conversion

- [ ] Audit finding read (severity, WCAG criterion, reproduction steps)
- [ ] Searched existing GitHub issues (open and closed)
- [ ] Issue created using accessibility_issue.md template
- [ ] Severity mapped (Severe→P0, Moderate→P1, Minor→P2)
- [ ] Scope guard added (allowed files, out-of-scope files)
- [ ] Acceptance criteria written (testable condition)
- [ ] Labels applied (a11y + severity + component area)
```

## Severity mapping reference

| Audit severity | Issue priority | Meaning |
| --- | --- | --- |
| Severe | P0 | Blocks a complete task for AT users |
| Moderate | P1 | Workaround exists but experience is degraded |
| Minor | P2 | Cosmetic or non-blocking issue |
