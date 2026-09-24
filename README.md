# brainframe-context-compress

Portable skill: shrink working context before the host blunt-compacts you.

Part of [brainframe-skills](https://github.com/CjPetersonIX/brainframe-skills). Not BrainFrame OS.


## Relation to BrainFrame OS (first glance)

1. **This repo is NOT the fleet OS.** Portable context-compress skill only.
2. **Fleet live truth** = [BrainframeOS README](https://github.com/CjPetersonIX/BrainframeOS/blob/main/README.md) + [`docs/ops/2026-09-23_t786u_FIRST_GLANCE_CURRENT_STATE.md`](https://github.com/CjPetersonIX/BrainframeOS/blob/main/docs/ops/2026-09-23_t786u_FIRST_GLANCE_CURRENT_STATE.md).
3. **CKPT format:** `<NODE-ID> CKPT <MASTER>.<LOCAL>` · current fleet epoch tip **5291 OPEN** (5292 VOID).
4. **MasterQ / map / rules:** MasterQ and fleet map live on BrainframeOS — not here.

---

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/CjPetersonIX/brainframe-context-compress/main/install.sh | bash
```

Pairs with [handoff](https://github.com/CjPetersonIX/brainframe-handoff) — the compact state note can be the CKPT body.

See [`SKILL.md`](SKILL.md).
