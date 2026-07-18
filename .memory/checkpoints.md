# Documentation Checkpoints

This file tracks major documentation milestones for diff tracking and updates.

---

## Checkpoint Format

```
## YYYY-MM-DD - Checkpoint Name

### Summary
Brief description of what was added/changed.

### Sections Added
- List of new sections

### Sections Modified
- List of modified sections with brief change notes

### Files Changed
- path/to/file.mdx
```

---

## 2025-01-07 - Initial Setup

### Summary
Created .memory folder with project context. Documentation structure not yet implemented.

### Files Created
- .memory/project-paths.md
- .memory/sdk-architecture.md
- .memory/api-endpoints.md
- .memory/vue-ecosystem.md
- .memory/checkpoints.md
- .memory/README.md

### Sections Added
- None yet (planning phase)

---

## 2025-01-07 - Full Documentation Structure

### Summary
Implemented complete 7-tab documentation structure with SDK, Vue, Trainer, Pad, API, and Recipes sections.

### Tabs Created
1. Home - Main landing page
2. SDK - TypeScript SDK documentation
3. Vue Components - vue2-components library
4. Vue Trainer - Physics game engine
5. Vue Pad - Diagram tool
6. API Reference - REST API endpoints
7. Recipes - Practical examples

### Files Created (48 total)

**SDK (19 files)**
- sdk/index.mdx
- sdk/core/index.mdx, models.mdx, collections.mdx, events.mdx, utilities.mdx
- sdk/pad/index.mdx, table-manager.mdx, balls.mdx, lines.mdx, saving.mdx
- sdk/game/index.mdx, physics.mdx, balls.mdx, shots.mdx, racking.mdx
- sdk/venues.mdx, players.mdx, tv.mdx, authentication.mdx, extras.mdx

**Vue (7 files)**
- vue/index.mdx
- vue/authentication.mdx, ui-elements.mdx, media.mdx, social.mdx, venue.mdx, branding.mdx

**Trainer (7 files)**
- trainer/index.mdx
- trainer/game-service.mdx, balls.mdx, shots.mdx, racking.mdx, camera.mdx, console.mdx

**Pad (5 files)**
- pad/index.mdx
- pad/table-manager.mdx, balls.mdx, lines.mdx, export.mdx

**API (10 files)**
- api/index.mdx
- api/authentication.mdx, users.mdx, venues.mdx, games.mdx, media.mdx, diagrams.mdx, comments.mdx, tv.mdx, services.mdx

**Recipes (11 files)**
- recipes/index.mdx
- recipes/sdk/add-balls.mdx, draw-lines.mdx, search-venues.mdx, save-diagrams.mdx
- recipes/vue/embed-trainer.mdx, show-feed.mdx, upload-media.mdx
- recipes/api/fetch-venues.mdx, record-shots.mdx, get-schedule.mdx

### Files Removed
- essentials/ folder (Mintlify boilerplate)
- ai-tools/ folder (Mintlify boilerplate)
- api-reference/ folder (replaced with api/)
- quickstart.mdx
- development.mdx

### Config Changed
- docs.json - Complete navigation restructure

---

## 2026-07-09 - Embed Flexibility & postMessage API

### Summary
Expanded the iframe embed surface in vue2-trainer and documented it. The embed
gained camera, diamond, cue, ball-skin, environment, and power-meter query
params; a deferred `start=click` poster gate; and a `postMessage` bridge that
lets a host page send commands into the table and listen for gameplay events.

### Sections Added
- trainer/embed-api.mdx - Full postMessage contract: message shapes, 17 commands, 10 relayed events, origin locking, worked host-page examples in plain JS and Vue 2.7

### Sections Modified
- trainer/embedding.mdx - Split the query-param table into Layout & rules /
  Equipment & presentation / Aim aids / Loading & host integration. Added
  `camera`, `diamond`, `cue`, `ballset`, `env`, `power`, `start`, `poster`,
  `origin`. Added a "What you can and cannot configure" coverage table, a camera
  preset table, diamond/cue/ballset id tables, a deferred-loading section, and
  the note that equipment is applied as a transient override so locked items
  render without being granted.

### Notes
- `chalk` and `tips` exist in the equipment catalog but have NO scene wiring
  (`System/Loadout/CategoryAdapter.ts` persists them to Vuex and nothing reads
  them). They are documented as explicitly NOT configurable rather than exposed
  as silent no-ops.
- Ball positions are not in the Vuex store (they hold `THREE.Vector3` on the
  ball manager), so `state.get` omits them rather than half-serving them.
- The published docs were already correct that `cloth`/`rail` take catalog ids,
  not hex colors; the trainer's own `Example/EmbedHost.vue` demo was passing hex
  and silently falling back to default felt. Fixed in the trainer repo.

### Files Changed
- trainer/embed-api.mdx (new)
- trainer/embedding.mdx
- docs.json

---

## Next Checkpoint: TBD

Future updates to track:
- New recipes added
- API endpoint additions
- Component documentation updates
- SDK version changes
