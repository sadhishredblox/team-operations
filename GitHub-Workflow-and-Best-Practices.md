# GitHub Workflow & Best Practices

A standardized process for managing code, branches, commits, pull requests, and reviews across all teams and projects.

---

## Table of Contents

- [Branch Naming Conventions](#1-branch-naming-conventions)
- [Commit Message Guidelines](#2-commit-message-guidelines)
- [Pull Request (PR) Process](#3-pull-request-pr-process)
- [Code Review Guidelines](#4-code-review-guidelines)
- [Merge Strategy](#5-merge-strategy)
- [Tagging Releases](#6-tagging-releases)
- [Branch Lifecycle](#7-branch-lifecycle)
- [Environment Rules](#8-environment-rules)
- [Best Practices Summary](#9-best-practices-summary)

---

## 1. Branch Naming Conventions

Branches RBXt follow a consistent naming structure to improve clarity, traceability, and automation.

### Format

```
<prefix>/<PROJECT-TicketNumber>-short-description
```

### Allowed Prefixes

| Prefix | Usage |
|--------|-------|
| `feature/` | New features or functionality |
| `bug/` | Bug fixes & defect resolutions |
| `hotfix/` | Urgent issues affecting production |
| `docs/` | Documentation updates |
| `refactor/` | Code quality improvements without behavior changes |
| `chore/` | Maintenance tasks, config, dependencies |
| `test/` | Testing-related changes |

### Example Branch Names

```
feature/RBX-15-add-playlist-export
bug/RBX-23-fix-spotify-auth
docs/RBX-9-getting-started-guide
hotfix/RBX-31-critical-auth-fix
refactor/RBX-44-cleanup-player-component
chore/RBX-52-update-dependencies
```

---

## 2. Commit Message Guidelines

Write clean, informative commit messages. Avoid vague or meaningless text such as "Update code", "Fix bug", "Changes", etc.

### Commit Format

```
<type>(ticket): short description

[Optional] Detailed explanation of what changed & why
```

### Commit Types

| Type | Purpose |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Formatting only (no logic changes) |
| `refactor` | Code restructuring |
| `test` | Add or update tests |
| `chore` | Maintenance, build or dependency changes |
| `perf` | Performance improvements |

### Good Commit Examples

```
feat(RBX-15): add playlist export functionality
fix(RBX-23): resolve token refresh issue for Spotify login
docs(RBX-9): update installation guide with new environment setup steps
refactor(RBX-44): improve player component state structure
```

### ❌ Bad Examples

```
fixed bug
changes made
update file
stuff done
```

---

## 3. Pull Request (PR) Process

### PR Requirements

- ✅ PR title RBXt reference ticket
- ✅ PR RBXt be assigned to at least one reviewer
- ✅ CI checks RBXt pass before merge
- ✅ Include screenshots / videos for UI updates
- ✅ Include test cases if relevant
- ✅ Provide context and reasoning

### PR Title Format

```
[RBX-15] Add playlist export feature
```

### PR Description Template

```markdown
### Summary
Brief explanation of what the change accomplishes.

### Ticket
https://linear.app/team/RBX-15

### Changes
- Item 1
- Item 2
- Item 3

### Screenshots / Recordings (if UI related)

### Testing Instructions
Steps to test this change

### Checklist
- [ ] Code follows standards
- [ ] Added tests if needed
- [ ] No console errors
- [ ] Works in staging environment
```

---

## 4. Code Review Guidelines

### For Authors

- Ensure code is clean, formatted, linted
- Remove unused imports & dead code
- Squash or organize commits if messy
- Don't assign reviewers until PR is ready

### For Reviewers

| ✅ DO | ❌ DON'T |
|-------|----------|
| Review within 24 hours | Delay review without reason |
| Give constructive feedback | Nitpick non-essential preferences |
| Suggest improvements clearly | Request unnecessary rewrites |
| Understand purpose before commenting | Merge without thorough check |

### Approval Rules

| Environment | Requirement |
|-------------|-------------|
| Dev branch | At least 1 approval |
| Staging | QA verified + reviewer approved |
| Production | Lead approval + successful QA |

---

## 5. Merge Strategy

| Branch | Strategy |
|--------|----------|
| feature → dev | Squash & merge |
| dev → staging | Merge commit |
| staging → main | Merge commit (release tag required) |
| hotfix → main & dev | Cherry-pick if necessary |

### Why Squash & Merge for features

- Keeps history clean
- One commit per feature
- Easier rollback

---

## 6. Tagging Releases

### Format

```
vMajor.Minor.Patch
```

### Examples

```
v1.0.0
v2.4.1
v3.0.0-beta.1
```

---

## 7. Branch Lifecycle

```
main (production)
   └── staging (release testing)
        └── dev (development integration)
             └── feature/bug/docs branches
```

### Flow Diagram

```
feature/RBX-15-add-export
         │
         ▼
        dev ──────────► staging ──────────► main
         │                 │                  │
    (squash merge)    (merge commit)    (merge + tag)
```

---

## 8. Environment Rules

| Environment | Purpose |
|-------------|---------|
| **Local** | Development |
| **Dev** | Integration testing |
| **Staging** | Pre-production QA |
| **Production** | Live users |

---

## 9. Best Practices Summary

### ✅ Do

- Commit early & often
- Keep PRs small and focused
- Write meaningful commit messages
- Use ticket references everywhere
- Communicate breaking changes
- Review PRs promptly
- Test before pushing

### ❌ Don't

- Push directly to `dev`, `staging`, or `main`
- Open massive PRs with no structure
- Leave PRs idle without updating
- Add temporary console logs / debug code
- Merge without approvals
- Force push to shared branches
- Ignore CI failures

---

## Quick Reference Card

| Action | Format |
|--------|--------|
| **Branch** | `feature/RBX-15-short-desc` |
| **Commit** | `feat(RBX-15): description` |
| **PR Title** | `[RBX-15] Feature description` |
| **Tag** | `v1.2.3` |

---

> **Remember:** Good Git hygiene makes collaboration smoother, debugging easier, and releases safer. When in doubt, communicate and ask for guidance.
