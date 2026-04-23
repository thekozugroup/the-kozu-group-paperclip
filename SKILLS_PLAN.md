# Kōzu Group — Skills Installation Plan

Purpose: decide which Paperclip/Claude skills each of the 7 agents should have installed. Practical, per-agent, actionable.

---

## 1. Core skills — install for everyone

Every agent gets these. They are the shared substrate.

| Skill | Why everyone needs it |
|---|---|
| `paperclipai/paperclip` | Core Paperclip coordination — delegation, status, inter-agent protocol |
| `paperclipai/para-memory-files` | PARA memory system — shared notebook of Projects/Areas/Resources/Archive |
| `anthropic-skills:context-management` | Graceful wrap-up when context fills; critical for long autonomous runs |
| `anthropic-skills:consolidate-memory` | Periodic reflective pass over memory files; keeps PARA clean |
| `superpowers:using-superpowers` | Bootstraps the superpowers skill-finding protocol |
| `superpowers:verification-before-completion` | No "I'm done" without evidence — applies to every role |
| `context-mode:context-mode` | Keeps raw tool output out of the context window; massive token saver |

Optional-but-recommended global: `caveman:caveman-commit` for tighter commit messages across all repos.

---

## 2. Per-agent recommendations

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1] Fermi** | Executive Assistant | `superpowers:brainstorming`, `superpowers:dispatching-parallel-agents`, `superpowers:writing-plans`, `paperclip-create-agent` (hiring), `anthropic-skills:docx`, `anthropic-skills:pptx`, `anthropic-skills:xlsx`, `anthropic-skills:pdf`, `anthropic-skills:schedule`, `schedule`, `loop` |
| **[E1.D1] Kepler** | Director, Personal Brand | `superpowers:brainstorming`, `superpowers:writing-plans`, `anthropic-skills:design-md` (brand system as DESIGN.md), `anthropic-skills:lab-repo-publish`, `anthropic-skills:docx`, `anthropic-skills:linkedin-job-search` (profile sync only) |
| **[E1.D1.A1] Halley** | Associate, michaelwong.life site | **`frontend-design:frontend-design`**, `anthropic-skills:design-md`, `anthropic-skills:lab-repo-publish`, `superpowers:test-driven-development`, `superpowers:executing-plans`, `superpowers:using-git-worktrees`, `superpowers:finishing-a-development-branch`, `superpowers:requesting-code-review` |
| **[E1.D2] Maxwell** | Director, Consulting | `superpowers:brainstorming`, `superpowers:writing-plans`, `superpowers:receiving-code-review`, `anthropic-skills:docx`, `anthropic-skills:pptx`, `anthropic-skills:xlsx` (client decks, SOWs, models) |
| **[E1.D2.A1] Faraday** | Associate, consulting.kozugroup.com | **`frontend-design:frontend-design`**, `anthropic-skills:design-md`, `superpowers:test-driven-development`, `superpowers:executing-plans`, `superpowers:using-git-worktrees`, `superpowers:systematic-debugging`, `superpowers:requesting-code-review` |
| **[E1.D3] Planck** | Director, Kōzu AI | `claude-api` (SDK/caching/migrations), `anthropic-skills:skill-creator`, `recursive-decomposition:recursive-decomposition`, `superpowers:brainstorming`, `superpowers:writing-plans`, `anthropic-skills:docx` (research writeups) |
| **[E1.D3.A1] Heisenberg** | Associate, ai.kozugroup.com | **`frontend-design:frontend-design`**, `anthropic-skills:design-md`, `claude-api` (demo code in docs), `superpowers:test-driven-development`, `superpowers:executing-plans`, `superpowers:using-git-worktrees`, `superpowers:requesting-code-review` |

---

## 3. Design / UI — "impeccable" stack for the three site associates

Halley, Faraday, Heisenberg all build sites. Install the same design stack for each so output quality is consistent across the three properties.

