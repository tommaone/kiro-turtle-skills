# 🐢 kiro-turtle-skills

TMNT turtle squad for [Kiro](https://kiro.dev) — siege-specialist development style.

## The Squad

| Agent | Role |
|-------|------|
| turtleman 🐢 | Top-level siege specialist mode |
| splinter 🐀 | Ratman orchestrator — dispatches turtles |
| vernon 🐸 | Socratic requirement enforcer |
| leonardo 🔵 | Architect/planner |
| donatello 🟣 | Tech/tooling implementer |
| raphael 🔴 | Fast bug fixer |
| michelangelo 🟠 | Creative lateral thinker |
| shredder ⚔️ | Adversarial gatekeeper/reviewer |

## Prerequisites

Turtle bodies and evolution files must be installed at `~/.turtles/`:

```
~/.turtles/
  dojo/
    turtle-dojo.md
  turtles/
    splinter.md
    turtleman.md
    leonardo.md
    donatello.md
    raphael.md
    michelangelo.md
    shredder.md
    vernon.md
  evolution/
    splinter.md
    leonardo.md
    donatello.md
    raphael.md
    michelangelo.md
    shredder.md
    vernon.md
```

Clone [turtle-squad-core](https://github.com/tommaone/turtle-squad-core) and symlink or copy:

```bash
mkdir -p ~/.turtles
cp -r turtle-squad-core/turtles ~/.turtles/turtles
cp turtle-squad-core/turtle-dojo.md ~/.turtles/dojo/turtle-dojo.md
# evolution files are personal — initialise empty if first time
for t in splinter turtleman leonardo donatello raphael michelangelo shredder vernon; do
  touch ~/.turtles/evolution/$t.md
done
```

## Setup

### Steering files (IDE — always active)

Copy or symlink `.kiro/steering/` into your workspace:

```bash
cp -r kiro-turtle-skills/.kiro/steering .kiro/steering
```

Or for global activation across all workspaces:

```bash
cp kiro-turtle-skills/.kiro/steering/*.md ~/.kiro/steering/
```

### Custom agents (CLI)

Copy `.kiro/agents/` into your workspace or `~/.kiro/agents/` for global access:

```bash
cp -r kiro-turtle-skills/.kiro/agents ~/.kiro/agents
```

Invoke agents in the Kiro CLI:

```
kiro agent splinter "refactor the auth module"
```

## Architecture

```
User → Kiro IDE/CLI
  → .kiro/steering/turtleman.md   (always active, sets mode)
  → .kiro/steering/turtle-dojo.md (always active, shared rules)
  → .kiro/agents/<turtle>.json    (CLI agents, prompt → ~/.turtles/turtles/)
         ↕
~/.turtles/turtles/<turtle>.md    (canonical turtle bodies, from turtle-squad-core)
~/.turtles/evolution/<turtle>.md  (personal lesson logs, platform-agnostic)
~/.turtles/dojo/turtle-dojo.md    (shared rules, platform-agnostic)
```

## Platform variants

| Platform | Repo |
|----------|------|
| Claude Code | [claude-skills](https://github.com/tommaone/claude-skills) |
| GitHub Copilot | [copilot-turtle-skills](https://github.com/tommaone/copilot-turtle-skills) |
| opencode | [opencode-turtle-skills](https://github.com/tommaone/opencode-turtle-skills) |
| Kiro | this repo |

*Original author: [@tommaone](https://github.com/tommaone)*
