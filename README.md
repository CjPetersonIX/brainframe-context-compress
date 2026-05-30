# brainframe-context-compress

```
██████╗ ██████╗  █████╗ ██╗███╗   ██╗███████╗██████╗  █████╗ ███╗   ███╗███████╗
██╔══██╗██╔══██╗██╔══██╗██║████╗  ██║██╔════╝██╔══██╗██╔══██╗████╗ ████║██╔════╝
██████╔╝██████╔╝███████║██║██╔██╗ ██║█████╗  ██████╔╝███████║██╔████╔██║█████╗
██╔══██╗██╔══██╗██╔══██║██║██║╚██╗██║██╔══╝  ██╔══██╗██╔══██║██║╚██╔╝██║██╔══╝
██████╔╝██║  ██║██║  ██║██║██║ ╚████║██║     ██║  ██║██║  ██║██║ ╚═╝ ██║███████╗
╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚══════╝
            S K I L L   ·   C O N T E X T - C O M P R E S S
```

A portable agent skill that keeps the working context lean — distill the session to a
compact state note, shed stale file dumps, and prefer search over re-reading whole files.
Compress **on your terms, before the cliff**, instead of letting the host compact bluntly
at 100%.

Built for small-RAM machines and long sessions, but useful anywhere.

Part of the [BRAINFRAME skills](https://github.com/The9thRealm/brainframe-skills) collection.

## Install (one line)

```bash
curl -fsSL https://raw.githubusercontent.com/The9thRealm/brainframe-context-compress/main/install.sh | bash
```

Installs to `~/.claude/skills/context-compress/` by default. Override with `SKILLS_DIR=...`.

## The idea

Context is a budget. When it overflows the host compacts it for you — bluntly, mid-task.
This skill compresses **proactively at ~70–80%**: write a compact state note (goal,
decisions, next step, key paths, gotchas), release the bulky stale items, and from there
prefer `grep`/slice reads over whole-file reads. Pairs naturally with the
[`handoff`](https://github.com/The9thRealm/brainframe-handoff) skill — the state note can
double as a resume checkpoint.

See [`SKILL.md`](SKILL.md) for the full discipline.

## Adopting in other CLIs

`SKILL.md` is plain Markdown — install as a Claude Code skill or paste its body into any
agent's rules/system prompt. Tool-agnostic.

## License

Public reference skill. Adopt freely.