**Required on all three associates:**
- **`frontend-design:frontend-design`** — this is the "impeccable" skill. It explicitly targets distinctive, production-grade frontend and avoids generic AI aesthetics. Non-negotiable for anyone shipping UI.
- **`anthropic-skills:design-md`** — lets each site codify its brand as a `DESIGN.md` (Google Stitch format). Tokens flow into frontend-design invocations. Kepler/Maxwell/Planck author the DESIGN.md; associates consume it.
- **`anthropic-skills:lab-repo-publish`** — Halley specifically (michaelwong.life/labs), but safe on all three for public repo hygiene.

**Workflow per site:**
1. Director (Kepler/Maxwell/Planck) uses `design-md` to author/update `DESIGN.md` in the site repo.
2. Associate runs `frontend-design` against that DESIGN.md to produce components.
3. Associate verifies with `verification-before-completion` and a Claude Preview / Chrome MCP screenshot.

---

## 4. Content / editorial — for brand/content directors

Kepler and Maxwell both produce written artifacts (essays, positioning, SOWs, pitches).

- `anthropic-skills:docx` — long-form editorial and client documents
- `anthropic-skills:pptx` — Maxwell especially, for client decks
- `anthropic-skills:design-md` — encode editorial brand (typography, voice-adjacent visual system)
- `superpowers:brainstorming` — the required pre-creative step
- `superpowers:writing-plans` — turn brand/editorial briefs into executable plans for associates

Fermi should also carry `docx`/`pptx`/`xlsx`/`pdf` since the EA role is document-heavy.

---

## 5. Research / AI — for Planck

Planck owns model governance and ai.kozugroup.com content.

- **`claude-api`** — build, debug, and migrate Anthropic SDK code; covers caching, thinking, tool use, batch, files, citations, model migrations. Core skill for an AI director.
- **`anthropic-skills:skill-creator`** — Planck should be the one authoring/evaluating new internal skills (see Gaps below).
- **`recursive-decomposition:recursive-decomposition`** — for large-corpus research tasks (analyzing many papers or logs).
- **`anthropic-skills:docx`** — for research writeups and governance memos.

Heisenberg inherits `claude-api` so the code samples on ai.kozugroup.com actually compile and follow current best practices.

---

## 6. Gaps — skills to build

None of these exist in the current ecosystem; Planck (with `skill-creator`) should author them.

1. **`kozu-brand-voice`** — editorial voice rules for Kōzu Group writing (tone, forbidden phrases, house style). Used by Kepler, Maxwell, Fermi. Would plug into `design-md` and `docx` workflows.
2. **`kozu-site-deploy`** — unified deploy/preview/rollback procedure across the three marketing sites (michaelwong.life, consulting.kozugroup.com, ai.kozugroup.com). Halley/Faraday/Heisenberg all need this and today it lives in tribal knowledge.
3. **`kozu-client-sow`** — SOW/proposal template and guardrails for Maxwell (scoping, pricing bands, deliverable definitions).
4. **`kozu-model-governance`** — Planck's internal rubric for evaluating/approving models for client work; structured checklist, risk flags, pricing sanity check.
5. **`kozu-delegation`** — wraps `paperclip` with Kōzu-specific badge routing ([E1] → [E1.Dx] → [E1.Dx.Ay]) and the team's escalation norms. Used by Fermi and all three Directors.
6. **`kozu-weekly-review`** — structured Friday reflection that pulls from PARA memory and produces a CEO-facing digest. Fermi-owned.

---

## Installation quick-reference

Run per agent from their Paperclip workspace:

```
# Core (all agents)
paperclip install paperclipai/paperclip
paperclip install paperclipai/para-memory-files
paperclip install anthropic-skills:context-management
paperclip install anthropic-skills:consolidate-memory
paperclip install superpowers:using-superpowers
paperclip install superpowers:verification-before-completion
paperclip install context-mode:context-mode
```

Then layer the per-agent skills from section 2.
