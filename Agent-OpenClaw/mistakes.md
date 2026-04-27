# Mistakes

## Pattern Log
- Date: 2026-04-13
  - Mistake: Important user facts were sometimes saved only in OpenClaw memory and not reflected in Obsidian
  - Cause: Memory capture flow was split between systems without a single source of truth
  - Prevention: When a fact should persist for future work, store it in the appropriate Obsidian layer as well
