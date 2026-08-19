<!-- markdownlint-disable -->

# Hardening Report: jdiegosierra--contributor-report/v1.3.2

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jdiegosierra--contributor-report/v1.3.2** was hardened automatically. 8 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All `uses:` references in check-dist.yml use version tags instead of pinned 40-character SHA commit hashes: `actions/checkout@v6`, `pnpm/action-setup@v5`, `actions/setup-node@v6`, `actions/upload-artifact@v7`.

Locations:

- `.github/workflows/check-dist.yml:29`
- `.github/workflows/check-dist.yml:33`
- `.github/workflows/check-dist.yml:36`
- `.github/workflows/check-dist.yml:62`

### unpinned-uses (severity: high)

All `uses:` references in ci.yml use version tags instead of pinned 40-character SHA commit hashes: `actions/checkout@v6`, `pnpm/action-setup@v5`, `actions/setup-node@v6` (used in both jobs).

Locations:

- `.github/workflows/ci.yml:22`
- `.github/workflows/ci.yml:25`
- `.github/workflows/ci.yml:28`
- `.github/workflows/ci.yml:48`
- `.github/workflows/ci.yml:51`
- `.github/workflows/ci.yml:54`

### unpinned-uses (severity: high)

All `uses:` references in codeql-analysis.yml use version tags instead of pinned 40-character SHA commit hashes: `actions/checkout@v6`, `github/codeql-action/init@v4`, `github/codeql-action/autobuild@v4`, `github/codeql-action/analyze@v4`.

Locations:

- `.github/workflows/codeql-analysis.yml:26`
- `.github/workflows/codeql-analysis.yml:31`
- `.github/workflows/codeql-analysis.yml:38`
- `.github/workflows/codeql-analysis.yml:43`

### unpinned-uses (severity: high)

The `uses:` reference in contributor-report.yml uses a version tag instead of a pinned 40-character SHA commit hash: `actions/checkout@v6`.

Locations:

- `.github/workflows/contributor-report.yml:18`

### unpinned-uses (severity: high)

All `uses:` references in dependabot-auto-merge.yml use version tags instead of pinned 40-character SHA commit hashes: `dependabot/fetch-metadata@v2`, `actions/checkout@v6`, `pnpm/action-setup@v5`, `actions/setup-node@v6`.

Locations:

- `.github/workflows/dependabot-auto-merge.yml:11`
- `.github/workflows/dependabot-auto-merge.yml:17`
- `.github/workflows/dependabot-auto-merge.yml:23`
- `.github/workflows/dependabot-auto-merge.yml:28`

### unpinned-uses (severity: high)

All `uses:` references in licensed.yml use version tags instead of pinned 40-character SHA commit hashes: `actions/checkout@v6`, `actions/setup-node@v6`, `ruby/setup-ruby@v1`, `licensee/setup-licensed@v1.3.2`.

Locations:

- `.github/workflows/licensed.yml:27`
- `.github/workflows/licensed.yml:32`
- `.github/workflows/licensed.yml:38`
- `.github/workflows/licensed.yml:41`

### unpinned-uses (severity: high)

All `uses:` references in linter.yml use version tags instead of pinned 40-character SHA commit hashes: `actions/checkout@v6`, `pnpm/action-setup@v5`, `actions/setup-node@v6`, `super-linter/super-linter/slim@v8`.

Locations:

- `.github/workflows/linter.yml:28`
- `.github/workflows/linter.yml:32`
- `.github/workflows/linter.yml:35`
- `.github/workflows/linter.yml:42`

### unpinned-uses (severity: high)

All `uses:` references in release-please.yml use version tags instead of pinned 40-character SHA commit hashes: `googleapis/release-please-action@v4`, `actions/checkout@v6`.

Locations:

- `.github/workflows/release-please.yml:14`
- `.github/workflows/release-please.yml:20`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all unpinned `uses:` references across 8 workflow files:
- check-dist.yml: actions/checkout@v6 → @d23441a4, pnpm/action-setup@v5 → @fc06bc12, actions/setup-node@v6 → @24997072, actions/upload-artifact@v7 → @043fb46d
- ci.yml: same checkout/pnpm/setup-node pins applied to both jobs
- codeql-analysis.yml: actions/checkout@v6 → @d23441a4, github/codeql-action/{init,autobuild,analyze}@v4 → @e0647621
- contributor-report.yml: actions/checkout@v6 → @d23441a4
- dependabot-auto-merge.yml: dependabot/fetch-metadata@v2 → @21025c70, plus checkout/pnpm/setup-node
- licensed.yml: actions/checkout@v6 → @d23441a4, actions/setup-node@v6 → @24997072, ruby/setup-ruby@v1 → @a30dfa45, licensee/setup-licensed@v1.3.2 → @0d52e575
- linter.yml: checkout/pnpm/setup-node pins, super-linter/super-linter/slim@v8 → @4ce20838
- release-please.yml: googleapis/release-please-action@v4 → @5c625bfb, actions/checkout@v6 → @d23441a4

Note: licensed.yml and linter.yml were corrupted by overlapping edits and were rewritten in full with correct content.

