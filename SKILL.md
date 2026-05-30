---
name: context-compress
description: Proactively shrink the working context before it overflows — distill the conversation to a compact state note, drop stale file dumps, and prefer search over re-reading whole files. Invoke when a session is getting long, when the user says "compress", "compact", "running low on context", or before any operation that will dump a lot of output. On small machines, run this before the host's compaction kicks in.
---

# Context-compress — survive long sessions

Context is a budget, not an afterthought. When it runs out mid-task the host compacts it
*for* you — bluntly, and at the worst possible moment. This skill is the disciplined
alternative: **compress on your terms, before the cliff**, so nothing important gets
summarized away and small-RAM machines stay responsive.

The rule of thumb: **compress proactively at ~70–80% of the context budget**, not at 100%.

## What "compress" means here

It is *not* "forget everything". It's distilling the session down to the few things the
next stretch of work actually needs, and shedding the bulk that doesn't:

1. **Write a compact state note first.** Before dropping anything, capture the durable facts
   — current goal, decisions made, the next concrete step, key file paths/line numbers, and
   any gotchas discovered. (If the `handoff` skill is installed, reuse its checkpoint format
   so the note doubles as a resume point.)
2. **Shed stale bulk.** The biggest context hogs are full file dumps and long command
   outputs you've already acted on. Once a file's relevant fact is in the state note, you
   don't need its full text in context anymore.
3. **Re-fetch on demand, narrowly.** Prefer `grep`/search for the exact symbol or line over
   re-reading a whole file. Read only the slice you need, when you need it.

## Working habits that keep context small (apply continuously)

- **Search over slurp.** `grep`/glob for the symbol; read the matching slice, not the file.
- **One workload at a time.** Finish or park one thread before opening the next; don't hold
  three half-read subsystems in context simultaneously.
- **Summarize tool output.** After a long log or test run, keep the verdict (pass/fail +
  the one line that mattered), not the full scroll.
- **Offload heavy reads.** If the host supports sub-agents or background tasks, push
  large-file research out so the bulk never lands in the main context — keep only the answer.
- **Persist, don't carry.** Anything you'll need later but not right now goes to a file
  (state note, scratch doc), not held in the window.

## When to fire

- Proactively at ~70–80% context usage (estimate from session length if no meter).
- Before a step that will dump a lot: a big build log, a wide `git diff`, a large file read.
- When the user says compress / compact / "running low".
- On a small machine (low RAM), earlier rather than later — beat the host's auto-compaction.

## Steps

1. Write/refresh the compact **state note** (goal · decisions · next step · key paths · gotchas).
2. Identify the largest stale items in context (full file dumps, long outputs already acted on)
   and mentally release them — you can re-fetch narrowly if needed.
3. From here on, default to `grep`/slice reads instead of whole-file reads.
4. Tell the user, in one line, that you compressed and where the state note lives.

## Don't

- Don't compress away the **next action** or an unresolved decision — those are the whole point.
- Don't drop something you have no way to recover. If it isn't in a file or re-derivable,
  write it down before releasing it.
- Don't wait for 100%. Late compression means the host compacts for you and you lose control
  of what's kept.
