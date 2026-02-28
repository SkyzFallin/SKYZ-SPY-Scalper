# Repository Audit & Improvement Roadmap

## Scope
This audit reviews the current repository structure, documentation quality, and GitHub hardening opportunities.

Current state snapshot:
- Core docs: `README.md`
- Asset: `banner.svg`
- No source-code directory or build/test pipeline checked in yet.

## Executive Summary
The project branding and strategy explanation are clear, but the repository is currently "documentation-first" with limited engineering guardrails. The fastest way to level up quality and trust is to add:

1. **Security baseline automation** (CodeQL + Dependabot)
2. **Responsible disclosure policy** (`SECURITY.md`)
3. **Community/process scaffolding** (issue templates, contribution guidance)
4. **Code-quality automation once script/code is added** (lint/tests/CI)

## Findings & Recommendations

### 1) Security posture is currently manual
**Risk:** Vulnerabilities and insecure dependencies can go undetected as the project grows.

**Recommendation:**
- Add **CodeQL** scanning (currently configured for GitHub Actions workflows, with easy expansion to app languages when code is added).
- Add **Dependabot** updates for GitHub Actions and package ecosystems once present.
- Enforce branch protection in GitHub settings (required PR reviews + required checks).

**Status in this patch:** Implemented (`.github/workflows/codeql.yml`, `.github/dependabot.yml`).

---

### 2) No security disclosure channel
**Risk:** Researchers/users have no clear path to report security issues privately.

**Recommendation:**
- Add `SECURITY.md` with reporting contact and response expectations.

**Status in this patch:** Implemented (`SECURITY.md`).

---

### 3) No standardized issue intake
**Risk:** Bug reports/instructions become inconsistent and harder to triage.

**Recommendation:**
- Add GitHub Issue Forms (bug report + feature request).
- Consider adding labels + triage automation in future.

**Status in this patch:** Implemented (`.github/ISSUE_TEMPLATE/bug_report.yml`, `.github/ISSUE_TEMPLATE/feature_request.yml`).

---

### 4) Missing contributor and engineering standards docs
**Risk:** New contributors have no coding standards, local setup, or PR expectations.

**Recommendation (next steps):**
- Add `CONTRIBUTING.md` with:
  - local setup steps
  - branch naming and commit message conventions
  - testing/linting requirements
- Add `CODE_OF_CONDUCT.md` and `LICENSE` if not yet configured.

---

### 5) Strategy code should be versioned directly
**Risk:** Indicator logic may be shared externally but not reproducible/auditable in-repo.

**Recommendation (next steps):**
- Add a `src/` folder with the actual indicator script(s).
- Add changelog entries for parameter and logic changes.
- Add deterministic test fixtures where possible (e.g., static candles and expected signal timestamps).

---

## "Cooler" Enhancements (High value)

1. **Backtest transparency dashboard**
   - Add a `docs/performance.md` with methodology and monthly snapshots.
2. **Release notes + semantic versioning**
   - Tag each strategy update with rationale and impact.
3. **Visual examples**
   - Add chart screenshots/GIFs for valid vs invalid setups.
4. **Parameter matrix docs**
   - Explain how 5/10/15 minute profile constants differ numerically.
5. **Roadmap board**
   - Use GitHub Projects for milestones (signal quality, risk model, UX overlays).

## Suggested 30-Day Plan

### Week 1
- Add contribution docs (`CONTRIBUTING.md`, `LICENSE`, `CODE_OF_CONDUCT.md`).
- Turn on branch protection rules.

### Week 2
- Commit indicator source code and establish folder structure.
- Add basic CI checks (format/lint/unit tests where applicable).

### Week 3
- Add sample datasets/screenshots and signal validation examples.
- Publish release v0.1.0 with changelog.

### Week 4
- Track metrics: issue response time, PR cycle time, release cadence.
- Iterate on templates and automation.

## KPI Ideas
- Median issue triage time < 48h
- PR time-to-merge < 3 days
- >= 1 tagged release per month
- 100% of PRs linked to issue or roadmap item

---
If you want, the next step can be a **"production-ready GitHub foundation"** pass that adds branch protection checklist, conventional commits, release workflow, and docs automation.
