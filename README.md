# Project-Documentation-Maintenance-agent


[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](LICENSE)

> Rules and documentation templates that help AI agents — and human teams — keep a project's long-term documentation accurate, current, and well-structured over the whole life of the project.

[**中文版 README**](README.zh-CN.md)

## What this is

This repository is a **maintenance playbook + template kit** for anyone (especially AI coding agents) who maintains project documentation over the long run. It answers questions like:

- What should be checked before touching project documentation?
- Where does the truth live — current code, design records, git history, or old chat sessions?
- Which document owns which content (`README.md` vs `architecture.md` vs `decisions.md` vs `known-issues.md`)?
- When should a document be updated, and when should it deliberately be left alone?
- What counts as "done" after a maintenance session?

It contains two parts.

### 1. `AGENTS.md` — long-term maintenance rules

A concise rule set an agent reads before and during any documentation work:

| Section | Covers |
|---|---|
| Scope | What this rule file applies to, and what it does **not** authorize |
| Pre-maintenance checks | What to read and verify before editing docs |
| Sources of truth | Code/config > architecture & decision records > git history; old docs and chats are only leads |
| Documentation principles | Update only what changed; no duplicate authority; mark unverified content; keep secrets out |
| Document responsibilities | A table mapping each doc (`README`, `architecture`, `decisions`, `database`, `deployment`, `CHANGELOG`, `known-issues`) to its content |
| Long-term records | Decisions, changelog, and known issues conventions |
| Deletion & cleanup | Never delete/move/overwrite potentially unique material without explicit confirmation |
| Done criteria | How to tell a maintenance session is actually complete |

### 2. `docs/templates/` — document templates

A template set for the standard project documents, plus an index that tells the agent which template to open for which document:

| Template | For |
|---|---|
| `README.md.template` | Project intro, install, run and test entry points |
| `architecture.md.template` | Modules, data flow, boundaries, deployment topology |
| `decisions.md.template` | Significant technical & product decisions (DEC-001, …) |
| `database.md.template` | Data model, migrations, data safety |
| `deployment.md.template` | Environments, deployment steps, verification, rollback |
| `CHANGELOG.md.template` | User-visible version changes |
| `known-issues.md.template` | Current unresolved problems and risks |
| `session-index.md.template` | (optional) Traceability of AI sessions to decisions and docs |

## Directory layout

```
.
├── AGENTS.md               # Long-term maintenance rules
├── docs/
│   └── templates/          # Document writing templates
│       ├── INDEX.md        # Template index & usage rules
│       ├── README.md.template
│       ├── architecture.md.template
│       ├── decisions.md.template
│       ├── database.md.template
│       ├── deployment.md.template
│       ├── CHANGELOG.md.template
│       ├── known-issues.md.template
│       └── session-index.md.template
```

## Getting started

1. Copy `AGENTS.md` and the `docs/templates/` directory into your project root.
2. Tell your AI agent to read `AGENTS.md` before maintaining project documentation — it sets the boundaries and the "done" criteria.
3. When creating or updating a document, have the agent open `docs/templates/INDEX.md` first and read only the template for the document being touched.
4. Adapt the rules to your project; nothing in the templates is a claim about your project's actual facts until you fill it in.

## Notes

- This repo contains **rules and templates only** — there is no code to build, run, or test.
- Placeholders in templates are format examples, not project facts.
- Keep secrets, personal data, and unnecessary sensitive paths out of project documentation (see `AGENTS.md`).

## License

[GPL-3.0](LICENSE) © sunteki
