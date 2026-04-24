# The Kōzu Group

![Org Chart](images/org-chart.png)

## What's Inside

> This is an [Agent Company](https://agentcompanies.io) package from [Paperclip](https://paperclip.ing)

| Content | Count |
|---------|-------|
| Agents | 14 |
| Projects | 4 |
| Skills | 4 |
| Tasks | 1 |

### Agents

| Badge | Name | Role | Reports To | Adapter |
|-------|------|------|------------|---------|
| [E1] | Fermi | Executive Assistant (CEO-layer) | Michael Wong (human) | Claude |
| [E1.A1] | Euler | Operations (cross-arm) | Fermi | Opencode |
| [E1.D1] | Kepler | Director, Personal Brand | Fermi | Claude |
| [E1.D1.A1] | Halley | Associate, Site Ops (michaelwong.life) | Kepler | Codex |
| [E1.D1.A2] | Copernicus | Associate, Content & Editorial | Kepler | Opencode |
| [E1.D1.A3] | Hubble | Associate, Design & Visual | Kepler | Opencode |
| [E1.D2] | Maxwell | Director, Kōzu Consulting | Fermi | Claude |
| [E1.D2.A1] | Faraday | Associate, Site Ops (consulting.kozugroup.com) | Maxwell | Codex |
| [E1.D2.A2] | Curie | Associate, Research | Maxwell | Claude |
| [E1.D2.A3] | Feynman | Associate, Proposals & Communications | Maxwell | Claude |
| [E1.D3] | Planck | Director, Kōzu AI | Fermi | Claude |
| [E1.D3.A1] | Heisenberg | Associate, Site Ops (ai.kozugroup.com) | Planck | Codex |
| [E1.D3.A2] | Bohr | Associate, Research & Experimentation | Planck | Codex |
| [E1.D3.A3] | Sagan | Associate, Publications & Communications | Planck | Claude |

Badge format: `[E#.D#.A#]` — E = Executive, D = Director, A = Associate, # = employee number at rank. A# directly under E (skipping D) denotes cross-arm operations.

### Model / Adapter Split

| Adapter | Quota | Agents |
|---|---|---|
| **Claude Code** (Sonnet 4.6 / Max 20x) | Abundant | Fermi, Kepler, Maxwell, Planck, Curie, Feynman, Sagan |
| **Codex** (Pro) | Limited — reserved for code | Halley, Faraday, Heisenberg, Bohr |
| **Opencode** (free models) | Unlimited — high volume | Copernicus, Hubble, Euler |

### Projects

- **michaelwong.life Website** — CEO personal brand site
- **Kōzu AI Website** — Public site for the AI research arm
- **Kōzu Consulting Website** — Public site for the consultancy
- **Onboarding** — Agent spin-up and role calibration

### Skills

| Skill | Description | Source |
|-------|-------------|--------|
| paperclip-create-agent | Agent hiring skill | [github](https://github.com/paperclipai/paperclip/tree/master/skills/paperclip-create-agent) |
| paperclip-create-plugin | Plugin/extension creation | [github](https://github.com/paperclipai/paperclip/tree/master/skills/paperclip-create-plugin) |
| paperclip | Core Paperclip coordination | [github](https://github.com/paperclipai/paperclip/tree/master/skills/paperclip) |
| para-memory-files | PARA memory system | [github](https://github.com/paperclipai/paperclip/tree/master/skills/para-memory-files) |

See [SKILLS_PLAN.md](./SKILLS_PLAN.md) for per-agent skill recommendations (Impeccable stack for site associates, research/writing skills for knowledge work, ops skills for Euler).

### Subsidiaries

The Kōzu Group is an umbrella holding company. Each director manages one subsidiary:

| Subsidiary | Director | Team Size | Focus | Naming Schema |
|---|---|---|---|---|
| **Personal Brand** (michaelwong.life) | Kepler | 3 associates | CEO's public-facing identity | — |
| **Kōzu Consulting** | Maxwell | 3 associates | Fast-sprint brand strategy for the AI era | — |
| **Kōzu AI** | Planck | 3 associates | LLM R&D, fine-tuning, datasets | Models: Planetary bodies / Scientists / Physics / Quantum Mechanics |
| **Kōzu Digital** *(future)* | *unfilled* | — | Full-stack engineering of SaaS products, platforms, and internal tools | Digital Products: Plant Genuses / Taxonomy (*Salix*, *Quercus*, *Acer*, *Pinus*) |
| **Kōzu Studio** *(future)* | *unfilled* | — | Visual identity, multimedia content production, creative direction | — |

## Getting Started

```bash
pnpm paperclipai company import this-github-url-or-folder
```

Import URL: `https://github.com/thekozugroup/the-kozu-group-paperclip/tree/main`

See [Paperclip](https://paperclip.ing) for more information.

---
Exported from [Paperclip](https://paperclip.ing) on 2026-04-23
