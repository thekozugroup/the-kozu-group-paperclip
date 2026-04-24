# Kōzu Group — Skills Installation Plan

Purpose: decide which Paperclip/Claude skills each of the 14 agents should have installed. Practical, per-agent, actionable. Skills listed here are for Claude Code agents primarily; Codex and Opencode agents should have the core Paperclip skills + the claude-compatible skills that survive adapter translation.

---

## 1. Core skills — install for everyone

Every agent gets these. They are the shared substrate.

| Skill | Why everyone needs it |
|---|---|
| `paperclipai/paperclip` | Core Paperclip coordination — delegation, status, inter-agent protocol |
| `paperclipai/para-memory-files` | PARA memory system — shared notebook of Projects/Areas/Resources/Archive |
| `anthropic-skills:context-management` | Graceful wrap-up when context fills |
| `anthropic-skills:consolidate-memory` | Periodic memory cleanup |
| `superpowers:using-superpowers` | Bootstraps the superpowers skill-finding protocol |
| `superpowers:verification-before-completion` | No "I'm done" without evidence |
| `context-mode:context-mode` | Keeps raw tool output out of context; massive token saver |

Optional global: `caveman:caveman-commit` for tighter commit messages.

---

## 2. Per-agent recommendations

### Executive layer

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1] Fermi** | Executive Assistant | `superpowers:brainstorming`, `superpowers:dispatching-parallel-agents`, `superpowers:writing-plans`, `paperclip-create-agent`, `anthropic-skills:docx/pptx/xlsx/pdf`, `anthropic-skills:schedule`, `schedule`, `loop` |
| **[E1.A1] Euler** | Operations (cross-arm) | `anthropic-skills:xlsx` (finance sheets), `anthropic-skills:docx` (legal templates), `anthropic-skills:schedule`, `anthropic-skills:pdf` (invoice/contract processing), `loop` for recurring ops checks |

### Directors

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1.D1] Kepler** | Director, Personal Brand | `superpowers:brainstorming`, `superpowers:writing-plans`, `anthropic-skills:design-md` (brand system), `anthropic-skills:lab-repo-publish`, `frontend-design:frontend-design` (review layer), `anthropic-skills:docx` |
| **[E1.D2] Maxwell** | Director, Kōzu Consulting | `superpowers:brainstorming`, `superpowers:writing-plans`, `anthropic-skills:pptx` (sprint decks), `anthropic-skills:docx` (SOWs), `anthropic-skills:design-md`, `schedule`, `loop` |
| **[E1.D3] Planck** | Director, Kōzu AI | `claude-api`, `anthropic-skills:skill-creator` (author Kōzu skills), `recursive-decomposition:recursive-decomposition`, `superpowers:writing-plans`, `anthropic-skills:pdf` (research papers), `superpowers:brainstorming` |

### Personal Brand team (Kepler's reports)

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1.D1.A1] Halley** | Site Ops (michaelwong.life) | `frontend-design:frontend-design` (Impeccable stack), `anthropic-skills:design-md`, `superpowers:test-driven-development`, `superpowers:systematic-debugging`, `superpowers:using-git-worktrees`, `superpowers:requesting-code-review` |
| **[E1.D1.A2] Copernicus** | Content & Editorial | `anthropic-skills:docx` (long-form drafts), `anthropic-skills:pdf` (reading source material), `superpowers:writing-plans` (editorial planning) — note: Opencode agent, skip Claude-only skills |
| **[E1.D1.A3] Hubble** | Design & Visual | `frontend-design:frontend-design`, `anthropic-skills:design-md` — note: Opencode agent; image-gen tools better handled at platform level |

### Kōzu Consulting team (Maxwell's reports)

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1.D2.A1] Faraday** | Site Ops (consulting.kozugroup.com) | `frontend-design:frontend-design`, `anthropic-skills:design-md`, `superpowers:test-driven-development`, `superpowers:systematic-debugging`, `superpowers:using-git-worktrees` |
| **[E1.D2.A2] Curie** | Research | `anthropic-skills:pdf` (reading industry reports), `anthropic-skills:docx` (research briefs), `anthropic-skills:xlsx` (competitor comparison matrices), `recursive-decomposition:recursive-decomposition`, `superpowers:brainstorming` |
| **[E1.D2.A3] Feynman** | Proposals & Communications | `anthropic-skills:docx` (SOWs), `anthropic-skills:pptx` (proposal decks), `anthropic-skills:pdf` (client handoffs), `superpowers:writing-plans`, `anthropic-skills:design-md` (proposal style guide) |

