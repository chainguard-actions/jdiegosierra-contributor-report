<!-- markdownlint-disable -->

# Hardening Report: jdiegosierra--contributor-report/v1.3.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jdiegosierra--contributor-report/v1.3.3** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All workflow files use mutable tag-based or version-string `uses:` references instead of immutable 40-character SHA commit pins. This exposes the workflows to supply-chain attacks if any referenced action's tag is moved or compromised. Affected references include: actions/checkout@v6, pnpm/action-setup@v5, actions/setup-node@v6, actions/upload-artifact@v7, github/codeql-action/init@v4, github/codeql-action/autobuild@v4, github/codeql-action/analyze@v4, dependabot/fetch-metadata@v2, ruby/setup-ruby@v1, licensee/setup-licensed@v1.3.2, super-linter/super-linter/slim@v8, googleapis/release-please-action@v4.

Locations:

- `.github/workflows/check-dist.yml:32`
- `.github/workflows/check-dist.yml:35`
- `.github/workflows/check-dist.yml:38`
- `.github/workflows/check-dist.yml:72`
- `.github/workflows/ci.yml:22`
- `.github/workflows/ci.yml:25`
- `.github/workflows/ci.yml:28`
- `.github/workflows/ci.yml:52`
- `.github/workflows/ci.yml:55`
- `.github/workflows/ci.yml:58`
- `.github/workflows/codeql-analysis.yml:26`
- `.github/workflows/codeql-analysis.yml:31`
- `.github/workflows/codeql-analysis.yml:37`
- `.github/workflows/codeql-analysis.yml:42`
- `.github/workflows/contributor-report.yml:18`
- `.github/workflows/dependabot-auto-merge.yml:12`
- `.github/workflows/dependabot-auto-merge.yml:17`
- `.github/workflows/dependabot-auto-merge.yml:23`
- `.github/workflows/dependabot-auto-merge.yml:28`
- `.github/workflows/licensed.yml:26`
- `.github/workflows/licensed.yml:31`
- `.github/workflows/licensed.yml:40`
- `.github/workflows/licensed.yml:44`
- `.github/workflows/linter.yml:30`
- `.github/workflows/linter.yml:33`
- `.github/workflows/linter.yml:36`
- `.github/workflows/linter.yml:49`
- `.github/workflows/release-please.yml:16`
- `.github/workflows/release-please.yml:23`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all mutable tag-based `uses:` references to immutable 40-character SHA commits across 8 workflow files:
- check-dist.yml: actions/checkout@v6, pnpm/action-setup@v5, actions/setup-node@v6, actions/upload-artifact@v7
- ci.yml: actions/checkout@v6 (×2), pnpm/action-setup@v5 (×2), actions/setup-node@v6 (×2)
- codeql-analysis.yml: actions/checkout@v6, github/codeql-action/init@v4, github/codeql-action/autobuild@v4, github/codeql-action/analyze@v4
- contributor-report.yml: actions/checkout@v6
- dependabot-auto-merge.yml: dependabot/fetch-metadata@v2, actions/checkout@v6, pnpm/action-setup@v5, actions/setup-node@v6
- licensed.yml: actions/checkout@v6, actions/setup-node@v6, ruby/setup-ruby@v1, licensee/setup-licensed@v1.3.2
- linter.yml: actions/checkout@v6, pnpm/action-setup@v5, actions/setup-node@v6, super-linter/super-linter/slim@v8
- release-please.yml: googleapis/release-please-action@v4, actions/checkout@v6

All original tags preserved as inline comments (e.g., `# v6`) for readability. SHAs were resolved using lookup_action_sha.

