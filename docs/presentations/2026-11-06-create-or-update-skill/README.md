# Presentation: the create-or-update-skill skill

Date: 2026-11-06 · Audience: every team writing agent skills in the monorepo · Language: each slide shows English on the left and French on the right.

Why the monorepo keeps its own skill-authoring skill instead of following one from the market: convergence, the Wakam context, collective improvement, a frontmatter whose every field is weighed by its use, pros and cons, and agent-agnostic invocation. The skill itself lives at `.agents/skills/create-or-update-skill/SKILL.md`.

## Slides

1. Cover

   ![Cover](01-cover.png)

2. The skill market is crowded

   ![The skill market is crowded](02-market.png)

3. What create-or-update-skill does

   ![What create-or-update-skill does](03-what.png)

4. Why our own: five reasons

   ![Why our own: five reasons](04-reasons.png)

5. Convergence: a mix, not a choice

   ![Convergence](05-convergence.png)

6. Fitted to Wakam

   ![Fitted to Wakam](06-context.png)

7. In the monorepo, we improve it together

   ![Collaboration](07-collab.png)

8. Mandatory fields: use, pros, cons

   ![Mandatory fields](08-frontmatter.png)

9. Optional fields: use, pros, cons

   ![Optional fields](09-optional.png)

10. Agent-agnostic

    ![Agent-agnostic](10-agnostic.png)

11. Invocable by any agent: three tiers

    ![Three tiers](11-invocable.png)

12. Takeaway

    ![Takeaway](12-close.png)

## Limits checked against the tooling

The skills linter is `Pricing/.agents/scripts/validate-skills.py`; the pre-commit hook runs it on Pricing skills (`pricing-skills-lint`) and on root skills (`monorepo-skills-lint`).

| Limit                                   | Where it is enforced                                                                                              |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `name` ≤ 64 chars, equal to its folder  | skills linter (E4)                                                                                                |
| `description` ≤ 1,024 chars             | skills linter (E5) and `Pricing/.agents/scripts/harness-budget.sh` (Pricing scope), from `description-limits.env` |
| `description` over 500 chars            | skills linter warning (W1), from `description-limits.env`                                                         |
| `description` aim ~300 chars            | convention only (`create-or-update-skill` checklist)                                                              |
| `category` one of seven families        | skills linter (E16); a root skill without one also fails `monorepo-skills-overview`                               |
| `company` equal to `wakam`              | skills linter (E17)                                                                                               |
| `effort` low, medium or high            | convention only (`create-or-update-skill` checklist)                                                              |
| Any field outside the allowed list      | skills linter (E12)                                                                                               |
| Body < 200 lines                        | convention only; `harness-budget.sh` warns past 500 lines or 5,000 tokens (Pricing scope)                         |
| Always-on harness ≤ 15,000 tokens/app   | `harness-budget.sh` pre-commit, root and Pricing nodes                                                            |
| ≤ 500 always-on tokens moved per commit | `harness-budget.sh` pre-commit, root and Pricing nodes                                                            |

The linter checks the value of `category` and `company` when present; the presence of `category`, `company` and `effort` is checked by the checklist and review.