### Kōzu AI team (Planck's reports)

| Agent | Role | Skills beyond the core |
|---|---|---|
| **[E1.D3.A1] Heisenberg** | Site Ops (ai.kozugroup.com) | `frontend-design:frontend-design`, `anthropic-skills:design-md`, `superpowers:test-driven-development`, `superpowers:systematic-debugging`, `anthropic-skills:pdf` (model docs) |
| **[E1.D3.A2] Bohr** | Research & Experimentation | `claude-api` (model integrations), `recursive-decomposition:recursive-decomposition` (experiment design), `superpowers:test-driven-development`, `superpowers:systematic-debugging`, `anthropic-skills:xlsx` (results tables) |
| **[E1.D3.A3] Sagan** | Publications & Communications | `anthropic-skills:pdf` (paper drafting), `anthropic-skills:docx` (announcements), `anthropic-skills:design-md` (publication style), `superpowers:writing-plans`, `recursive-decomposition:recursive-decomposition` |

---

## 3. Adapter compatibility notes

### Claude Code agents (7)
Fermi, Kepler, Maxwell, Planck, Curie, Feynman, Sagan — **full skill support**. Install everything in their row.

### Codex Pro agents (4)
Halley, Faraday, Heisenberg, Bohr — Codex has its own skill surface. Install:
- Paperclip core skills (cross-adapter)
- PARA memory
- Codex-native equivalents of `superpowers:test-driven-development` / `systematic-debugging` where available
- Skip Claude-only skills (frontend-design/Impeccable may need direct Claude delegation for design review)

### Opencode agents (3)
Copernicus, Hubble, Euler — Opencode free tier has minimal skill surface. Install:
- Paperclip core skills
- PARA memory (if supported)
- Rely on strong system prompts (AGENTS.md + SOUL.md) rather than skills for steering

---

## 4. Design / UI skills — "Impeccable" stack

For anyone building or reviewing UI (Kepler, Maxwell, Planck, Halley, Faraday, Heisenberg, Hubble):

- **`frontend-design:frontend-design`** — explicitly avoids generic AI aesthetics, enforces distinctive production-grade UI
- **`anthropic-skills:design-md`** — codify brand tokens, typography, spacing, and voice guidelines as DESIGN.md files the associates consume

Each director should author a `DESIGN.md` for their arm. Associates consume it during implementation.

---

## 5. Research / AI skills — Planck's stack

Planck needs to author new Kōzu-specific skills over time:

- **`claude-api`** — build and tune model/API integrations
- **`anthropic-skills:skill-creator`** — author new skills when workflow demands them
- **`recursive-decomposition:recursive-decomposition`** — break down complex research questions

Bohr inherits `claude-api` and `recursive-decomposition` for experiment design.

---

## 6. Content / editorial skills

Copernicus, Feynman, Sagan are the three writing-heavy roles. They share:
- `anthropic-skills:docx` — long-form drafting
- `anthropic-skills:pdf` — reading source material, producing final artifacts
- `superpowers:writing-plans` — outline before drafting

Feynman additionally gets `anthropic-skills:pptx` for proposal decks.

---

## 7. Operations skills — Euler's stack

Euler handles cross-arm finance, legal, scheduling, vendors:

- `anthropic-skills:xlsx` — finance tracking, budget sheets
- `anthropic-skills:docx` — legal and contract templates
- `anthropic-skills:pdf` — invoice/contract processing
- `anthropic-skills:schedule` — cross-arm time coordination
- `loop` — recurring ops checks (weekly invoicing, monthly reports)

---

## 8. Gaps — skills to build for Kōzu

Six skills this team will need that don't exist off-the-shelf. Planck (with `skill-creator`) should author these:

1. **`kozu-brand-voice`** — codified tone guide for each arm, consumable by content agents
2. **`kozu-site-deploy`** — standard deploy workflow for the three Kōzu sites (guarded, verified, reversible)
3. **`kozu-client-sow`** — SOW and proposal template generator for consulting engagements
4. **`kozu-model-governance`** — model registry enforcement, naming-schema validation, release gates for Kōzu AI
5. **`kozu-sprint-delegation`** — Fermi's delegation pattern as a reusable skill (triage → assign → verify)
6. **`kozu-weekly-review`** — Friday synthesis: each director submits, Fermi consolidates, CEO reads

Order of build: 1 → 5 → 2 → 6 → 3 → 4. Voice first (everyone needs it), delegation pattern second (Fermi's core loop), then the role-specific ones.
