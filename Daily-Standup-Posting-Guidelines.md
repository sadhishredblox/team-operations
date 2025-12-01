# Daily Standup Posting Guidelines

A structured communication process that ensures visibility, accountability, and efficient collaboration across multiple ongoing projects.

---

## Table of Contents

- [Standup Schedule](#standup-schedule)
- [Standup Format & Templates](#standup-format--templates)
- [Good vs Bad Standup Examples](#good-vs-bad-standup-examples)
- [Best Practices](#best-practices-for-effective-standups)
- [Writing Good Blockers](#writing-good-blockers)
- [FAQ](#faq)

---

## Standup Schedule

### Morning Standup Post

| | |
|---|---|
| **When** | Start of your workday (9:00 AM – 10:30 AM IST) |
| **What to post** | What I'm doing today |

**Purpose:**
- Set clear intentions for the day
- Provide visibility across teams and projects
- Align on priorities and dependencies
- Enable early feedback if required

---

### Evening Standup Post

| | |
|---|---|
| **When** | End of your workday (after 7:00 PM IST) |
| **What to post** | What I did today + Blockers + Notes |

**Purpose:**
- Report on progress and completed work
- Surface blockers immediately
- Facilitate overnight review and direction for next morning

---

### Review & Feedback Cycle

| | |
|---|---|
| **When** | Evening / Night IST |

**Actions:**
- Leads review standup posts
- Blockers are discussed and resolved
- Guidance and feedback provided as required
- Plans refined for the next day

---

## Standup Format & Templates

### Morning Post Template

```markdown
**Morning Standup - [Your Name] - [Date]**

**Projects & Tasks for Today:**
[Project Name]
- [ ] Task 1: [Brief description] — [Ticket / PR link]
- [ ] Task 2: [Brief description] — [Ticket / PR link]

[Project Name]
- [ ] Task 3: [Brief description]

**Context / Priority Notes (Optional):**
[Any clarification, questions, deadlines, or dependency notes]
```

#### Example

```markdown
**Morning Standup - Priya Sharma - Oct 1, 2025**

**Projects & Tasks for Today:**
Swypatune
- [ ] Implement social sharing for round results — ML-342
- [ ] Code review for Chris's voting UI PR

Swype App
- [ ] Fix navigation bug on iPhone 12 mini — BUG-128

**Context:**
Prioritizing social sharing for Friday release. Will sync with design if preview layout needs adjustments.
```

---

### Evening Post Template

```markdown
**Evening Standup - [Your Name] - [Date]**

**What I Did Today:**
[Project Name]
- [DONE] Task 1 — [PR / Commit link]
- [IN PROGRESS] Task 2 — [Current state / % done / next steps]

[Project Name]
- [DONE] Task 3 — [Details]

**Blockers:**
- [Describe blocker, impact, and what or who is needed]

OR

**Blockers:** None today!

**Notes (Optional):**
[Testing coverage, learnings, dependencies, next steps]
```

#### Example

```markdown
**Evening Standup - Priya Sharma - Oct 1, 2025**

**What I Did Today:**
Swypatune
- [DONE] Implemented social sharing for round results — PR #842 (ready for review)
- [IN PROGRESS] Code review for Chris's voting UI (60%, will complete tomorrow)

Swype App
- [DONE] Fixed navigation bug on iPhone 12 mini — BUG-128 (merged)

**Blockers:**
- Twitter preview images not showing. OG tags valid, but validator shows 404.
  Need support: @chris to review CDN caching or meta generation.

**Notes:**
Bug fix also resolves mini/SE screen edge cases; screenshots added to PR.
```

---

## Good vs Bad Standup Examples

### GOOD Examples

#### ✅ Specific & actionable

```markdown
[DONE] Fixed PWA side navigation z-index bug (BUG-156)
- Beacon widget now visible when offcanvas is open
- PR #847 merged, tested on 5 viewports
```

#### ✅ Clear blockers

```markdown
**Blockers:**
Can't complete Stripe integration testing — missing test API keys.
Need: test_pk / test_sk for sandbox environment.
```

#### ✅ Provides context

```markdown
**Context:**
Focusing on voting UI refactor — final blocker for mobile 2.5 release due Thursday EOD.
```

---

### ❌ Avoid These

#### Too vague

```
Working on bugs
Doing some coding
Testing stuff
```

#### No context

```
Fixed the thing
Updated file
Merged PR
```

#### Confusing blockers

```
Blockers:
- Something is broken
- Waiting on someone
- API doesn't work
```

---

## Best Practices for Effective Standups

### ✅ Do This

#### Use clear status indicators

| Status | Meaning |
|--------|---------|
| `[DONE]` | Completed |
| `[IN PROGRESS]` | Active |
| `[PAUSED]` | Blocked |
| `[NEXT]` | Next task |

#### Include links

- PR links (`#ID`)
- Ticket numbers
- Documentation URLs
- Commit references

#### Quantify work

| Instead of | Write |
|------------|-------|
| "Fixed bugs" | "Fixed 5 bugs" |
| "Optimized performance" | "Improved load time by 60%" |

#### Describe impact

- "Unblocks mobile release"
- "Fixes top customer complaint"

### ❌ Avoid

- Vague or filler updates
- Hiding blockers
- Saying "almost done" without detail
- Missing links or progress status

---

## Writing Good Blockers

A good blocker answers:

| Question | Example |
|----------|---------|
| What is blocking you? | Missing Stripe sandbox keys |
| Why is it blocking you? | Cannot test payment flow |
| What do you need? | API keys or access |
| Who can help? | @Chris |
| What have you tried? | Using dev keys / reading docs |

### Good Blocker Example

```markdown
**Blocker:** Can't test Stripe payment flow in staging

**Details:**
- Need Stripe test API keys (test_pk & test_sk)
- Production keys cause CORS errors
- Blocking payment testing (3 days stalled)
- @chris has access to Stripe dashboard

**Tried:** tested dev keys, checked outdated docs
```

### Bad Blocker Examples

| Bad Example | Why It's Bad |
|-------------|--------------|
| Something is broken | No detail |
| API doesn't work | Which API? What error? |
| Need help | With what specifically? |
| Waiting on someone | Who? For what? When? |

---

## FAQ

### What if I finish early?

```markdown
Update (2 PM IST): Completed tasks early.

Picking up:
- Helping Raj with code review
- Exploring React Native performance tools
- Updating documentation
```

### What if I'm blocked and need urgent help?

1. Post blocker in standup
2. DM the person who can assist
3. @mention relevant member or channel
4. Escalate if urgent

> ⚠️ **Do NOT wait for next standup to ask for help**

### Do we still post during sprint planning / retros?

Yes — keep it short.

```markdown
Morning Standup - [Name]
- Sprint planning 9–11 AM
- After planning: start highest priority ticket
```

### What counts as a blocker?

| ✅ Counts as Blocker | ❌ Not a Blocker |
|---------------------|------------------|
| Waiting on code review | Don't know how to do something |
| Missing permissions | Running slow |
| Technical infrastructure down | Taking longer than expected |
| Dependency delayed | Confusion in requirement (ask in Notes) |

### Can I skip Friday standups if I posted Thursday evening?

**No** — Friday evening post helps US team plan Monday.

---

## Final Note

> Strong standups reflect **professionalism**, **ownership**, and **team clarity**.
>
> The goal is not reporting for the sake of reporting, but enabling **faster progress** and **better collaboration**.
