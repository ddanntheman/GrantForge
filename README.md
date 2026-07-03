<div align="center">

# GrantForge

**A full-lifecycle grant writing engine for Claude.**

From finding the right opportunity to a submission-ready application — discovery, eligibility triage, cited research, drafting, budgets, and a mock-scorer review, all in your organization's voice.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-blue.svg)](https://github.com/ddanntheman/GrantForge/releases)
[![Claude Plugin](https://img.shields.io/badge/Claude-Plugin-d97757.svg)](#installation)

</div>

---

## Overview

Grant writing is slow, repetitive, and unforgiving: the same organizational boilerplate rewritten for every funder, requirements scattered across 60-page NOFOs, budgets that must reconcile to the dollar, and reviewers who score against rubrics you never see.

GrantForge streamlines that entire process for the people doing the work — nonprofits, schools, universities, local governments, and companies pursuing federal, state, foundation, and corporate funding. Every draft passes through a built-in house style that removes AI writing patterns, and every application is graded by a mock reviewer before it goes out.

## Table of Contents

- [How It Works](#how-it-works)
- [The Workflow](#the-workflow)
- [Deliverables](#deliverables)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Components](#components)
- [Repository Layout](#repository-layout)
- [Responsible Use](#responsible-use)
- [Contributing](#contributing)
- [License](#license)

## How It Works

GrantForge learns your organization once, then reuses that knowledge on every application:

1. **Set up once.** A guided interview builds your organization's dossier — identity and registrations (EIN, UEI, SAM), mission and programs, capacity and leadership, financials, past awards, and impact metrics. Upload past applications and GrantForge extracts answers from them into a reusable answer library, and learns your writing voice from your samples.
2. **Work the pipeline.** Everything lives in a `.grantforge/` folder that persists across sessions. Each completed application makes the next one faster — winning language is harvested back into your answer library.

## The Workflow

Run the whole lifecycle with `/grantforge`, or invoke any stage directly by just asking:

| Stage | Say | What Happens |
|-------|-----|--------------|
| **Discover** | "find grants for us" | Searches Grants.gov, state portals, foundations, and corporate givers; returns a ranked, verified shortlist |
| **Intake** | "respond to this RFP" | Parses the announcement into a requirements matrix; eligibility check; go/no-go recommendation |
| **Research** | "research this grant" | Builds a cited evidence base (need data, intervention evidence) and funder intelligence (990s, giving history, priorities) |
| **Draft** | "draft the application" | Writes each section against the funder's verbatim prompts, within limits, in your voice |
| **Budget** | "build the budget" | Excel budget workbook plus a matching budget narrative, with verification math |
| **Review** | "are we ready to submit?" | Compliance audit, mock-scorer grading against the rubric, and a requirements-to-response compliance matrix |
| **Track** | "what's in our pipeline?" | Deadlines, statuses, win rate; harvests winning language back into your answer library |

## Deliverables

- **Word documents** formatted to the funder's rules
- **Portal-ready plain-text sections** with character counts
- **Excel budget workbooks** with a matching budget narrative
- **A compliance matrix** proving every requirement was addressed

## Installation

No API keys, accounts, or MCP servers required — research uses built-in web search.

### Claude Code (CLI)

```bash
claude plugin marketplace add ddanntheman/GrantForge
claude plugin install grantforge@grantforge-marketplace
```

Or try it for a single session without installing:

```bash
git clone https://github.com/ddanntheman/GrantForge.git
claude --plugin-dir ./GrantForge/plugins/grantforge
```

### Cowork / Claude Desktop App

Download [`dist/grantforge.plugin`](dist/grantforge.plugin), then open it in a Cowork chat and click **Save plugin** (or install via *Settings → Capabilities → Plugins*).

### Other Environments

`plugins/grantforge/` is a standard Claude plugin directory (`.claude-plugin/plugin.json`, `skills/`, `commands/`). Place it wherever your environment loads plugins from. The nine skills are self-contained markdown and work individually if the target only supports skills.

## Getting Started

Connect a folder where GrantForge should live (your grants folder), then say **"set up GrantForge"**. Setup takes one guided conversation; uploading past applications and reports speeds it up considerably. After that, start anywhere in the workflow — paste an RFP, ask for discovery, or run `/grantforge`.

## Components

| Component | Purpose |
|-----------|---------|
| `/grantforge` | Lifecycle orchestrator — runs the full workflow end to end |
| `grant-setup` | First-run interview; builds the org profile, answer library, and voice profile |
| `grant-discover` | Finds and ranks open funding opportunities matching your profile |
| `grant-intake` | Parses RFPs/NOFOs into a requirements matrix; go/no-go recommendation |
| `grant-research` | Cited evidence base and funder intelligence (990s, giving history) |
| `grant-draft` | Section-by-section drafting against the funder's verbatim prompts |
| `grant-budget` | Budget workbook and budget narrative with verification math |
| `grant-review` | Compliance audit, mock-scorer grading, compliance matrix |
| `grant-tracker` | Cross-session pipeline: deadlines, statuses, win rate |
| `house-style` | Shared writing standard; strips AI writing patterns from all prose |

## Repository Layout

```
.claude-plugin/marketplace.json   Claude plugin marketplace manifest
plugins/grantforge/               The GrantForge plugin (source of truth)
  .claude-plugin/plugin.json      Plugin manifest
  commands/grantforge.md          /grantforge lifecycle orchestrator
  skills/                         The nine skills
dist/grantforge.plugin            One-click installable for Cowork / Claude desktop
```

## Responsible Use

GrantForge drafts, researches, and checks — it does not submit. Every application still needs a human who knows the organization to verify facts, figures, and commitments before it goes to a funder. Treat the mock-scorer review as a rehearsal, not a guarantee.

## Contributing

Issues and pull requests are welcome. If GrantForge helped you win (or lose) a grant, feedback on what worked and what didn't is especially valuable — [file an issue](https://github.com/ddanntheman/GrantForge/issues) describing the funder type and where the output fell short.

## License

Released under the [MIT License](LICENSE).

Copyright © 2026 [Drew Danner](https://github.com/ddanntheman)
