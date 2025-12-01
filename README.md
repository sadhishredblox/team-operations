# Team Documentation Wiki

This repository contains the GitHub Wiki documentation for our team.

## Structure

```
├── Home.md                                        # Wiki homepage
├── _Sidebar.md                                    # Wiki sidebar navigation
├── _Footer.md                                     # Wiki footer
│
├── Processes & Guidelines
│   ├── Daily-Standup-Posting-Guidelines.md        # Standup process documentation
│   └── Work-Discipline-and-Communication-Standards.md  # Work discipline & communication
│
├── Development
│   └── GitHub-Workflow-and-Best-Practices.md      # Git workflow, branches, PRs, reviews
│
└── README.md                                      # This file
```

## How to Use

### Option 1: GitHub Wiki (Recommended)

1. Create a new repository on GitHub
2. Go to the **Wiki** tab
3. Copy the contents of each `.md` file into corresponding wiki pages
4. The `_Sidebar.md` and `_Footer.md` files will automatically be used by GitHub Wiki

### Option 2: Clone Wiki Directly

If you have an existing repository with a wiki:

```bash
git clone https://github.com/YOUR_ORG/YOUR_REPO.wiki.git
# Copy these files into the cloned wiki repo
git add .
git commit -m "Add team documentation"
git push
```

## File Naming Convention

- Use hyphens (`-`) instead of spaces in filenames
- Example: `Daily-Standup-Posting-Guidelines.md`
- This creates cleaner URLs: `wiki/Daily-Standup-Posting-Guidelines`

## Adding New Documentation

1. Create a new `.md` file with hyphenated name
2. Add a link in `Home.md` under the appropriate category
3. Add a link in `_Sidebar.md` for navigation

## Current Documentation

### Processes & Guidelines

| Document | Description |
|----------|-------------|
| [Daily Standup Posting Guidelines](Daily-Standup-Posting-Guidelines.md) | Morning/evening standup templates, blocker guidelines, and FAQ |
| [Work Discipline & Communication Standards](Work-Discipline-and-Communication-Standards.md) | Work hours, attendance, leave policies, and communication expectations |

### Development

| Document | Description |
|----------|-------------|
| [GitHub Workflow & Best Practices](GitHub-Workflow-and-Best-Practices.md) | Branch naming, commit messages, PR process, code reviews, and merge strategies |
