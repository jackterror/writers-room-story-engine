# REPO-STANDARDS.md

Standards for every public skill repository under `github.com/jackterror`. Run this checklist before a repo goes public and again before any registry submission. Reference implementation: [`social-demand-signal-agent`](https://github.com/jackterror/social-demand-signal-agent).

---

## 1. Required files

Every skill repo ships with all of these at the root:

| File | Purpose |
|---|---|
| `SKILL.md` | Primary entrypoint. Orchestration layer – concise, points to reference files. |
| `README.md` | Public front door. Follows the README template below. |
| `LICENSE` | MIT, copyright Jack Dalrymple. No repo goes public without it. |
| `.gitignore` | Standard ignore set (below). |
| `CREATOR.md` | Creator attribution and package context. |
| `SOURCES.md` | Framework influences and synthesis notes. |
| `CHANGELOG.md` | Version history, newest first. |
| `PACKAGE-DESCRIPTION.md` | Registry / sharing framing. |
| `TEST-PROMPTS.md` | Test inputs for evaluation. |

Optional but encouraged: `examples/`, `reference/`, `MEGA-SKILL.md` (single-file fallback for runners that can't traverse folders).

## 2. Standard .gitignore

```
.DS_Store
__pycache__/
*.py[cod]
.env
runtime/
dist/
*.sqlite3
*.sqlite3-shm
*.sqlite3-wal
eval-workspace/
node_modules/
.idea/
.vscode/
```

Never put packaging hygiene notes in the README – the `.gitignore` is the packaging hygiene.

## 3. README template

Section order, top to bottom:

1. **H1 in Title Case** – e.g. `# Persuasion Audit Engine`, never the repo slug.
2. **One-line description** – formula: *"A modular AI-ready [X] that [does Y], grounded in [Z]."* Must match the GitHub repo description verbatim.
3. **What it does** – capabilities, scannable.
4. **Default behavior** – how it acts unprompted.
5. **Architecture / Package structure** – tree-format code block, not a bullet list:
   ```
   skill-name/
   ├── SKILL.md
   ├── reference/
   │   └── ...
   └── examples/
   ```
6. **Agent Skill installation** – always this exact block, slug swapped:

   ```markdown
   ## Agent Skill installation

   The repository root follows the [Agent Skills specification](https://agentskills.io/specification).

   Claude Code:

   ```bash
   ln -s /absolute/path/<repo-slug> ~/.claude/skills/<repo-slug>
   ```

   OpenAI Codex:

   ```bash
   ln -s /absolute/path/<repo-slug> ~/.codex/skills/<repo-slug>
   ```

   Then ask:

   ```text
   Use $<repo-slug> to <canonical first task>.
   ```
   ```

7. **Notes / philosophy** (optional).
8. **Creator and license** – always the closing section, always verbatim:

   ```markdown
   ## Creator and license

   Created by [Jack Dalrymple](https://jackdalrymple.com/), Founder of [Cap and Cut](https://capandcut.com/). See [CREATOR.md](CREATOR.md).

   Released under the MIT License. See [LICENSE](LICENSE).
   ```

## 4. Brand domains – non-negotiable

Two domains anchor every public repo, always together:

- `https://jackdalrymple.com/` – the person (non-www is canonical). Goes in the About panel website field and the Creator link.
- `https://capandcut.com/` – the studio. Goes in the Creator block and `CREATOR.md`.

Every repo must link both. The README closer and `CREATOR.md` are the enforcement points – if either domain is missing from either file, the repo fails the checklist. Non-www is the canonical form for new work; the www form in older files still resolves via 301 and may be aligned opportunistically.

## 5. GitHub repo settings (About panel)

- **Description**: the same one-liner as the README.
- **Website**: `https://jackdalrymple.com/`
- **Topics**: 8–10, always including the core four – `claude-skills`, `ai-agents`, `agent-skills`, `prompt-engineering` – plus domain-specific tags (e.g. `persuasion`, `copywriting`, `storytelling`, `social-listening`).
- **Social preview image**: upload one (Settings → Social preview), built per `CAPANDCUT-DESIGN.md` – Inter, #FFD600 yellow rule, AGENTIC SYSTEM eyebrow.

## 6. Style rules

- The studio is always written **Cap and Cut** – never "Cap & Cut". In caps: CAP AND CUT.
- Spaced en dashes ( – ) in prose, never em dashes.
- No internal build/housekeeping notes in public docs.
- CHANGELOG entries dated, newest first, semver-ish (`v1.1.0 – 2026-07-06`).
- Every claim in the README should be verifiable by opening the files it points to.

## 7. Pre-publish checklist

- [ ] LICENSE present (MIT, Jack Dalrymple)
- [ ] README follows template order, H1 in Title Case
- [ ] Creator and license block is the final README section
- [ ] Agent Skill installation block present with correct slug
- [ ] Tree-format package structure block
- [ ] `.gitignore` matches standard set
- [ ] Repo description = README one-liner
- [ ] Website set to jackdalrymple.com
- [ ] Both brand domains (jackdalrymple.com + capandcut.com) linked in README closer and CREATOR.md
- [ ] 8–10 topics applied
- [ ] Social preview uploaded
- [ ] No packaging/internal notes in public docs
