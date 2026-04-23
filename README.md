# The Kōzu Group

![Org Chart](images/org-chart.png)

## What's Inside

> This is an [Agent Company](https://agentcompanies.io) package from [Paperclip](https://paperclip.ing)

| Content | Count |
|---------|-------|
| Agents | 7 |
| Projects | 4 |
| Skills | 4 |
| Tasks | 1 |

### Agents

| Badge | Name | Role | Reports To |
|-------|------|------|------------|
| [E1] | Fermi | Executive Assistant (CEO-layer) | Michael Wong (human) |
| [E1.D1] | Kepler | Director, Personal Brand | Fermi |
| [E1.D1.A1] | Halley | Associate, michaelwong.life site ops | Kepler |
| [E1.D2] | Maxwell | Director, Kōzu Consulting | Fermi |
| [E1.D2.A1] | Faraday | Associate, consulting.kozugroup.com site ops | Maxwell |
| [E1.D3] | Planck | Director, Kōzu AI | Fermi |
| [E1.D3.A1] | Heisenberg | Associate, ai.kozugroup.com site ops | Planck |

Badge format: `[E#.D#.A#]` — E = Executive, D = Director, A = Associate, # = employee number at rank.

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

See [SKILLS_PLAN.md](./SKILLS_PLAN.md) for per-agent skill recommendations (including `frontend-design` "Impeccable" stack for site associates, content/editorial skills for directors, and research/AI skills for Planck).

### Subsidiaries

The Kōzu Group is an umbrella holding company. Each director manages one subsidiary:

| Subsidiary | Director | Focus | Naming Schema |
|---|---|---|---|
| **Personal Brand** (michaelwong.life) | Kepler | CEO's public-facing identity | — |
| **Kōzu Consulting** | Maxwell | Fast-sprint brand strategy for the AI era | — |
| **Kōzu AI** | Planck | LLM R&D, fine-tuning, datasets | Models: Planetary bodies / Scientists / Physics / Quantum Mechanics |
| **Kōzu Digital** *(future)* | *unfilled* | Full-stack engineering of SaaS products, platforms, and internal tools | Digital Products: Plant Genuses / Taxonomy (*Salix*, *Quercus*, *Acer*, *Pinus*) |
| **Kōzu Studio** *(future)* | *unfilled* | Visual identity, multimedia content production, creative direction | — |

## Getting Started

```bash
pnpm paperclipai company import this-github-url-or-folder
```

See [Paperclip](https://paperclip.ing) for more information.

---
Exported from [Paperclip](https://paperclip.ing) on 2026-04-23
