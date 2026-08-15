# ChalkySticks Comprehensive Product Feature Catalog

Research snapshot: July 29, 2026.

This is a repository-backed inventory of the ChalkySticks ecosystem: customer-facing products, reusable engines, account/community systems, administrative tools, and internal delivery infrastructure. It is intentionally broader than a public marketing page. The point is to capture everything that has been built, identify the strongest product stories, and expose the raw material for a much more dynamic homepage.

## How to read this catalog

- An unlabelled bullet is evidenced in current source, SDK, API, tests, or current product documentation.
- **Foundation** means the underlying engine, model, endpoint, or component exists, although every client may not expose it yet.
- **Partial** means meaningful working code exists, but the end-to-end product surface is incomplete, unverified, hidden, or still has a known limitation.
- **Experimental** means a functioning prototype or specialized build exists, but it should not be marketed as a generally available product.
- **Historic** means the product was built and is still useful evidence of capability, but its current distribution status is unclear.
- **Planned** is used only for clearly documented roadmap work. Homepage concepts later in this document may be intentionally net-new.
- **★ Feed** marks a capability or event that could make a strong dynamic-homepage module.

This is a capabilities inventory, not a release certification. Before publishing a claim externally, confirm the relevant production flag, client route, entitlement, and deployment.

## Contents

- [Ecosystem at a glance](#ecosystem-at-a-glance)
- [Pad](#pad)
- [Trainer](#trainer)
- [Find](#find)
- [City Sessions](#city-sessions)
- [Watch](#watch)
- [Scan and Computer Vision](#scan-and-computer-vision)
- [Learn, Content, and the Shot Codex](#learn-content-and-the-shot-codex)
- [Accounts, Social, and Community](#accounts-social-and-community)
- [Challenges, Statistics, Achievements, and Rewards](#challenges-statistics-achievements-and-rewards)
- [Mobile, Quest, Desktop, and Physical Installations](#mobile-quest-desktop-and-physical-installations)
- [Physics and Shot Intelligence](#physics-and-shot-intelligence)
- [SDK, API, Embeds, and Integrations](#sdk-api-embeds-and-integrations)
- [CMS, Moderation, and Venue Data Operations](#cms-moderation-and-venue-data-operations)
- [Internal Engineering and Delivery Platform](#internal-engineering-and-delivery-platform)
- [Important Status Boundaries](#important-status-boundaries)
- [Dynamic Homepage and Activity Feed Opportunities](#dynamic-homepage-and-activity-feed-opportunities)
- [Research Basis](#research-basis)

## Ecosystem at a glance

| Product or platform | Primary job | Distinctive advantage |
| --- | --- | --- |
| Pad | Explain, design, save, and share a pool shot or drill | A precise 2D authoring surface that can become rules, media, an embed, or a playable Trainer drill |
| Trainer | Practice or play pool in a full 3D simulation | Custom deterministic physics, deep input support, authored games, AI, replay, multiplayer, XR, and arcade-ready presentation |
| Find | Discover where and with whom to play | A 20,000+ venue graph enriched by check-ins, community media, revisions, semantic search, and local play signals |
| City Sessions | Give every real venue its own repeatable digital challenge board | Deterministic venue-specific games, a house pro, permanent unlocks, Session Stars, and Local Legend competition |
| Watch | Find and watch cue-sports programming | Channels, live status, schedules, categories, ingest automation, resilient playback, and homepage-ready programming data |
| Scan | Turn pool-table imagery and video into structured table state | Ball, pocket, cushion, rail-diamond, camera, homography, tracking, and camera-cut intelligence |
| Learn | Teach rules, patterns, drills, and culture | Cited rulebook answers, voice input, facts, articles, tutorials, events, videos, diagrams, and a shot Codex |
| Community | Connect players, venues, media, matches, and activity | Profiles, check-ins, comments, reactions, tags, shares, presence, notifications, and location-aware discovery |
| Challenges and rewards | Turn activity into progression | Daily challenges, rich stats, period leaderboards, achievements, collectibles, wallet rewards, products, and loadouts |
| SDK and API | Make the ecosystem composable | Framework-independent packages, browser bundles, remote configuration, embeds, realtime services, and a broad v3 API |
| CMS and data operations | Keep content, users, venues, schedules, and commerce healthy | Permissioned workflows, venue deduplication/enrichment, moderation, remote feed composition, and automated scanning |

# Pad

Pad is both a consumer diagramming product and a reusable pool-diagram engine. It can author a simple shot picture, encode an entire drill, persist it to an account, render it as media, place it in an article, or hand it to Trainer as a playable experience.

## Table and layout authoring

- Six-foot table configuration.
- Seven-foot table configuration.
- Eight-foot table configuration.
- Nine-foot table configuration.
- Ten-foot pocketless carom/billiards table configuration.
- Table-specific view boxes, playable bounds, ball sizing, and grid spacing.
- Normalized table coordinates, so layouts survive different render sizes.
- Cue ball, numbered 1–15 balls, ghost balls, arrow markers, and invisible routing markers.
- Multiple visual ball sets through per-diagram customization.
- Cue-ball alias normalization for human-friendly and imported formats.
- Add, remove, move, and query individual balls.
- Select and move multiple balls together.
- Cycle through overlapping balls.
- Select nearby balls with a hold gesture.
- Rack a supplied ball layout programmatically.
- Shuffle existing ball positions.
- Clear the entire table.
- Import a complete saved table state.
- Export a complete table state.
- Export state together with rendered SVG markup.
- Track ball count, ball-set type, table type, completion state, and version.
- Programmatic fluent diagram builder for generated content.
- Programmatic table builder and manager APIs.
- Pure geometry and manager layer that can run without the Vue interface.
- Ball, line, shape, sticker, text, rail, and trajectory managers.
- Stable normalized shape, sticker, and text coordinates on import/export.
- Touch, pointer, keyboard, and gesture-driven manipulation.
- Mobile and tablet-compatible web surface.
- Read-only and interactive rendering modes.
- Zoom-left, zoom-right, and full-table views.
- Undo and redo event surface.
- Deletion and deselect-all event handling.
- Alignment-grid display.
- Snap-to-grid behavior.
- Configurable grid opacity.
- Configurable subgrid divisions.
- Configurable subgrid opacity.

## Shot explanation and annotation

- Straight coach lines between balls.
- Aim lines from the cue ball through a target.
- Object-ball and cue-ball trajectory visualization.
- Reflected/bounce paths from rails.
- Multiple-bounce trajectory options.
- Quadratic Bézier curves for massé or curved-shot notation.
- Solid, dashed, and dotted line styles.
- Per-line color.
- Editable line control points.
- Invisible line waypoints for bank and kick diagrams.
- Line angle in degrees or radians.
- Line length, midpoint, slope, and total-path measurement.
- Parallel-line detection.
- Line-intersection calculation.
- Angle-between-lines calculation.
- Rail-reflection angle calculation.
- Point, length, midpoint, and tangent calculations along curved lines.
- Geometric target zones using circles and rectangles.
- General geometric shapes.
- Text annotations.
- Sticker/image annotations.
- Table rails and boundary awareness.
- Pocket-to-adjacent-rail lookup for shot rules.
- Ghost-ball aiming notation.
- Arrow-ball directional notation.
- **Foundation / admin preview:** physics-verified shot paths can be generated by the shared Shot Planner rather than drawn speculatively.
- **Foundation / admin preview:** direct shots, banks, kicks, combinations, power, spin, cue travel, leaves, and safeties can all participate in route planning.
- **★ Feed:** a diagram is naturally suited to “What’s your out?”, shot-of-the-day, puzzle, drill, and community-remix cards.

## Appearance and presets

- Per-diagram theme.
- Per-part colors for felt, cushion, cushion stroke, rail, rail detail, rail trim, pockets, diamonds, and inner/outer spots.
- Named blue, green, grey, purple, red, and yellow themes in the public embed DSL.
- Arbitrary stored color records for richer in-product rendering.
- Per-diagram ball-set selection.
- Pocket-style selection.
- Pocket-reducer/tightness setting.
- Show or hide diamonds.
- Show or hide the foot spot.
- Show or hide the head spot.
- Show or hide the head string.
- Show or hide the rack outline.
- Show or hide the grid.
- Show or hide ChalkySticks branding.
- Premium-aware customization fields.
- Appearance settings travel with the saved diagram.
- Customization change events for live renderers and autosave.
- **Foundation:** presets can combine theme, ball set, table markings, pocket treatment, grid, and branding into reusable looks.

## Drill rules and DSL

- Compact rules shorthand stored on a diagram.
- Compile shorthand into a complete custom-rules configuration for Trainer.
- Guided drill-builder state converted into shorthand.
- Best-effort shorthand-to-guided-builder conversion.
- Human-readable English summaries from shorthand.
- Human-readable English summaries from compiled rule configurations.
- Localizable/overridable phrase dictionary.
- Sequential, global/free-order, and multi-step flow modes.
- Lowest-ball, highest-ball, any-ball, named-group, specific-ball, range, cycle, and phase flows.
- Solids, stripes, and arbitrary named ball groups.
- Repeating closer balls and defined respot positions.
- Called-pocket rules.
- Required banks, combinations, jumps, and kicks.
- Forbidden banks, caroms, combinations, jumps, and kicks.
- Required rail counts before or after contact.
- Allowed-rail restrictions.
- “Clean” contact and no-extra-ball constraints.
- Scratch and wrong-ball loss conditions.
- Win, lose, per-shot, and global requirements.
- Scope qualifiers that apply rules above, below, through, to, up to, or except selected balls.
- Rail-adjacency exemptions beside called pockets.
- Schema-v2 declarative rule events and pre-resolved flow steps.
- **★ Feed:** rules make homepage diagrams actionable—“play this drill” instead of merely viewing an image.

## Saving, ownership, and community

- Save diagram layout to the API.
- Authenticated account-owned saves.
- Server-minted share hash.
- Load a diagram by API ID or hash.
- **Partial:** the SDK model has `is_public` and the gated UI offers private/link/public, but the current manager save payload does not persist that selection.
- Title and long-form description.
- Ordering and optional group ID for multi-diagram collections.
- Layout fingerprint for change detection.
- Diagram versioning.
- Owner relationship.
- Comments relationship.
- Reactions relationship.
- Tags relationship.
- Automatic `user.diagrams` relationship in the SDK.
- Debounced autosave pattern.
- Local-draft persistence pattern.
- Current Mine/Public library and explicit Save/Remix flow.
- Remix/fork behavior creates a new diagram rather than overwriting the source.
- **Partial:** comment, reaction, and tag relationships exist, but Pad does not yet expose all of those interactions in its own interface.
- **★ Feed:** newly published diagrams, followed creators, set additions, and remixes are high-quality feed events; comments/reactions become additional signals when their Pad UI is added.

## Import, export, sharing, and embeds

- Rendered SVG output.
- Rendered PNG output.
- Raster quality control.
- Raster resolution scaling.
- SVG URL for a saved diagram.
- PNG URL for a saved diagram.
- WebP output in stateless read embeds.
- JPEG output in stateless read embeds.
- Raw JSON/table-state export.
- Raw SVG-markup capture.
- Cleaned, portable SVG export strips selection handles/editor state and bakes sticker assets, arrow colors, table colors, and font fallbacks.
- Shareable saved-diagram hashes.
- Stateless diagram URLs that require no account, database row, or API ID.
- Compact public URL DSL for balls, lines, zones, table size, theme, editability, and format.
- Tolerant URL parsing that keeps valid elements and reports malformed segments.
- Canonical URL serialization after edits.
- Stateless limits of 32 balls, 64 lines, and 32 target zones.
- Generated read mode that replaces the temporary live table with an SVG or raster rendering.
- Editable iframe playground mode with table pointer and keyboard behavior.
- Parent-page `postMessage` event containing the canonical DSL and parsed configuration.
- Embeddable in articles, lessons, documentation, and third-party sites.
- Read-only embeds do not need Pad toolbars or persistence.
- Editable embeds deliberately omit menus, save controls, and implicit persistence.
- Safe parent integration can validate both message origin and iframe source.
- **Foundation:** the image-to-diagram inference API can turn a photograph or video frame into Pad-compatible structured state.
- **Partial / gated:** Pad has a file-picker, drag/drop, clipboard-paste, and native-picker still-photo surface behind `kit_pad_scanner`; ordinary-user rollout remains unverified.
- Send/launch a diagram as a Trainer drill through the shared layout and rules formats.
- Trainer embeds turn a Pad-authored layout into a playable 3D drill.
- Clear distinction between a 2D Pad embed and a playable 3D Trainer embed.
- **★ Feed:** every feed diagram can offer view, edit, save, share, and “play in Trainer” actions without duplicating authoring logic.

## Developer integration

- Installable Vue 2 Pad component.
- Installable framework-independent `sdk-pad` package.
- ESM package and browser-oriented integration.
- Local Vue events plus a global `pad.*` event bus.
- Full-state enrichment on every change event.
- Public manager access for custom tools.
- Stateless parser usable outside the ChalkySticks website.
- Diagram collection and factory helpers pre-wired to the v3 API.
- Table configuration lookup by friendly key or stored data type.
- Import from a bare layout, full table state, or Diagram model.
- Explicit markup-provider hook for UI renderers.
- Package primitives can support white-label diagram tools and custom editors.

## Current Pad UI details worth calling out

- Three active visual ball sets: Cyclop Pool, ChalkySticks Pool, and Billiards Standard.
- Built-in 8-Ball, 9-Ball, and 10-Ball rack actions.
- Ball-tray drag and drop.
- Number-key ball retyping.
- Shift-marquee group selection.
- Tab-based selection cycling.
- Keyboard nudging.
- Constrained zoom, pinch zoom, and pan.
- Angle snapping as well as grid snapping.
- Fullscreen support where the platform allows it; deliberately hidden on iOS.
- Auto-fix for trajectory chains, ghost contact markers, and tangent markers without moving the real balls.
- Optional route-color inheritance from the starting ball.
- Optional drag-to-massé behavior.
- Saved appearance presets.
- Save, load, delete, and choose a default preset.
- Import/export one preset.
- Import/export all presets.
- Pocket reducers in none, ¼-inch, ½-inch, ¾-inch, and 1-inch increments.
- Straight and rounded/Heyball pocket styles.
- Projection display with thicker routes and pocket rings for visibility on a real table.
- Inline single-line and multiline text editing.
- Text wrapping, resize, and rotation handles.
- Rectangular callouts from the ordinary menu.
- Circle, ellipse, and arrow annotations through the manager/API surface.
- Scalable and rotatable stickers.
- Sticker library with letters, numbers/ball numbers, and cue-tip/English-position graphics.
- Device-aware help that shows gestures on touch devices and keyboard shortcuts on desktop.
- Interactive first-use tutorial that verifies real actions rather than advancing as a slideshow.
- Tutorial covers adding, selecting, moving, deleting, cycling overlapping balls, group selection, and line drawing.
- Shared intent registry drives bindings, contextual hints, mastery, and tutorial objectives.

## Pad library, sets, and remix workflow

- “Mine” and “Public” library tabs.
- Authentication gate for the personal library.
- Paginated diagram cards.
- Thumbnail, title, practice-set badge, date, and owner-only deletion.
- Unsaved-change warning before replacing the current diagram.
- Save new, update owned, delete owned, and remix/fork flows.
- Remix deliberately clears the original model ID so the result is a new diagram.
- Anonymous save/remix option as well as account ownership.
- Title up to 120 characters.
- Description up to 2,000 characters.
- Optional named practice set.
- Practice-set namespace and explicit author ordering.
- Previous/next set navigator.
- Current position and set-total indicator.
- Saved payload includes layout, visual customization, title, description, cleaned SVG, rules, table type, set, and ordering.
- Save panel destinations for Practice Rack, Play as Drill, Trainer embed, public/set page, SVG, and PNG.
- **Foundation:** owner, comments, reactions, and tags relationships exist, but Pad does not yet expose all of those social interactions in its own UI.
- **★ Feed:** public diagrams and practice sets already have the core browse/remix mechanics needed for a community puzzle or drill stream.

## Pad scan/photo import

- **Partial / gated:** a photo scanner is substantially implemented behind the `kit_pad_scanner` feature; its ordinary-user rollout cannot be proven from the Pad package alone.
- File picker.
- Drag-and-drop image input.
- Clipboard paste.
- Native iOS/Android image-picker integration.
- Camera-capture hint.
- Lazy-loaded inference package.
- Still-image processing without temporal video tracking.
- Camera-orientation correction.
- Homography into canonical table coordinates.
- Cue-ball and 1–15 recognition.
- Replace the current rack with editable detected balls.
- Scanning phases, progress, preview, and placement events.
- **Foundation:** an exported live-camera detector supports table confidence, progress, camera capture, and automatic exposure, but the default Pad scene does not mount it.

## Experimental Pad runout planner

- **Experimental / admin-only:** the current feature policy keeps the planner restricted while it matures.
- Default editor and Run Out toolbar modes; nominated single-shot planning starts by selecting an object ball and tapping a pocket.
- Any-order, 9-Ball, Solids, Stripes, and Rotation runout orders.
- Auto, Fast, and Thorough search quality.
- “Plan Run Out,” previous shot, next shot, current-shot label, and clear-plan controls.
- Select an object ball and pocket to plan a nominated shot.
- Compute a multi-shot sequence.
- Step diagram ball state forward and backward through the planned run.
- Leave-aware order handling.
- Physical-world coordinate conversion from a Pad snapshot.
- Only diagram routes verified by the simulation.
- Prewarmed worker pool scaling from two to six workers.
- Direct, power-variant, combination, bank, and kick candidate families.
- Advance all simulated balls to rest before planning the next leave.
- Draw paths with ordinary editable Pad primitives.
- Solid cue/object paths and dashed rollouts/bystander paths.
- Ghost contacts, arrow terminals, and invisible rail joints.
- Robustness, simplicity, cushion-count, leave, cue-travel, and safety scoring foundations.
- **Current limitation:** Pad exposes no Fargo/skill control; its planner integration inherits the expert-level default of 700.
- **Not public yet:** “Best Shot” remains commented/development-only.
- **Not public yet:** defensive safety planning exists in the service but is development-only and is not drawn by the ordinary UI.

# Trainer

Trainer is a complete 3D pool simulation and practice/game platform rather than a single “pool game.” It combines authored rules, deterministic physics, AI, multiplayer, replay, progression, extensive controls, device adaptation, and a presentation system that can run on the web, mobile, desktop, Quest, or a physical cabinet.

## Ways to play

- Freeplay/practice.
- Guided tutorial.
- Authored drills.
- Community drills surface.
- Local multiplayer.
- Computer/AI opponent mode.
- Online multiplayer for authenticated users.
- Direct diagram-to-drill launches from Pad.
- Venue-specific City Sessions launches.
- Match configuration independent of the table/rack presentation.
- Match presets can control undo, ball dragging, spectators, alternating breaks, shot clocks, and pacing.
- Races to a configurable number of games.
- Point races for score-based games.
- Configurable player names and opponent identities.
- Configurable table/rack/appearance payload per match.
- Full title screen, main menu, play selection, settings, profile, Codex, loadout, history, and multiplayer flows.
- Audience and entitlement gates hide preview/premium sections where appropriate.
- Keyboard, touch, pointer, gamepad, and XR inputs.
- Responsive desktop, mobile, and tablet play.
- Embeddable playable scenes/drills.
- Electron desktop build and release targets for macOS, Windows, and Linux.

## Standard pool disciplines

- 8-Ball, available to the default audience.
- 9-Ball, available to the default audience.
- 10-Ball, available to the default audience.
- Straight Pool / 14.1, implemented and audience-gated.
- One Pocket, implemented and audience-gated.
- Rotation, implemented but hidden from the current menu.
- One-ball rack/debug support only; there is no registered OneBall rules strategy or player-facing mode.
- Three-ball, implemented but hidden from the current menu.
- Full-table freeplay.
- Custom rack layouts.
- **Partial:** Straight Pool is implemented but a current task notes a turn-handling defect that should be fixed before a strong competitive claim.
- **Partial:** One Pocket and K-Ball contain referee-dependent edge cases that the simulation cannot fully enforce.

## Original and training-focused game modes

- 19 total rule strategies: 17 statically registered strategies plus dynamic Custom and Drill.
- Alternate Eight, implemented and audience-gated.
- Alternating, implemented but hidden from the current menu.
- Beat the Clock, implemented and audience-gated.
- Break Contest, implemented and audience-gated.
- Speed Run, available to authenticated players.
- Penalty Kicks, implemented and audience-gated.
- Snooker Mini, implemented and audience-gated.
- K-Ball, implemented and audience-gated.
- Custom rules.
- Diagram-backed drills.
- Tutorial stages that can rerack themselves from authored layouts.
- Beat the Clock run-clock tiers of 20, 30, 40, 50, and 60 seconds.
- Speed Run per-shot clock.
- Break Contest configurable fresh-rack series.
- Score-based presentation for Penalty Kicks and Snooker Mini.
- Point-race behavior for Straight Pool and K-Ball.
- Per-mode rack strategies.
- Per-mode rules strategies.
- Per-mode lower-third and urgent-clock presentation.
- Per-mode win/loss and foul logic.
- Per-mode ball-in-hand policies.
- Dynamic pocket sizing/tightness, including tighter Snooker Mini pockets.
- Pocket reducers implemented as a real geometry/physics setting, not just artwork.
- Speed Run continually reracks and tightens its shot clock from 10 to 5 seconds; a miss, foul, or timeout ends the run.
- Penalty Kicks uses five progressively harder spot shots, solo scoring, versus play, and sudden death.
- Beat the Clock asks the player to clear 15 balls under one continuous clock and gives versus players equivalent fresh racks.
- Break Contest scores repeated fresh-rack breaks in solo or alternating-versus play, with sudden death.
- Mini Snooker uses ten reds and five colors, red/color alternation, respots, clearance scoring, and tighter pockets.
- Straight Pool includes called shots, scoring, 14-ball reracks, foul deductions, and a three-foul penalty.
- One Pocket includes owned foot pockets, race to eight, neutral-ball respots, foul debt, and three-foul loss.
- K-Ball uses 15-ball rotation, a point per ball, continuous reracking, and foul deductions.
- **Planned:** Best Lag, target-zone bocce, safety drills, Wordle-style pool, trivia/correspondence pool, oversized-ball games, animated hazards, and other digital-only modes are documented ideas, not current modes.
- **★ Feed:** daily mode rotations, time-attack records, perfect breaks, and novel mini-game results are strong recurring cards.

## Custom games and authored rules

- Shared custom-rules schema with Pad.
- Ten authored official drills.
- Line-Up.
- L Drill.
- Circle.
- Spot Shots.
- Chalky Corners.
- I Drill.
- Mississippi 9-Ball.
- Center Table.
- Brainwash.
- Rotate 15.
- Community drill browser with public Pad previews, pagination, refresh, and rules-aware launching.
- Diagrams with rules launch as Drill; diagrams without rules launch as Freeplay.
- **Partial:** the community-drill section and several advanced official drills are audience-gated.
- Load arbitrary authored ball layouts.
- Invert imported layouts.
- Convert Pad shapes into playable 3D target zones.
- Sequential ball orders.
- Free-order clearance.
- Alternating groups.
- Repeating closers.
- Multi-phase drills.
- Required or forbidden banks, kicks, combinations, caroms, jumps, and rails.
- Called pockets and pocket restrictions.
- Scratch, wrong-ball, foul-limit, and rail-contact outcomes.
- Per-shot and whole-session requirements.
- Rule humanization for instructions and summaries.
- Target-zone subsystem for position and landing objectives.
- Game-mode registry and authoring guide.
- Rack-strategy registry.
- Rules-strategy registry.
- Automated parity checks for registered games and documentation.
- Venue-game planner that converts City Sessions objectives into playable matches.
- **Foundation:** a creator can progress from Pad layout → shorthand rules → Trainer game without building a new game engine.

## Physics and shot control

- ChalkySticks’ own deterministic billiards physics engine.
- Fixed 240 Hz deterministic simulation.
- Ball-to-ball collisions.
- Ball-to-rail collisions.
- Pocket capture and settling.
- Friction and restitution configuration.
- Draw and follow.
- Left/right English.
- Natural swerve.
- Optional squirt.
- Massé shots.
- Jump shots.
- Elevated-cue shooting.
- Airborne balls that can clear balls and rails.
- Cushion deflection.
- Cue collision and automatic jacking over obstructions.
- Cue-ball strike-point control.
- Aim direction and power control.
- Adjustable shot speed/game speed.
- Runtime physics profiles and constants.
- Table-specific boundaries and pocket geometry.
- Multiple collision strategies, including continuous collision detection.
- Precomputed trajectories separated from playback.
- Deterministic results suitable for multiplayer and replay.
- Worker and worker-pool shot solving.
- Recorded collision and outcome events.
- **Partial:** a task notes a desire for a larger maximum-English range; the existing spin system is real, but its tuning is still evolving.

## Aiming and shot intelligence

- Ghost-ball aiming.
- Aim lines.
- Cue-ball and object-ball trajectory lines.
- Rail continuation/deflection trajectories.
- First-person shot alignment.
- Overview/tabletop alignment.
- Auto-aim search for viable pockets.
- Shot-search result application to cue direction.
- Direct-pot search.
- Bank and kick geometry through the shared Shot Planner.
- Physics-verified candidate routes.
- Power and strike recommendations.
- Skill-aware shot selection.
- Leave-aware runout scoring.
- Cue-travel and position scoring.
- Safety scoring.
- Diagnostic reasons when no verified route exists.
- Auto-hide aim assistance while an opponent shoots.
- Configurable assistance allows beginner-friendly and advanced presentations.
- **★ Feed:** detected trick shots, best routes, missed alternatives, and “could you make this?” challenges are compelling personalized content.

## AI opponents

- Computer opponents with distinct skill levels.
- Fargo-style ratings mapped into reusable skill profiles.
- Five named presets: Beginner 325, Intermediate 425, Advanced 625, Pro 800, and synthetic Ghost 1000.
- 32 illustrated opponent identities in the current Trainer opponent catalog.
- Decision-making profiles rather than simple random misses.
- Shot planning constrained by opponent ability.
- Difficulty-aware accuracy, power, and route selection.
- Eight AI shot families: direct, combination, bank, kick, safety, jump, massé, and break.
- Skill thresholds control which shot families an opponent will attempt.
- Aim, power, English, elevation, search breadth, and thinking time vary with rating.
- Named opponents and presentation-ready identities.
- City Sessions house pros derived from a large authored roster.
- Venue-specific deterministic house-pro identity.
- House-pro ratings spanning beginner/local to elite/pro levels.
- AI can play standard matches and venue-specific objectives.
- Worker-pooled planning keeps expensive search off the main render loop.
- **★ Feed:** “beat this venue’s house pro,” upset wins, rematches, and rival progress can create recurring stories.

## Multiplayer

- One durable match automatically behaves live when both players are present and correspondence-style when either leaves; these are tempos of the same architecture.
- Durable turn commands for absent opponents.
- Matchmaking/Quick Match infrastructure.
- **Dormant:** the current Quick Match card is shelved/commented even though queue infrastructure remains.
- Open table listings.
- Host a public/private table.
- Direct challenge.
- Join by human-friendly room code.
- Match inbox.
- Match invites and invite-claim flow.
- Configurable game type and race.
- Stable player/match/room identities.
- Server-adjudicated results.
- Shot packets and resolved-result packets.
- Authoritative shot sequence numbers.
- Remote pre-shot baseline restoration.
- Arrival-race handling for realtime events and durable state.
- Remote ball-in-hand synchronization.
- Current-turn notifications.
- Match-completed notifications.
- Next-rack flow.
- Rematch flow.
- Online 8-Ball.
- Online 9-Ball.
- Online 10-Ball.
- Online race lengths of one, two, or three.
- Explicit forfeit.
- Refresh/reconnect synchronization architecture.
- Table dressing/loadout shared as match configuration.
- Video-bubble overlay component.
- Realtime game-event channel for cue motion, ball motion, shots, state, and match lifecycle.
- **Partial:** WebRTC transport, match chat, spectator/coaching UI, and stronger anti-cheat validation remain roadmap items even though some protocol/facade foundations exist.
- **Partial:** reconnect and view-transition behavior have active follow-up items and should be treated as an improving subsystem.
- **★ Feed:** “your turn,” invite, rematch, friend online, open table, upset, and completed-match cards are the highest-urgency signed-in feed modules.

## Replays and match history

- Persist completed games and shots.
- Account-aware game recorder.
- Offline recording queue.
- Ordered retry/synchronization.
- Account partitioning so queued records do not cross users.
- Dead-letter retry/discard controls in the recording architecture.
- Deterministic trajectory replay.
- Restore the exact pre-shot state for each chapter.
- Shot-by-shot chapter navigation.
- Play and pause.
- Playback-speed control.
- Intra-shot seeking.
- Semantic trajectory markers.
- Replay timeline.
- Cue/spin/power readout.
- Draggable and collapsible replay workbench.
- Multi-shot selection.
- 0.25×, 0.5×, 1×, and 2× playback options.
- Automatic replay camera sequences.
- Editable camera-sequence model.
- Camera transition planning.
- Manual camera action immediately yields automatic direction.
- Match history UI.
- In-memory or persisted-shot playback.
- Replay-ready event stream.
- Stitch selected replay shots into a browser-rendered video.
- 30 or 60 frames per second.
- Screen-size, 720p, or 1080p capture.
- Discard or export the captured result.
- **Partial:** this is a strong replay workbench and capture pipeline, not yet a nonlinear trim/reorder editor or persistable editing project.
- **Foundation:** cool-shot detection and semantic markers can support generated highlight reels.
- **Planned:** automatically suggesting a shareable post-match highlight package is documented but not yet a finished social workflow.
- **★ Feed:** personal bests, close matches, unusual shots, and short generated replay highlights are among the richest media cards available to ChalkySticks.

## Cameras and presentation

- First-person follow camera.
- Overview camera.
- Overhead camera.
- Break and reverse-break views.
- Half-table view.
- Side view.
- Three-quarter view.
- End-table view.
- Close-up view.
- Six pocket-specific views.
- Free camera.
- Free-flight/free-look control.
- Interactive orbit camera.
- Cinematic orbit camera.
- Ball-tracking camera.
- Preset camera positions.
- Four persistent custom camera slots.
- Field-of-view and dolly controls.
- Post-shot camera director.
- Replay-specific camera direction.
- Smooth camera transitions.
- Standing and crouched aiming stances.
- Camera response to an automatically elevated cue.
- Cue fade near the first-person camera.
- Projection mode.
- Flat/orthographic presentation mode.
- Scene-mode overlay.
- Lower thirds for game, players, score, turn, and clocks.
- Mode-specific urgent-clock treatment.
- Banners, awards, accolades, summaries, highlights, and progression takeovers.
- Post-game breakdown and highlight tabs.
- Queueable presentation screens and reveals.
- Trick-feed overlay.
- Game outcome takeover.
- Screenshot-aware rendering path.
- Fullscreen support.
- **Partial / internal:** authenticated, opt-in admin remote control for installations and cabinets; public production rollout remains blocked on security/integration work.
- **Experimental:** physical-table projection and automatic homography alignment have meaningful foundations, but full AR/projector calibration remains roadmap work.

## Visual customization and loadouts

- 53 equipment catalog items across nine categories.
- Nine named table looks plus Custom in the current public strategy enum.
- Eight named environments plus Custom in the current public strategy enum.
- Environment-specific lighting, skybox, ground, carpet, and HDR reflections.
- Runtime environment switching and cycling.
- Custom lighting/environment configuration.
- Multiple American ball sets.
- Snooker ball set foundation.
- Eight Speed Run color variants.
- Sixteen cloth items.
- Six rail items.
- Three diamond items.
- Four cue items.
- Six cue-tip items.
- Five chalk items.
- Cloth, rail, and diamond material tinting.
- Cue texture/appearance routing.
- Ball-set runtime loading.
- Account/catalog-backed equipment access.
- Equipped-item persistence.
- Free, owned, locked, rarity, and entitlement-aware catalog states.
- Pocket tightness as a gameplay loadout/configuration dimension.
- Standard pocket profile.
- Tight 4.75-inch pocket profile.
- Pro 4-inch pocket profile.
- Master 3.5-inch pocket profile.
- Custom pocket widths down to cue-ball diameter.
- Pocket changes alter the visible rails and actual collision boundary together.
- Full-table themes for brands, venues, broadcasts, and events.
- Automatic fallback to an unlocked wired item.
- **Partial:** the Loadout architecture and catalogs are substantial, while some earn paths, creator tools, and scene wiring for placeholder items remain incomplete.
- **Partial:** chalk and cue-tip selections are preference/cosmetic state rather than visible 3D equipment, and no equipment item changes physics today.
- **★ Feed:** newly earned cosmetics, rare unlocks, venue themes, and limited-time loadouts are natural reward cards.

## Graphics, performance, and device adaptation

- Automatic render-quality profile.
- Manually selectable Lowest, Low, Medium, High, and Very High profiles.
- Device-aware rendering policy.
- Mobile performance tuning.
- Low-power coordinator.
- Texture-size and environment-map controls.
- Shadow, antialiasing, device-pixel-ratio, lighting, and post-processing profiles.
- Deferred expensive environment-map setup.
- Reversible XR performance profile.
- Frame-rate and performance instrumentation.
- Mobile performance benchmark scenarios.
- Long-running memory/leak-soak scenarios.
- Profile comparison tools.
- Debug panel.
- FPS counter.
- Runtime physics and render diagnostics.
- Browser/WebGL compatibility handling.
- Orientation fixes for phones and tablets.
- Reduced effects where mobile GPUs need it.
- Quest-specific rendering optimization.

## Controls and accessibility of play

- Mouse/pointer aiming and shooting.
- Touch aiming and shooting.
- Keyboard shortcuts.
- Analog gamepad sticks.
- Gamepad button intent mapping.
- Automatic gamepad connection/disconnection detection.
- Stable assignment of controllers to player seats.
- Per-seat input authorization.
- Gamepad deadzone and sensitivity.
- Gamepad haptics for ball-ball, ball-rail, and pocket collisions.
- Up to two assigned player gamepad seats, with stable claiming and haptics.
- Gamepad fine-aim controls.
- XR controllers.
- Input mappings normalized across keyboard, touch, gamepad, and XR.
- Continuous aim, power, spin, camera, and stance control.
- Native browser gamepad support.
- Cabinet-friendly control abstraction.
- **Experimental:** a trackball/no-button tabletop cabinet configuration has been built and performance-tested on Android hardware.

## Audio

- Music, ambience, UI, cue, collision, pocket, and other SFX categories.
- Independent master and category volume.
- Independent sound-type enables.
- Muffle bus.
- Music ducking.
- Sound cooldowns.
- Velocity-sensitive volume.
- Randomized sound variations.
- Runtime event-bus audio control.
- Prebuilt mute/settings controls.
- Persistable preferences.
- Environment and match ambience.
- Post-game and reward reveal sounds.

## XR, Quest, desktop, and installation modes

- WebXR immersive-VR support detection.
- A-Frame immersive entry/exit lifecycle.
- Quest-compatible VR play.
- Quest controller routing.
- Floating XR controls.
- XR camera mode.
- Automatic Quest PWA VR-entry attempt with manual fallback.
- Quest-specific table/asset choices.
- Reversible performance changes on leaving VR.
- Standalone Quest app shell that boots directly to freeplay.
- Electron Trainer shell.
- macOS, Windows, and Linux Electron build targets.
- Auto-update dependency and release scripts.
- Remote-control capability for managed installations.
- Kiosk/cabinet suitability.
- Current specialized Electron cabinet mode; custom cabinet hardware and projection deployments remain experimental installations.

## Stats, Codex, progression, and profile

- Lifetime/career gameplay statistics for CPU and Online play.
- Challenges use a separate rollup.
- Practice and local two-player games remain archived/replayable but are excluded from career totals.
- Match history.
- Profile statistics screen.
- Profile Overview with account level, exact XP progress, wallet/streak, and separate Online/CPU records.
- Account screen.
- Subscription screen.
- Best-trick tracking.
- Trick detection and naming.
- Trick scoring.
- Trick feed.
- Shot Codex built from 92 authored shot definitions across 18 families.
- Shot discovery date.
- Times a shot has been made.
- Best points and best tier per Codex shot.
- Search/match aliases for equivalent shot names.
- Banks up through five rails.
- Kicks up through “Holy Kick” depth.
- Combination-depth recognition.
- Trainer medal rules.
- Account accomplishment catalog integration.
- Goals with live progress.
- Collectibles.
- Rarity filters.
- Difficulty filters.
- Local/profile-partitioned unlocks.
- Server-backed account awards.
- Post-game progression presentation.
- Server-authoritative XP receipts.
- Lifetime account levels from 1–999.
- Exact XP-to-next-level progress.
- Separate competitive Online and private CPU records.
- Multi-level-crossing ceremony.
- Equipment-unlock ceremony.
- Post-game XP and component breakdown.
- Bounded recovery while match adjudication is pending.
- **Partial:** second-device entitlement/loadout stabilization and offline-to-online recap recovery remain active work.
- **★ Feed:** Codex discoveries, rare tricks, streaks, personal bests, goals nearing completion, and post-game awards provide abundant personalized stories.

## Embedding and developer surface

- Installable Vue 2 Trainer package.
- Embeddable game scene.
- Playable drill embed distinct from Pad’s 2D embed.
- Props for environment, appearance, match, rules, rack, and controls.
- Programmatic ball racking and custom layouts.
- Programmatic camera control.
- Programmatic shot execution.
- Programmatic player management.
- Runtime game-speed and physics control.
- Rich public event catalog.
- Control, state, collision, shot, visual, match, multiplayer, camera, replay, gamepad, and XR events.
- Console/debug API.
- Public system facades with explicit lifecycle.
- White-label-ready engine architecture, although product policy for formal white-label distribution is still undecided.

# Find

Find is ChalkySticks’ real-world pool discovery layer: a worldwide venue directory, map, semantic search engine, contribution system, check-in surface, and bridge from physical locations into City Sessions and Trainer.

## Venue network and discovery

- More than 20,000 marketed pool-playing venues worldwide.
- Natural-language venue search.
- Geolocation-driven nearby results.
- Authenticated advanced semantic search.
- Coordinate-radius search.
- Distance sorting.
- Fuzzy venue-name matching.
- Fuzzy address matching.
- Semantic similarity over indexed venue imagery.
- Search by visual concepts such as cloth color, table brand, room style, neighborhood, or atmosphere.
- Voice/audio search input.
- Rough-location discovery.
- Precise current-location discovery with permission flow.
- City search.
- Neighborhood search.
- Venue-name search.
- Infinite/paginated result loading.
- Nearby-only result mode.
- Favorites-only result mode for authenticated users.
- Nearby, Favorites, and Map tabs.
- Random venue endpoint for discovery.
- External-place lookup by Google Place ID.
- Duplicate/similar-venue detection foundations.
- **★ Feed:** “new near you,” “open now,” “worth the trip,” “matches your vibe,” and “you have not played here yet” can all be personalized from existing venue/search data.

## Interactive map and location pages

- Searchable venue markers.
- Marker preview cards.
- Result-density-aware map zoom.
- Follow current location.
- Restore current location after browsing.
- URL-backed/shareable map position.
- Deep-linked maps.
- Up to 64 mapped results in the current map experience.
- SEO-friendly named city pages.
- Paginated venue grids per location.
- Large shortcut catalog spanning major pool cities worldwide.
- Venue, city, location, content, and static sitemaps.
- Structured venue data/JSON-LD for search engines.
- Semantic and geographic discovery complement one another rather than competing.

## Venue detail pages

- Venue name.
- Street address.
- Description.
- Website.
- Phone/call action.
- Directions action.
- Open/closed status.
- Weekly hours.
- Map context.
- Nearby venues.
- Google rating.
- Photo gallery.
- Tagged community media.
- Recent comments.
- Public venue conversation.
- Recent check-ins.
- Community revision history.
- Revision submission.
- Favorite/Love reaction.
- Current City Sessions board.
- **★ Feed:** favorite-venue hours changes, new photos, reopened status, new equipment, fresh comments, and new Session boards are naturally meaningful updates.

## Structured venue attributes

- Cash-only status.
- Food availability.
- Free-table availability.
- Gambling.
- Smoking.
- Live music.
- League availability.
- Tournament availability.
- Seven-foot tables.
- Eight-foot tables.
- Nine-foot tables.
- Snooker.
- Carom/billiards.
- Ping pong.
- Darts.
- Foosball.
- Shuffleboard.
- Skee-ball.
- Contact details and location geometry.
- Hours and operational status.
- Imported and community-maintained metadata.
- **Foundation:** these attributes can power highly specific searches and homepage recommendations, such as “9-foot tables open late within five miles.”

## Check-ins and presence

- Check in to a venue.
- Check-in frequency guard on the API.
- Public venue check-in history.
- Latest check-in per user.
- Global/searchable check-in feed.
- Current-presence relationship based on a user’s latest check-in within 12 hours.
- Recent check-ins on venue pages.
- Check-in totals on profiles.
- Unique-venue totals on profiles.
- Location-aware accomplishments.
- CSX reward for an eligible venue check-in.
- City Sessions access based on physical presence or prior check-in.
- **★ Feed:** friends checking in, familiar faces at a favorite room, a busy nearby venue, first-time visits, streaks, and local-champion activity are among the best real-world feed signals.

## Photos, video, and community contributions

- Venue image upload.
- Venue video upload.
- Direct/presigned media upload flow.
- Import media from a URL.
- Venue-photo ordering.
- Tagged venue-photo wall.
- User attribution on community photos.
- Paginated venue gallery.
- Photo/video detail view.
- Love reactions on media.
- Comments on media.
- “Take a photo” contribution action.
- User and venue tags.
- Tag acceptance/rejection sharing flow.
- User-submitted venue revisions.
- Revision notes.
- Multiple revision images.
- Pending moderation state.
- Create a new venue shell from a revision/submission.
- Anonymous contribution fallback.
- Google Place lookup/import in the submission flow.
- Submit amenities, games, equipment, notes, photo, and review-style comments.
- The direct venue-create endpoint assigns an owner who may update the listing; the public revision/submission flow does not currently assign ownership.
- **★ Feed:** new nearby photos, missing-photo missions, revision approvals, before/after listing improvements, and high-value contributor activity turn directory maintenance into community content.

## Find-adjacent player discovery

- Nearby-player list.
- Active-player list.
- New-user discovery.
- Player hometown.
- Preferred games.
- Skill/talent level.
- Favorite venues.
- Recent check-ins.
- Location beacons for “looking for a game.”
- Proximity search over short-lived beacons.
- “Friendly Faces” venue context.
- **Partial:** a complete friend/follow graph is not yet shipped, so “friends here now” requires that missing relationship layer or an explicit contacts/co-player alternative.
- **★ Feed:** nearby players looking for a game is an unusually actionable, time-sensitive homepage card.

## Find data quality and external enrichment

- Google Places import and enrichment.
- Google photo retrieval.
- Place suggestions.
- Geocoding.
- IP-based location fallback.
- Yelp/Google search and test utilities.
- Missing-data enrichment jobs.
- Similar-venue scoring.
- Duplicate clusters.
- Duplicate-media cleanup.
- Slug generation.
- Permanently-closed marking.
- Site-preview extraction.
- AI-generated venue-image tooling.
- Image-quality evaluation.
- Revision summarization.
- Semantic text and image embeddings.
- Gemini-backed media embedding/search foundation.
- Candidate discovery pipeline.
- **★ Feed:** “recently enriched or community-confirmed,” “newly reopened,” “listing substantially improved,” and “help confirm this place” give data operations a useful public face.

## Find boundaries

- No explicit business-verification/claim-an-existing-venue workflow was found.
- Owner-based update authorization exists for directly created venues, but public submissions do not establish ownership and should not be described as venue claiming.
- No first-party star-review model was found; comments, revisions, media, favorites, and imported Google ratings are the current equivalents.
- No first-party venue-event calendar was found; league/tournament availability is structured metadata and event flyers are content.
- Semantic search quality depends on having representative indexed venue imagery.

# City Sessions

City Sessions turns a static place listing into a persistent local game. Every venue receives a deterministic challenge board, a house pro, stars, a venue leaderboard, and two ways to unlock play: prove you are physically there or purchase permanent remote access with earned currency.

## Venue-specific board

- Deterministic challenge board generated from venue identity and generator version.
- Venue-name corrections do not unexpectedly rotate the board.
- Stable named random-number streams for reproducible content.
- Three board tiers.
- Novice, Local, Road, Shortstop, and Pro difficulty language in the generator.
- 3-ball, 5-ball, and 9-ball par-style challenges.
- Table challenges.
- Signature challenges.
- House-pro challenge.
- 8-Ball, 9-Ball, 10-Ball, Straight Pool, and Speed Rack style inputs.
- Trainer deep links and fullscreen launch.
- Board preview before play.
- Lock overlay and access explanation.
- Per-venue star display.
- **★ Feed:** “today at your favorite room,” “one star left,” and “a nearby board you have never tried” create a repeatable local-game loop.

## Signature games

- Beat the Clock.
- Break Contest.
- Speed Run.
- Bank It, implemented as a spot-shot drill.
- Existing Trainer mini-games reused as authored venue challenges.
- Venue objectives converted into full Trainer match configurations.
- Difficulty and target values derived deterministically.
- **Foundation:** the board generator can grow as Trainer gains more authored games without replacing the venue product.

## House pros

- Roughly 159 authored house-pro names.
- 31 character-art assets.
- Deterministic house-pro assignment per venue.
- Fargo-style ratings.
- Ratings map into reusable Trainer skill profiles.
- Ratings span roughly 300–875.
- AI DecisionMaker plays the challenge at the assigned ability.
- Presentation-ready opponent name, art, and skill identity.
- **★ Feed:** house-pro win streaks, upset wins, venue rivalries, and “this week’s rematch” can make AI feel socially persistent.

## Access and unlocks

- Anonymous users are prompted to authenticate.
- Play access after the user has ever checked in at the venue.
- Physical free-unlock flow.
- Precise-location requirement.
- Under-0.1-mile client proximity gate in the current flow.
- Live camera/table scan verifies a pool table.
- Successful table scan can trigger the check-in.
- Permanent venue unlock for 1,000 CSX.
- Ordinary wallet product SKU `unlock.venue.{id}`.
- Server-authoritative product price.
- Append-only wallet transaction.
- Durable `venue_unlock` entitlement.
- Lazy product/catalog creation at purchase time rather than pre-creating 20,000+ products.
- Published/available venue validation.
- **★ Feed:** earnable remote unlocks create a clean bridge between community contributions, wallet rewards, physical visits, and digital play.

## Session Stars and Local Legend

- Star conditions tied to completed venue playables.
- Venue-scoped user statistics.
- Per-user board progress.
- Session Stars.
- Venue leaderboard.
- Local Legend competition.
- Real completion/condition evaluation in the newer phase.
- **Foundation / planned:** stars could feed accomplishments and reward presentation, but current City Sessions play does not award account XP, currency, inventory, or durable entitlements.
- **Partial:** the venue page has a real cross-player venue-scoped leaderboard; the broader Trainer Career city/district projection remains local-only.
- **Partial:** signed-in end-to-end verification remains called out in current project notes.
- **Partial:** some star reporting is client-originated and needs stronger server trust/validation before it should carry high-stakes rewards.
- **Partial:** richer mid-session star-tally presentation remains unfinished.
- **★ Feed:** stars earned, rank movement, a threatened Local Legend title, and first-place takeovers are premier homepage stories.

## Future variation clearly not shipped

- More varied slot drills and mini-games are proposed.
- Codex-backed Session Stars are proposed.
- Venue-specific cosmetic loadouts are proposed.
- Board modifiers are proposed.
- These are credible extensions of existing systems, but should not be represented as current City Sessions features.

# Watch

Watch is a programmed cue-sports television experience rather than a plain video list. It combines channel schedules, “on now” logic, live sources, replay rails, metadata, chat, casting, resilient playback, ingest automation, and location in the broader homepage feed.

## Viewer experience

- Full theater page.
- Live-first playback.
- “On Now” rail.
- “Up Next” rail.
- Full-match and replay rails.
- Program guide.
- Channel selection.
- Match metadata.
- Source attribution.
- Collapsible chat.
- Mute control.
- Fullscreen.
- Keyboard shortcuts.
- Deep link to a channel.
- Deep link to an individual schedule item.
- Embedded YouTube playback.
- Embedded Facebook playback.
- Casting support.
- Capacitor/iOS-specific playback handling.
- Autoplay and fallback handling.
- Wall-clock synchronization into programmed content.
- Calculate elapsed offset for a show already in progress.
- Detect/flag a broken current item and advance.
- Mark-watched API.
- **★ Feed:** Live Now and Starts Soon have natural urgency and already fit the existing homepage module system.

## Channels and cue-sports coverage

- 8-Ball.
- 9-Ball.
- 10-Ball.
- Straight Pool.
- Snooker.
- Billiards/carom.
- Trick shots.
- One Pocket.
- Wider SDK game-category vocabulary for Artistic Pool, Balkline, Bank Pool, Blackball, Chinese 8-Ball, Cutthroat, Puzzle Rack, Pyramid, Rotation, and more.
- Channel metadata and YouTube/source URLs.
- Channel-map endpoint.
- Filter schedule by game type.
- Thumbnail, title, description, duration, game type, source, and live status.
- Host/source detection.

## Scheduling and ingest

- Deterministic 24-hour daily programming.
- Weighted content rotation by game type.
- Upcoming, past, live, date, duration, status, title, and channel filters.
- Public channel, schedule, and live endpoints.
- Authenticated schedule CRUD.
- Authenticated content ingestion.
- Default schedule-page sizing.
- Refresh/check-channel commands.
- Confirm and fetch live broadcasts.
- YouTube channel live checks.
- YouTube WebSub hooks.
- `yt-dlp` scan tooling.
- Facebook Live ingestion.
- Schedule/cache purge commands.
- Scraper history, error, and live logs in the ingestion utility.
- **Partial:** some automatic live scanners are commented out in scheduled tasks; externally or manually ingested live content still works.
- **★ Feed:** a programming recommender can combine game preferences, favorite players/sources, schedule, and viewing history.

## Watch chat and community

- Ably-backed realtime room.
- Chat history retrieval.
- Realtime message subscription.
- Anonymous read-only chat.
- Authentication required to send.
- Message deduplication.
- Autoscroll.
- New-message handling.
- Reusable chat components.
- **Partial:** follow, reaction, and share controls are hidden until schedule relationships are complete.

## Viewing rewards

- Backend watch-recording route.
- Binge Breaker accomplishment.
- Afternoon Gamer accomplishment.
- Night Owl accomplishment.
- Live Fan accomplishment.
- **Foundation / partial:** these awards are implemented server-side, but no current client call to the watch-recording endpoint was found.
- **★ Feed:** progress toward viewing accomplishments and a “continue watching” card could improve return visits once client tracking is wired.

## Watch companion surfaces

- Watch content can render in the existing homepage feed.
- TV-specific orientation handling in the mobile app.
- SDK usable independently for channel/schedule/live models.
- **Historic:** an Electron Watch/TV desktop wrapper and packaged Mac build demonstrate desktop-distribution capability, but current support/distribution should be confirmed.

# Scan and Computer Vision

Scan is a reusable computer-vision platform for converting photographs, live camera feeds, recorded clips, and video frames into stable pool-table geometry and ball state. It is useful to Pad, Trainer, venue verification, broadcast analysis, physical-table overlays, and future automatic scoring.

## End-to-end table understanding

- Detect pool balls.
- Classify cue ball and numbered balls.
- Detect pockets.
- Infer missing or obscured pockets from the visible geometry.
- Preserve inference provenance and confidence.
- Detect cushions.
- Estimate inner and outer table corners.
- Detect rails.
- Estimate cloth color.
- Detect rail diamonds.
- Classify whether an image contains a pool table.
- Distinguish overhead and freehand camera types.
- Infer table orientation geometrically.
- Solve a perspective homography.
- Transform image coordinates into a canonical portrait table.
- Canonical model sized around a 1000 × 2010 mm table space.
- Transform detected balls, points, and the source image.
- Emit diagnostics and debug overlays.
- **★ Feed:** a scan can create an instant “play this real table,” venue verification, before/after analysis, or community puzzle card.

## Camera and video intelligence

- Perceptual camera fingerprint using difference hashing.
- Group frames by camera.
- Detect camera cuts.
- Preserve separate state for each camera in a multi-camera stream.
- Prevent a cut from corrupting the current table state.
- Continuous video processing.
- `requestVideoFrameCallback` support.
- Motion-energy segmentation into padded shot windows with hysteresis, quiet-time closure, and occlusion/camera-suspension handling.
- Greedy frame-to-frame assignment.
- Anti-swap logic for nearby balls.
- Stationary-window detection.
- Two-dimensional Kalman filtering.
- Ball identity ledger.
- Camera-type stabilization.
- Homography exponential moving average.
- Pocket locks.
- Stabilized transformed-ball output.
- Per-ball path reconstruction with fragmented-track stitching, fitted route segments, and inferred cushion, ball-collision, stop, pocket, and lost events.
- Suitable foundations for livestream overlays and post-production analytics.

## Rail and diamond analysis

- Geometry-guided rail scan.
- Triplet-coherent diamond/blob detection.
- Multi-scale image analysis.
- Rail-line extrapolation.
- Cushion-position estimation.
- Table-edge diagnostics.
- Debug visualization.
- **Foundation:** rail geometry can improve bank/kick analysis, real-table calibration, and broadcast graphics.

## Classifier options

- Browser-side ONNX Runtime Web.
- Browser-side TensorFlow.js/Teachable Machine.
- InferenceJS/Roboflow detection.
- Remote HTTP inference provider.
- Node/server scanner provider.
- Lazy runtime loading.
- CDN or locally hosted runtime.
- HTML canvas input.
- HTML image input.
- HTML video input.
- ImageBitmap input.
- Configurable classification threshold.
- Model events.
- WebAssembly-backed execution where supported.
- ImageNet-style ONNX preprocessing.

## Image, clip, and video-frame APIs

- Raw table-scan endpoint.
- Full table-scan endpoint.
- Image-to-diagram endpoint.
- Clip-scan endpoint.
- YouTube-frame endpoint.
- Raw bounding-box `TableScan` model.
- Complete image-to-Pad-diagram pipeline.
- Client-side image resizing.
- Save a generated diagram with a PNG URL.
- Extract a YouTube video frame for analysis.
- Gated Pad still-photo import.
- Admin remote table scan for Trainer.
- City Sessions camera proof of a physical pool table.
- **Partial:** the platform is broader than any one public UI; each consumer has its own rollout and trust constraints.

## What Scan makes possible next

- Automatic scorekeeping from a fixed camera.
- Livestream ball-state overlays.
- Shot-by-shot broadcast metadata.
- Physical-to-digital game replay.
- Automatic Pad diagrams from instructional video.
- Table calibration for a projector.
- AR aim and route overlays.
- Search venue photos by table/equipment/room appearance.
- Verify venue submissions contain actual pool tables.
- Detect table availability/occupancy.
- Analyze practice without requiring manual shot entry.
- These are product opportunities built on real components, not all current end-user workflows.

# Learn, Content, and the Shot Codex

Learn combines editorial content, rules, diagrams, games, facts, creator video, events, and automatically detected shot knowledge.

## Rulebooks and cited answers

- Structured rulebook content.
- Natural-language questions over rulebooks.
- Answers with citations.
- Source list.
- Latency and cache metadata.
- Rulebook-specific context.
- Ask interface.
- Local question history.
- Delete history.
- Voice/audio question input.
- Experimental-answer disclaimer.
- **★ Feed:** “rule of the day,” a disputed-rule explainer, and one-tap follow-up questions make useful evergreen cards.

## Editorial and media

- Articles.
- News.
- Tutorials.
- Videos.
- Event flyers.
- Rulebooks.
- Content channels.
- Content detail pages.
- Content comments.
- Content reactions.
- Content tags.
- Publishing status and scheduling foundations.
- Reusable media library.
- Creator-specific video modules.
- Dr. Dave video module.
- Other YouTube creator modules.
- Video-frame extraction.
- Content-driven Pad diagrams.
- Content-driven Trainer drills.
- **★ Feed:** the same story can progress from article → diagram → playable drill → result, which is a much stronger loop than a conventional news feed.

## Facts and pool culture

- Facts collection.
- Random-fact endpoint.
- Source field.
- Validation state.
- Fact comments.
- Fact CRUD in the platform.
- Homepage facts module.
- **★ Feed:** short facts are useful low-friction separators between higher-commitment play and social cards.

## “What’s Your Out?”

- Interactive feed component exists.
- Pad-like problem presentation.
- Natural bridge into diagrams and Trainer.
- **Dormant:** the default feed configuration currently comments it out because of a scroll/interaction issue.
- **★ Feed:** after fixing the interaction bug, this should be a flagship daily module rather than a minor content card.

## Shot Codex

- 92 authored shot definitions.
- 18 shot families.
- Alternate match names/aliases.
- Difficulty classification.
- Automatic discovery from live Trainer play.
- First-discovered date.
- Last-made date.
- Times made.
- Best score.
- Best tier.
- Bank depth recognition.
- Kick depth recognition.
- Combination depth recognition.
- Jump, massé, spin, cut, carom, break, foul, and other trick families.
- Shot Library menu.
- Accomplishments catalog.
- Trainer Medals catalog.
- Goals catalog.
- Collectibles catalog.
- **Partial / special-user preview:** the Codex is implemented but audience-gated in the normal Trainer feature policy.
- **★ Feed:** “new shot discovered,” “complete this family,” and “your friend just landed a Triple Bank” are ideal progression stories.

## Tool/Kit boundaries

- Rulebook and Pad tools are functional.
- **Not implemented:** current Shot Clock placeholder page.
- **Not implemented:** current Handicapper placeholder page.
- **Not implemented:** current Killers placeholder page.
- **Not implemented:** current Rack Randomizer placeholder page.
- **Not implemented:** current Scorekeeper placeholder page.
- These should stay out of a shipped feature list until their routes become real products.

# Accounts, Social, and Community

The account layer connects physical venue activity, digital games, media, diagrams, content, rewards, and notifications. It is much more substantial than login, though the conventional friend/follow graph is a notable missing piece.

## Authentication and account security

- Email/password registration.
- Email availability check.
- Email/password login.
- Token login.
- Password reset request.
- Password reset completion.
- Password change.
- Google OAuth.
- Facebook OAuth foundations.
- Web redirect OAuth.
- Native Capacitor PKCE OAuth.
- JWT/shared authentication store.
- Authentication lifecycle events.
- TOTP multi-factor authentication.
- MFA challenge.
- Recovery codes.
- MFA disable.
- CMS/admin authentication.
- Role-aware and permission-aware access.

## Player profiles

- Avatar.
- Biography.
- Hometown.
- Preferred games.
- Skill/talent level.
- Favorite venues.
- Recent check-ins.
- Total check-ins.
- Unique venues visited.
- Contribution totals.
- Weekday activity.
- Favorite playing day.
- Trainer statistics.
- Trainer history.
- Progress.
- Subscription information.
- Account settings.
- Nearby-player discovery.
- Active-player discovery.
- New-player discovery.
- **Partial:** public-profile media is deliberately hidden/commented in the current app.
- **★ Feed:** a profile supplies preference, skill, location, history, and progress signals for far better personalization than a generic activity stream.

## Comments, reactions, tags, and shares

- Polymorphic comments.
- Comment replies.
- Venue comments.
- Media comments.
- Content comments.
- Diagram-comment relationship.
- Fact comments.
- Polymorphic reactions.
- Love/favorite reaction.
- Venue favorites.
- Media favorites.
- Content reactions.
- Diagram-reaction relationship.
- User tagging on media.
- Venue tagging on media.
- Tagged-media reverse lookup.
- Share/tag acceptance.
- Share/tag rejection.
- Image uploads.
- Video uploads.
- Bunny Stream webhook.
- **Foundation:** the same interaction primitives can be applied consistently to diagrams, replays, drills, venues, and content.

## Realtime presence and communication

- Shared Ably connection.
- Presence.
- Realtime chat rooms.
- Send chat message.
- Edit chat message.
- Delete chat message.
- Chat history.
- Watch-room chat.
- Realtime game channel.
- Cue-motion events.
- Ball-motion events.
- Shot events.
- Game-state events.
- Match-lifecycle events.
- Matchmaking-matched event.
- State-request flow.
- Short-lived location beacons.
- Proximity search for players looking for a game.
- **Partial:** in-match chat is not yet a completed Trainer workflow.
- **Partial:** direct messaging surfaces and notification types exist in pieces, but a complete general-purpose DM product was not established.

## Notifications and push

- Durable notification inbox.
- All and Unread views.
- Unread count.
- Paginated notifications.
- Mark one read.
- Mark all read through a snapshot ID.
- Realtime Ably invalidation/delivery.
- The backend publishes `notification:created` and `notification:changed`; the current shared client consumes created events, while changed-event subscription/refetch remains pending.
- Firebase Cloud Messaging push.
- Multiple registered devices.
- Per-device registration.
- Idempotent deduplication.
- Retirement of stale notifications.
- Match invitation received.
- Match invitation claimed.
- Your-turn notification.
- Match-completed notification.
- Accomplishment award.
- Wallet reward.
- **Foundation only:** friend request, media tag, nearby venue check-in, and message notification types are reserved but do not yet have current producers.
- **★ Feed:** notification and homepage ranking should coordinate so urgent match actions are visible without showing the same event five times.

## Friend/follow boundary

- Friend request routes are commented out.
- Current friend-list UI acknowledges that no friend API is available.
- “Fresh faces to follow” appears as feed copy, but a complete follow action was not found.
- Do not claim a shipped friend graph today.
- **New opportunity:** build a relationship graph from explicit friends/follows, repeat opponents, shared check-ins, venue communities, and accepted media tags.
- That graph unlocks many of the most compelling homepage ideas later in this document.

# Challenges, Statistics, Achievements, and Rewards

These systems turn one-off actions into repeatable play, measurable improvement, recognition, and a real cross-product economy.

## Daily and authored challenges

- One shared Daily Challenge per day.
- Same rack/problem for every participant.
- Today tab.
- Archive tab.
- Leaderboard tab.
- Completion tracking.
- Streak tracking.
- Monthly-clear tracking.
- Top-25 boards.
- Date lookup.
- Date-range lookup.
- Slug lookup.
- Diagram-authored challenges.
- Procedurally seeded challenges.
- Difficulty.
- Game type.
- Rules.
- Time limit.
- Regeneration.
- CMS challenge editor.
- Schedule and publishing controls.
- **Partial / authenticated preview:** the Daily Challenge UI and data exist but are not a universal anonymous surface.
- **★ Feed:** the Daily Challenge, friend rank, local rank, streak, attempt count, and personal-best delta are obvious homepage anchors.

## Statistics platform

- Arbitrary named user counters.
- Venue-scoped statistics.
- Lifetime aggregate.
- Full local game history.
- Notable-event history.
- Durable account synchronization.
- Daily leaderboards.
- Weekly leaderboards.
- Monthly leaderboards.
- Yearly leaderboards.
- All-time leaderboards.
- Tie handling.
- Include-current-user option.
- Friends/user-subset filtering foundation.
- Venue leaderboard.
- City leaderboard.
- Daily Rack Speed Run metric.
- Venue Check-in Champions.
- Active-Day Streak.
- Future cabinet high-score metric.

## Trainer statistics depth

- Games played.
- Wins.
- Win rate.
- Make percentage.
- Total shots.
- Longest run.
- Average run.
- Trick points.
- Best trick.
- Recent-form sparklines.
- Last 10, 50, and 100-game windows.
- Career recap.
- Break make percentage.
- Balls per break.
- Best break.
- Break-and-runs.
- Dry breaks.
- Bank percentage.
- Kick percentage.
- Jump percentage.
- Carom percentage.
- Clean pots.
- Combinations.
- Multi-ball shots.
- Draw, follow, stop, and massé usage.
- Time at the table.
- Decision time.
- Fastest and longest games.
- Innings.
- Peak ball speed.
- Total ball travel.
- Cue-ball travel.
- Fouls.
- Scratches.
- Streaks.
- Power tendency.
- Favorite English.
- Favorite pocket.
- Average power.
- Newest 30 complete local games.
- Per-game result, shots, accuracy, duration, shot sequence, detail, and replay.
- JSON statistics export.
- JSON statistics import.
- Local-data clear.
- **Partial:** guest history does not automatically merge into an account, and server restore is not yet complete cross-device recovery.
- **★ Feed:** personal records, trend changes, strengths, weaknesses, and practice prescriptions can generate genuinely useful individualized cards.

## Accomplishments and achievements

- 138 seeded account accomplishment definitions.
- 24 accomplishment categories.
- Common, uncommon, rare, epic, and legendary rarity tiers.
- Check-in accomplishments.
- Collectible accomplishments.
- Community accomplishments.
- Economy accomplishments.
- Exploration accomplishments.
- 8-Ball accomplishments.
- 9-Ball accomplishments.
- Break accomplishments.
- General game accomplishments.
- Multiplayer accomplishments.
- Run accomplishments.
- Scratch/foul accomplishments.
- Session accomplishments.
- Skill accomplishments.
- Streak accomplishments.
- Win accomplishments.
- Gameplay accomplishments.
- League accomplishments.
- Lifetime accomplishments.
- Media accomplishments.
- Milestone accomplishments.
- Photo accomplishments.
- Social accomplishments.
- Tool accomplishments.
- Server award job.
- CSX reward amounts.
- 16 additional registered Trainer-local achievement rules.
- Achievement notifications and post-game presentation.
- **★ Feed:** rarity, progress percentage, recent awards, and “almost there” conditions provide a robust, non-invented progression feed.

## Wallet and digital ownership

- CSX wallet.
- Current balance.
- Append-only transaction ledger.
- Transaction history.
- Duplicate-award guards.
- Reward notifications.
- 60 CSX venue-check-in earn path.
- 150 CSX venue-revision earn path.
- 75 CSX daily-collection earn path.
- Variable accomplishment rewards.
- Product catalog.
- Product categories.
- Spend endpoint.
- User-owned products.
- Entitlements.
- Loadouts/equipped items.
- Venue-unlock purchase.
- Server-authoritative price.
- Atomic debit plus entitlement.
- Lazy per-venue product creation.
- RevenueCat subscription integration.
- **Not current:** real-money wallet top-ups.
- **Not current:** physical-goods checkout.
- **Not current:** a complete refund system.
- **★ Feed:** claimable rewards, enough-to-unlock prompts, new ownership, and meaningful spend history can connect contribution, play, and customization.

# Mobile, Quest, Desktop, and Physical Installations

ChalkySticks is delivered through more surfaces than a responsive website. The shared engines already support native wrappers, headset play, desktop packaging, kiosk operation, and specialized physical installations.

## Native-capable mobile app

- Capacitor iOS/Android shell.
- Camera access.
- Camera preview.
- Device information.
- Geolocation.
- Haptics.
- Keyboard integration.
- Native push notifications.
- Native share sheet.
- Screen-orientation control.
- Splash screen.
- Status bar.
- Toasts.
- Preferences/storage.
- Native OAuth.
- RevenueCat subscriptions.
- Speech recognition.
- Pad inside the app.
- Trainer inside the app.
- Watch inside the app.
- Offline/no-connection messaging.
- Mobile media upload handling.
- HEIC and image-orientation handling.
- **★ Feed:** mobile push, location, camera, haptics, and native sharing make the dynamic homepage capable of acting like a local play companion, not merely a website.

## Quest/WebXR

- WebXR immersive-VR detection.
- A-Frame session entry/exit.
- Meta Touch tracked-controller support.
- Normalized XR stick/button input.
- First-person VR camera.
- Head-locked control panel.
- Quest-specific models.
- Quest-specific render profile.
- Recenter.
- Aim.
- Power.
- English.
- Fine aim.
- Shoot.
- Jump.
- Ball movement.
- Undo.
- Rack selection.
- Table color.
- Trajectories.
- Ghost ball.
- Quest PWA shell that boots directly to freeplay.
- Automatic immersive-entry attempt in the installed PWA.
- Manual-entry fallback.
- **Partial wording:** say “WebXR and Meta Quest support,” not “native Oculus Store app.”
- Real-headset permission, refresh-rate, and long-session verification remain important release checks.

## Trainer desktop and arcade

- Electron desktop shell.
- macOS build target.
- Windows build target.
- Linux build target.
- Fullscreen cabinet mode.
- Electron sandboxing.
- WebGL, worker, and Gamepad support.
- Per-cabinet configuration.
- Optional pointer disabling.
- Long-running kiosk behavior.
- Operating-system fullscreen.
- Background update checks.
- Install update on quit.
- Default-account login retry.
- Title/attract mode.
- `unlockAll` installation option.
- Admin remote control.
- **Current specialized surface:** arcade cabinet mode is implemented, not merely conceptual.
- **Experimental hardware:** a trackball/no-button tabletop cabinet was performance-tested on multiple Android devices.

## Other companion/history

- **Historic:** Electron Watch/TV app.
- **Historic:** desktop Pad task marked complete, but current distribution and maintenance should be verified.
- **Experimental:** browser/video capture and projection workflows for physical-table analysis.
- **Experimental:** automatic homography-aligned projection.
- **Experimental:** AR game-viewer concepts.

# Physics and Shot Intelligence

Physics and shot planning are shared product infrastructure. They power Trainer, Pad’s runout preview, AI, multiplayer, replay, and future computer-vision/physical-table experiences without being tied to Vue, Three.js, or A-Frame.

## Physics engine

- Framework-independent TypeScript.
- Deterministic simulation.
- Fixed 240 Hz timestep.
- Multiple independent engine instances.
- Multiple named configurations.
- Impulse-based rigid bodies.
- Restitution.
- Coulomb friction.
- Spin transfer.
- Sliding-to-rolling transition.
- Draw and follow.
- Persistent side spin.
- Side-spin cushion deflection.
- Natural swerve.
- Optional squirt.
- Massé and follow/draw massé.
- Jump.
- Gravity and airborne motion.
- Ball rotation.
- Smart stopping.
- Rail-top landings.
- Table fall-off.
- Pocket capture and settling.
- Discrete collision strategy.
- Backtrack collision strategy.
- BacktrackPlus adaptive collision strategy.
- Adaptive-substep strategy.
- Swept continuous collision detection.
- Effective 960 Hz collision-frame resolution in BacktrackPlus trajectories.
- Ball-ball swept spheres.
- Ball-rail sweeps.
- Airborne rail clearing.
- Rectangle boundaries.
- Polygon boundaries.
- SVG path-defined table boundaries supporting absolute M/L/H/V/C/Z commands, with cubic Bézier tessellation.
- Line and circular-arc boundary parsing.
- Bézier tessellation.
- Semantic rails.
- Full shot-to-rest trajectories.
- Event streams.
- Packed worker-friendly data.
- Worker pools.
- Zero-copy/typed-array optimizations.
- Lightweight aim paths.
- Playback separated from solve.
- Reproducible multiplayer/replay outcomes.
- **Honest limit:** not a perfect material simulator; rack compression, viscoelastic cushion response, cloth nap, and environmental conditions remain outside or incomplete.

## Shot Planner

- Framework-independent planner.
- Direct-shot geometry.
- Bank-shot geometry.
- Kick-shot geometry.
- Combination candidates.
- Route event sequences.
- Physics verification.
- Intended-pocket verification.
- Correct-first-contact verification.
- Scratch rejection.
- Off-table rejection.
- Power variants.
- Cue strike-point variants.
- Search policies.
- Candidate diagnostics.
- Failed-search reasons.
- Route simplicity scoring.
- Cushion-count scoring.
- Gentler-shot preference.
- Fargo/skill profiles.
- Human-attempt simulation option.
- Leave-aware runout ranking.
- Next-shot availability.
- Cue-travel scoring.
- Safety search and scoring.
- Shared worker pool.
- **Current limitation:** Trainer AI is sophisticated single-shot search with limited leave awareness, not a complete full-rack AI runout planner.
- **Experimental:** Pad exposes full-run planning only to admins while it matures.

# SDK, API, Embeds, and Integrations

The ecosystem is designed as composable packages and services, not a collection of isolated pages.

## SDK package family

- `sdk-core` for models, collections, providers, remote config, feature flags, events, input, media, and utilities.
- `sdk-authentication` for login, registration, OAuth, tokens, and shared auth state.
- `sdk-pad` for diagrams, rules, customization, persistence, and stateless URL encoding.
- `sdk-game` for gameplay models, shots, matches, challenges, leaderboards, matchmaking, and venue-board generation.
- `sdk-physics` for deterministic billiards simulation.
- `sdk-shot-planner` for verified route search and runout/safety scoring.
- `sdk-inference` for vision, homography, tracking, and camera fingerprints.
- `sdk-table-scanner` for pool-table image classification.
- `sdk-players` for player profiles and location beacons.
- `sdk-tv` for channels, schedules, and live content.
- `sdk-extras` for facts, rulebooks, cited Q&A, places, YouTube, table scans, realtime chat, and game communication.
- ESM builds.
- Browser bundles.
- Common `sdk-core` conventions across packages.

## Core input system

- Logical action manager across device types.
- Keyboard shortcuts and phases.
- Pointer tap.
- Double tap.
- Hold.
- Swipe.
- Pinch.
- Wheel.
- Gesture presets.
- Browser gamepad.
- Auto-detect.
- Deadzone.
- Repeat.
- Rumble.
- Button combinations.
- Button sequences.
- XR controller normalization.
- Sensor sources.
- Video sources.
- Shared input mapping for embedded and white-label clients.

## Core sound and device services

- Howler-backed playback.
- Sound categories.
- Volume control.
- Pooling.
- Presets.
- Crossfades.
- Muffle effects.
- Microphone capture.
- Web speech recognition.
- Capacitor speech recognition.
- Geolocation.
- Share.
- Haptics.
- Media upload.
- Resumable upload foundations.
- Subscription services.
- Cache, network, and device utilities.

## Remote configuration and analytics

- Remote feature flags.
- Admin, staff, special-user, premium, authenticated, and general audience gates.
- Flag dependencies.
- Permission gates.
- Local overrides.
- Remote refresh.
- Remotely configurable homepage module structure.
- Provider-agnostic analytics.
- Google analytics provider.
- Meta analytics provider.
- Reddit analytics provider.
- PII scrubbing.
- Do Not Track support.
- Sampling.
- Rate limits.
- Deduplication.
- Debouncing.
- Middleware.
- DOM hooks.

## Embeds

- Stateless 2D Pad iframe.
- Read-only image mode.
- Editable Pad playground mode.
- SVG, PNG, WebP, and JPEG render options.
- Canonical compact URL DSL.
- Parent change messages.
- Chrome-free playable Trainer iframe.
- Load diagram and rules by URL.
- Load game type, balls, equipment, table appearance, environment, and camera.
- Configure power meter, ghost ball, and trajectories.
- Deferred click-to-load.
- Diagram-poster mode that avoids WebGL allocation before interaction.
- Parent commands for aids, aim, ball set, camera, cloth, cue, diamonds, English, environment, rack, power, rails, shot, undo, and state.
- Live layout replacement.
- Parent events for pocket, foul, game end, motion stop, rack, shot, trick, and turn.
- Origin validation.
- Input sanitization.
- **Partial:** pocket tightness is not yet a Trainer embed query.
- **Partial:** complete ball-position state responses and all loadout scene effects are not yet exposed.

## API breadth

- Authentication and MFA.
- Users, profiles, roles, and permissions.
- Venues, geospatial search, text search, semantic search, candidates, revisions, check-ins, and media.
- Diagrams and image generation.
- Content, channels, facts, and rulebooks.
- Comments, replies, reactions, tags, and shares.
- Media upload and video processing.
- Games, matches, shots, turns, invitations, matchmaking, and results.
- Challenges and leaderboards.
- User and venue statistics.
- Accomplishments.
- Wallet, products, catalog, entitlements, and loadouts.
- Notifications and devices.
- TV channels, schedules, live items, watch tracking, and ingest.
- Table scan, image-to-diagram, clip scan, and video-frame extraction.
- Configuration, feature flags, and remote feed.
- Location-aware activity feed.
- Realtime service integration.

# CMS, Moderation, and Venue Data Operations

The CMS is a broad operations product in its own right. It controls users, content, challenges, schedules, venues, product configuration, moderation, and the homepage without requiring application deployments.

## Permissioned admin areas

- Dashboard.
- Roles.
- Permission matrix.
- Billing service spend.
- Billing history.
- Transactions.
- Users.
- Profile administration.
- Game/stat administration.
- User media.
- Access and roles.
- Subscription view.
- Ban/unban.
- User deletion.
- Daily challenges.
- Comments.
- Flagged-comment moderation.
- Media moderation.
- Content list/editor.
- Content details, body, media, tags, and publishing.
- Reusable media library.
- Media preview, metadata/alt-text/tag editing, URL copy, and deletion.
- Venue revisions.
- Settings versions.
- Feature flags.
- General configuration.
- Homepage feed editor.
- TV schedule.
- TV game types.
- Venue search.
- Venue CRUD.
- Venue contact/location/facilities/hours/media/revisions/publishing.
- Venue candidates.
- Duplicate venue clusters.

## Remote homepage composer

- Ordered module list.
- Enable/disable modules.
- Authentication-required switch.
- Editable display text.
- Editable URLs.
- Editable code/configuration.
- Numeric props.
- Tags.
- Boolean props.
- Central API persistence.
- Roll out a new feed mix without a mobile/web release.
- **★ Feed:** this makes the homepage proposal in the next section an evolution of current infrastructure, not a greenfield rewrite.

## Venue candidate and duplicate workflows

- Candidate source/city.
- Google rating.
- Google review count.
- Place type.
- Pending/approved/denied statistics.
- Approve candidate.
- Deny candidate.
- Asynchronous Google Places enrichment.
- Duplicate-cluster scoring.
- Choose the winning venue.
- Dry-run merge preview.
- Transfer related records.
- Merge duplicate.
- Remember/dismiss a false-positive cluster.
- Search Google suggestions from CMS.

## Automated venue scanner

- Pull pending venue candidates from the API.
- Headless Google Photos scan.
- Playwright stealth/browser isolation.
- TensorFlow.js classification.
- CLIP classification by sport.
- Approval/rejection.
- High-confidence automatic approval.
- Upload approved venue images.
- Moderation web UI.
- Full pull → scan → classify pipeline.
- Watcher/daemon mode.
- Throughput and failure statistics.
- SQLite lifecycle state.
- Retry tracking.
- Pipeline run IDs.
- Per-venue child-process isolation.
- CAPTCHA handling.
- Cookie and navigation handling.
- **Internal:** this is a data-operations tool, not a consumer promise.

## CMS limitations to preserve

- **Partial:** revision viewing/diffing is current, but approval/decline controls acknowledge endpoint uncertainty.
- **Partial:** media moderation controls exist, but current API validators do not persist the requested status transition.
- Avoid claiming these workflows are fully closed-loop until the API behavior is corrected and verified.

# Internal Engineering and Delivery Platform

These systems are not homepage products, but they materially increase the speed and safety with which ChalkySticks can maintain a large multi-repository ecosystem.

## ChalkySticks MCP server

- Search source code.
- Search documentation.
- Find SDK usage.
- Find component usage.
- Find Sass usage.
- Find API usage.
- Dependency graph.
- Impact analysis.
- Package version inventory.
- Version-drift detection.
- Guarded dependency upgrades.
- Publish-cascade planning.
- Documentation freshness.
- Infrastructure inventory.
- Infrastructure search and read.
- Infrastructure hash/diff.
- Configuration validation.
- Deployment tooling.
- Read-only by default.
- Confirmation and clean-worktree guards for mutations.

## Action daemon and media pipelines

- Loopback-only action daemon.
- File-backed runs.
- Artifacts.
- Manifests.
- Logs.
- Composable pipelines.
- Blender Trainer preview rendering.
- ImageMagick convert.
- ImageMagick trim.
- ImageMagick flatten.
- Image identification.
- FFmpeg probe.
- Video frame extraction.
- Audio muting.
- Speed change.
- Transcode.
- Trim.
- Durable output artifacts for later inspection.

## Infrastructure and release operations

- Multi-service deployment configuration.
- Cache management.
- Server inventory.
- Documentation deployment.
- Package build/release workflows.
- Electron release workflows.
- SDK dependency synchronization.
- Package drift checks.
- Feature-flag and remote-config rollout.

# Important Status Boundaries

This section exists to prevent an impressive internal capability inventory from turning into overclaiming.

- Pad’s Mine/Public library, practice sets, saving, remixing, export, and Trainer handoff are current.
- Pad comments, reactions, and tags exist as SDK relationships but not as complete Pad-native social UI.
- Pad visibility selection should be verified end-to-end; the UI and model exist, but current persistence wiring warrants a check.
- Pad photo import is gated and the live-camera scanner is host/API-oriented.
- Pad runout planning is admin-only; “Best Shot” and safety planning are development-only.
- A Pad embed is a 2D diagram/playground. A Trainer embed is the playable physics experience.
- Trainer has 19 rule-strategy types, but only a subset is enabled for every ordinary user.
- Trainer’s current simulated table geometry is a regulation nine-foot table; multiple table sizes belong to Pad, not current Trainer.
- Trainer’s 8-Ball, 9-Ball, and 10-Ball are broadly available; Speed Run and Online require authentication.
- Several Trainer games, Codex, Career, community drills, and Daily Challenge surfaces are gated previews.
- Trainer online play currently supports 8-Ball, 9-Ball, and 10-Ball, with races to 1–3.
- Trainer multiplayer supports live/correspondence convergence, but not every lifecycle path has completed verification.
- Trainer spectating has engine/protocol support but no complete public in-progress match browser.
- Trainer’s replay workbench, scrubbing, automatic cameras, and video export are real; nonlinear trim/reorder/project editing is not.
- Trainer’s cosmetics are extensive, but chalk/tips are preference-only today and equipment does not alter physics.
- Trainer AI does sophisticated physics-backed single-shot search with limited leave awareness; multi-rail search and true full-rack planning remain deferred.
- Use “WebXR and Meta Quest support,” not “native Oculus Store app.”
- Watch viewing accomplishments are backend-ready but the current client tracking call was not found.
- Watch follow/reaction/share UI remains hidden.
- A complete friend/follow graph is not shipped.
- Reserved notification types are not the same as real event producers.
- City Sessions is substantial, but server trust around some star reporting and signed-in end-to-end verification still need work.
- Kit placeholders such as Shot Clock and Scorekeeper are not current tools.
- Wallet top-ups, physical checkout, and refunds are not current commerce features.
- CMS media/revision moderation has incomplete status-transition wiring.
- Gaussian-splat visuals are demo/legacy experimentation, not a current Trainer feature.
- Pad image-overlay upload controls are disabled and should not be listed as shipped.
- Generic Pool, Snooker, Aramith Premium, Aramith Black, and Predator Arcos II Pad ball manifests are dormant/commented, not current choices.

# Dynamic Homepage and Activity Feed Opportunities

The most important conclusion from this inventory is that ChalkySticks does not need to invent a dynamic homepage from scratch. It already has:

- A remotely configurable ordered feed.
- A CMS feed composer.
- Auth-required module gating.
- Reusable homepage modules.
- A location-filtered activity API.
- Venue, content, user, check-in, and media feed jobs.
- Realtime Ably events.
- Native push notifications.
- Location and favorite-venue context.
- Rich Trainer statistics and replay data.
- Daily and venue leaderboards.
- City Sessions progress.
- A wallet and accomplishment system.
- Watch schedules and live state.
- Pad diagrams and public practice sets.

The work is primarily to add better cards, publish a few missing domain events, build a lightweight relationship graph, and rank the mixture intelligently.

## Homepage status key

- **Existing** — an endpoint, event, model, component, or close equivalent already exists.
- **Compose** — the underlying data exists; this needs a new card, query, aggregation, or ranking rule.
- **New** — it needs a new relationship, workflow, or data source.
- **Urgent** — time-sensitive and should appear near the top.
- **Evergreen** — useful when the user has no fresh social/local activity.

## Existing homepage/feed foundation

Current or already-represented modules include:

- TV Playing Live and TV Playing Now.
- New users.
- New venues worldwide.
- New venues nearby.
- Nearby venues.
- Nearby halls.
- Favorite venues.
- Nearby venue check-ins.
- Venue table-photo/media feed.
- Users nearby.
- Dr. Dave videos.
- Other creator videos.
- Articles.
- Latest content.
- News.
- Tutorials.
- Event flyers.
- Facts.
- Ads.
- Messages/system messages.
- Prototype/disabled Trainer test module.
- “What’s Your Out?” component, currently disabled because of its scrolling issue.
- Remotely supplied feed structure from `/v3/config/app`; the CMS persists changes through authenticated `PUT /v3/settings/feed`.
- Location-filtered event feed from `/v3/feed`.

Existing feed-event vocabulary includes:

- Venue added.
- Venue updated.
- Venue media added.
- Venue check-in.
- Player beacon added.
- Tournament added.
- League added.
- Content added.
- Pad content added.
- News added.
- Video added.
- User added.
- Game added.
- Game updated.
- Game deleted.
- TV item added.

Current API jobs already publish a useful subset:

- Venue added.
- Venue updated.
- Venue media added.
- Venue check-in.
- Beacon added.
- Content added.
- User added.
- User media added.
- User updated.

## The homepage’s job

A strong ChalkySticks homepage should answer five questions in the first few cards:

1. Is there anything I need to act on now?
2. Is anything interesting happening around me or at a place I care about?
3. What should I play or practice next?
4. Did I or someone relevant make progress?
5. Is there something live, new, or delightful worth watching?

The feed should feel like the front door to the entire ecosystem, not a news page with product links.

## Recommended P0 modules

These offer the best combination of user value, existing data, and ecosystem breadth.

| Priority | Module | Status | Why it belongs near the top |
| --- | --- | --- | --- |
| 1 | Your online match turn | **Existing · Urgent** | A direct action with durable match and notification data |
| 2 | Match invitation / rematch | **Existing · Urgent** | High-intent social play |
| 3 | Daily Challenge + current rank | **Compose · Urgent** | A universal daily habit with an immediate Play action |
| 4 | City Sessions at a favorite/recent venue | **Compose** | Joins real places, Trainer, progress, and wallet unlocks |
| 5 | Live Now / Starts Soon on Watch | **Existing · Urgent** | Time-sensitive and visually strong |
| 6 | Nearby player looking for a game | **Existing · Urgent** | Turns the homepage into a real-world utility |
| 7 | Recent check-ins at favorite venues | **Existing/Compose** | Local social proof even before a friend graph exists |
| 8 | Personal best or newly discovered Codex shot | **Compose** | Personalized, celebratory, and replayable |
| 9 | Open-now venue recommendation | **Compose** | Uses location, hours, preferences, and venue attributes |
| 10 | New/updated favorite venue | **Existing/Compose** | A relevant version of the existing venue-update feed |
| 11 | What’s Your Out? | **Existing, fix required** | A signature interactive content format |
| 12 | Resume a drill, tutorial, replay, or Pad diagram | **Compose** | Reduces friction and recovers abandoned intent |

## Act-now and realtime modules

### Matches and multiplayer

- **Existing · Urgent:** Your turn in an asynchronous match.
- **Existing · Urgent:** Match invitation received.
- **Existing · Urgent:** Invitation accepted; rack is ready.
- **Existing:** Opponent completed a turn.
- **Existing:** Match completed.
- **Existing:** Rematch prompt.
- **Compose:** Close-game recap with final score and decisive shot.
- **Compose:** Opponent is online now—finish the correspondence match live.
- **Compose:** An open 8-Ball/9-Ball/10-Ball table matches your preferred game and race.
- **Compose:** A recently faced opponent opened a table.
- **New:** A friend opened a table.
- **New:** A favorite creator/house pro is hosting a public table.
- **New:** Live spectator card for a notable in-progress rack.
- **New:** “Jump in after this rack” queue.

### Nearby play

- **Existing · Urgent:** A nearby player beacon says someone is looking for a game.
- **Existing/Compose:** Multiple fresh check-ins indicate a favorite venue is active now.
- **Compose:** The closest open venue that matches preferred table/game attributes.
- **Compose:** A venue you have not visited is active and within a short trip.
- **Compose:** “Three familiar players are at this venue,” using repeat co-location before a friend graph exists.
- **New:** Friend checked in nearby.
- **New:** A friend group is choosing between two venues.
- **New:** Table availability or current wait estimate.
- **New:** League or tournament begins soon nearby.
- **New:** Venue-hosted open-play night.
- **New:** Booking/wait-list opening at a favorite venue.

### Watch

- **Existing · Urgent:** Live Now.
- **Existing · Urgent:** Starts in 15 minutes.
- **Existing:** Up Next on a preferred channel/game type.
- **Compose:** Continue the currently scheduled program at the correct elapsed position.
- **Compose:** A live/replay item matches the user’s preferred discipline.
- **Compose:** Watch item connected to a drill or Codex family the user is practicing.
- **New:** Venue watch party nearby.
- **New:** Live local league or tournament stream.

## City Sessions modules

- **Compose:** Current stars at a favorite venue.
- **Compose:** One condition remains to clear a board tier.
- **Compose:** New personal best on a signature game.
- **Existing/Compose:** Venue leaderboard rank.
- **Compose:** Rank moved up.
- **Compose:** Rank moved down.
- **Compose:** Another player is close to taking Local Legend.
- **Compose · Urgent:** Your Local Legend title was taken.
- **Compose:** House pro rematch.
- **Compose:** First-time board at a nearby venue.
- **Compose:** Unplayed City Sessions board within a chosen radius.
- **Compose:** Recently checked-in venue is now playable from home.
- **Existing/Compose:** You have enough CSX to unlock a venue.
- **Compose:** Earn one accomplishment or contribution reward to afford the unlock.
- **Compose:** Compare board progress across two favorite venues.
- **Compose:** Weekly neighborhood City Sessions recap.
- **New:** Venue-vs-venue star competition.
- **New:** Traveling board or seasonal modifier.
- **New:** Team session where multiple local players combine stars.

## Daily Challenge and competitive modules

- **Existing/Compose:** Today’s Daily Challenge.
- **Existing/Compose:** Current global rank.
- **Compose:** Local/city rank.
- **Compose:** Venue-community rank.
- **Compose:** Rank gained or lost since the last visit.
- **Existing/Compose:** Completion streak.
- **Compose · Urgent:** Streak expires today.
- **Compose:** Monthly clear progress.
- **Compose:** Personal best improved.
- **Compose:** First attempt versus best attempt.
- **Compose:** Top replay from the leaderboard.
- **New:** Friend leaderboard.
- **New:** Challenge a friend’s exact run.
- **New:** Ghost race against another player’s recorded result.
- **New:** Venue-specific Daily Challenge.
- **New:** Dynamic pocket-size challenge of the day.
- **New:** Creator-authored weekly challenge.

## Trainer progress and coaching modules

- **Compose:** New longest run.
- **Compose:** New Speed Run record.
- **Compose:** New Break Contest score.
- **Compose:** New fastest clear.
- **Compose:** New break-and-run.
- **Compose:** New best trick.
- **Compose:** Codex shot discovered.
- **Compose:** Codex family completion percentage.
- **Compose:** Rare Trainer Medal earned.
- **Compose:** Account accomplishment earned in Trainer.
- **Compose:** Goal is one action from completion.
- **Compose:** Career/City Sessions milestone.
- **Compose:** Recent match result with rematch.
- **New:** Persist and continue tutorial progress; current tutorial state is ephemeral.
- **New:** Persist and resume an unfinished official drill; no durable drill checkpoint exists today.
- **Compose:** Replay the last complete match.
- **Compose:** “Watch your best shot” replay chapter.
- **Compose:** Weekly training recap.
- **Compose:** Accuracy trend improved.
- **Compose:** Break results improved.
- **Compose:** Favorite shot/pocket/power trend changed.
- **Compose:** Personalized weakness card: “You missed 42% of long left cuts this week.”
- **Compose:** Recommended existing drill based on misses.
- **New:** Automatically generated Pad drill based on the player’s miss pattern.
- **New:** AI-generated next lesson.
- **New:** Compare this week’s form to a similar-skill cohort.
- **New:** Train against a recorded “ghost” run.

## Replay and highlight modules

- **Compose:** Rare trick replay.
- **Compose:** Match-winning shot.
- **Compose:** Largest comeback.
- **Compose:** Break-and-run highlight.
- **Compose:** Unusual jump or massé.
- **Compose:** Multi-rail bank/kick.
- **Compose:** High trick-score sequence.
- **Compose:** Auto-selected shot of the day.
- **Compose:** Personal highlight reel from the week.
- **New:** Friend highlight.
- **New:** Community-voted shot of the day.
- **New:** “Can you beat this run?” exact-rack challenge from a replay.
- **New:** Theme-park-photo-style automatic replay package.
- **New:** Shareable vertical-video rendering.
- **New:** Venue-branded highlight reel.

## Pad, drills, and community-creativity modules

- **Existing/Compose:** Newly published public diagram.
- **Compose:** New diagram in a saved or owned practice set.
- **Existing/Compose:** Recently remixed diagram.
- **Compose:** Trending public diagram by loads/remixes.
- **Compose:** Recently updated official practice set.
- **Compose:** Community drill matched to the user’s skill.
- **Compose:** Drill from a recently discovered Codex family.
- **Compose:** Diagram attached to a current article/video.
- **Compose:** “Play this diagram” direct Trainer launch.
- **Compose:** Continue editing an unsaved/local Pad draft.
- **Compose:** Resume a saved diagram.
- **Compose:** A creator published a multi-diagram lesson.
- **New:** Creator follows.
- **New:** Diagram reaction/comment activity in Pad.
- **New:** Remix lineage card showing source and variations.
- **New:** Collaborative diagram/set.
- **New:** Weekly community puzzle contest.
- **New:** Scan a table photo to publish a challenge.

## Venue and local-community modules

- **Existing:** Newly added venue nearby.
- **Existing:** Newly added venue worldwide.
- **Existing:** Venue updated.
- **Existing:** New venue photo.
- **Existing:** Recent venue check-in.
- **Compose:** Recently updated favorite venue.
- **New / fix required:** Recently approved community revision.
- **Compose:** Venue marked reopened.
- **Compose:** Venue marked permanently closed, with alternatives.
- **Compose:** New hours.
- **Compose:** New table/equipment attributes.
- **Compose:** New League/Tournament availability attribute.
- **Compose:** New comments at a favorite venue.
- **Compose:** New community media at a favorite venue.
- **Compose:** Trending nearby venue based on fresh check-ins.
- **Compose:** Quiet alternative to a currently busy venue.
- **Compose:** “People who play your preferred game go here.”
- **Compose:** “Try a 9-foot room,” based on the player’s normal venue history.
- **Compose:** City/neighborhood venue digest.
- **Compose:** Recently enriched or community-confirmed listing.
- **Compose:** “Help complete this venue” missing-data mission.
- **Compose:** Confirm hours.
- **Compose:** Add a photo.
- **Compose:** Verify table sizes.
- **Compose:** Confirm whether the venue is still open.
- **Existing/Compose:** Contribution submitted and CSX earned.
- **New:** Venue-owner announcement.
- **New:** Tonight’s specials.
- **New:** Table-rate update.
- **New:** Booking/wait list.
- **New:** First-party venue event calendar.

## Check-in and relationship modules

- **Existing:** Latest nearby check-ins.
- **Compose:** Repeat players at the same favorite venue.
- **Compose:** Someone with similar preferred games checked in nearby.
- **Compose:** A recent opponent checked in nearby.
- **Compose:** A player previously co-located with you is at a venue now.
- **New:** Recent check-ins from friends.
- **New:** Friends at your favorite place now.
- **New:** “You just missed” a friend/recent opponent.
- **New:** Friend has visited a new venue.
- **New:** Friend became Local Legend.
- **New:** Friend earned a rare accomplishment.
- **New:** Followed player published a replay or drill.
- **New:** Small private group/session planning.

## Achievements, wallet, and ownership modules

- **Existing/Compose:** Accomplishment earned.
- **Compose:** Accomplishment progress.
- **Compose:** Almost-complete accomplishment.
- **Compose · Urgent:** Streak is at risk.
- **Existing:** Wallet reward.
- **Compose:** Daily/weekly wallet earnings recap.
- **Compose:** Enough CSX for a relevant unlock.
- **Compose:** Suggested venue unlock after a recent visit.
- **Compose:** Newly owned cosmetic.
- **Compose:** New loadout item available.
- **Compose:** Rare/epic/legendary reward reveal.
- **Compose:** Continue an incomplete collectible set.
- **Compose:** Community contribution generated a reward.
- **New:** Limited-time cosmetic.
- **New:** Seasonal collection.
- **New:** Gift or challenge-stake mechanism.
- **New:** Venue-sponsored reward.

## Learn and media modules

- **Existing:** Article.
- **Existing:** News.
- **Existing:** Tutorial.
- **Existing:** Video.
- **Existing:** Event flyer.
- **Existing:** Fact.
- **Existing, fix required:** What’s Your Out?
- **Compose:** Rule of the day.
- **Compose:** Rule answer related to the player’s last game.
- **Compose:** Codex shot explanation.
- **Compose:** Drill paired with a creator video.
- **Compose:** “Watch, diagram, then play” lesson bundle.
- **Compose:** Trending question from the cited rulebook Q&A.
- **Compose:** Content matched to preferred games and current skill.
- **Compose:** Weekly learning path.
- **New:** Community-submitted rules question.
- **New:** Expert answer/video response.
- **New:** Interactive quiz that launches a table state.

## Net-new homepage-native ideas

These ideas do not need to masquerade as existing features. They are interesting precisely because the current platform makes them plausible.

### Real-world pool pulse

- Live venue pulse combining recent check-ins, fresh comments, new media, current beacons, hours, and City Sessions play.
- Estimated busy/quiet state.
- Camera- or check-in-derived table availability.
- Neighborhood heat map.
- “Best place to play right now” recommendation.
- “Where players at your level are gathering.”
- Weather-aware indoor-play recommendation.
- Time-of-day-aware room recommendation.
- Travel mode that surfaces boards and venues in an upcoming city.
- Crossed-paths history with privacy controls.
- “Missed connections” for opted-in players who repeatedly share venues.

### Social play graph

- Friends and follows.
- Recent opponents.
- Repeat co-players.
- Shared-venue communities.
- Practice-set/creator follows.
- Small clubs.
- Session groups.
- Team builder based on location, preferred game, and skill.
- Challenge-any-card action.
- Private activity visibility.
- Close-friends-only check-ins.

### Adaptive coaching feed

- Automatically identify weak shot families.
- Convert recent misses into a Pad diagram.
- Generate a rules-backed Trainer drill.
- Schedule spaced repetition.
- Detect when the weak family improves.
- Celebrate mastery with Codex/accomplishment progression.
- Recommend a relevant article or video.
- Compare predicted versus actual make rate.
- Explain a better route after a replay.

### Community challenges

- Turn any replay into an exact-rack challenge.
- Turn any Pad diagram into a one-tap contest.
- Friend ghost races.
- Venue-versus-venue boards.
- City-versus-city boards.
- Neighborhood seasons.
- Creator challenge series.
- Team cumulative stars.
- Dynamic pocket-size ladders.
- Daily trick family.
- Weekly safety puzzle.

### Venue participation

- Listing-completeness missions.
- Crowd verification.
- Reopen/closed verification.
- Table-brand and size verification.
- League/tournament schedule contributions.
- Venue-owned posts.
- Specials and table rates.
- Bookings and wait lists.
- Sponsored City Sessions boards.
- Venue-branded cosmetics and replays.
- Reward drops for physical visits.

### Geographic collectibles

- City badges.
- Neighborhood sets.
- Venue-stamp passport.
- Table-type collections.
- “Play all five boroughs” routes.
- Travel streaks.
- Secret/limited City Sessions conditions.
- Physical check-in plus digital challenge combination.
- Local history/fact collectibles.

## Suggested signed-in feed composition

A good signed-in session should be heterogeneous and finite, not an endless pile of interchangeable carousels.

1. One urgent action, if present: turn, invite, live event, nearby beacon, or expiring streak.
2. One personalized play card: Daily Challenge, City Sessions, resume drill, or weakness practice.
3. One local/social card: check-in, favorite-venue update, Local Legend, or nearby player.
4. One progress card: personal best, Codex discovery, accomplishment, wallet reward, or rank movement.
5. One watch/learn card: live program, replay highlight, rule, tutorial, or creator video.
6. One discovery card: new venue, public diagram, practice set, opponent, or game mode.
7. Optional sponsored/promotion card, frequency-capped.
8. Refresh with new modules only when the underlying event set changes materially.

## Suggested signed-out feed composition

The signed-out homepage should demonstrate the ecosystem without pretending to know the visitor:

1. Live Now or Up Next on Watch.
2. Nearby/open venues after optional location consent.
3. Daily Challenge preview with a guest attempt.
4. What’s Your Out?
5. Public Pad diagram or community drill.
6. City Sessions explanation at a nearby venue.
7. Pool fact or cited rule answer.
8. Recent venue photos/check-ins in coarse location.
9. One clear account benefit: save progress, receive turns, publish diagrams, earn CSX.

## Ranking signals

The feed ranker should mix explicit product priorities with user relevance.

### Positive signals

- Urgency.
- Distance.
- Favorite venue.
- Recent venue visit.
- Preferred game type.
- Skill match.
- Existing match relationship.
- Explicit friend/follow.
- Repeat opponent.
- Repeat co-location.
- Unfinished progress.
- Near-complete goal.
- Rank movement.
- Novelty.
- Freshness.
- Live state.
- Strong media/replay.
- Directly playable action.
- Contribution opportunity.
- High-confidence venue data.

### Negative signals

- Already seen.
- Already completed.
- Stale venue status.
- Repeated creator/source.
- Too many cards from one product.
- Too many passive content cards.
- Too many promotional cards.
- Excessive travel distance.
- Wrong skill level.
- Duplicate notification and feed event.
- Low-confidence inferred social relationship.
- Location-sensitive content without consent.
- A card whose destination is gated or unfinished for the current audience.

## Feed guardrails

- Never expose precise check-in/location data beyond the user’s chosen visibility.
- Use coarse location for anonymous visitors.
- Let users mute products, venues, people, and card families.
- Explain recommendation reasons: “Because you favor 9-Ball” or “At a venue you visited.”
- Deduplicate push, notification inbox, and homepage stories.
- Collapse repetitive events into a digest.
- Apply frequency caps to ads, rewards, and venue promotions.
- Prefer one strong card per product before repeating a product.
- Do not rank a hidden/gated destination for an ineligible user.
- Expire realtime cards aggressively.
- Clearly distinguish sponsored, venue-authored, inferred, and community content.
- Preserve moderation status and audience rules.
- Let “not interested” improve future ranking.
- Keep critical match turns and invites accessible outside the ranked feed.

## Recommended implementation sequence

### P0 — compose existing data

- Fix and restore What’s Your Out?
- Add universal Daily Challenge card with rank/streak.
- Add Your Turn and Match Invite cards.
- Upgrade Live Now into Live Now/Starts Soon.
- Add City Sessions progress card for favorite/recent venues.
- Add nearby beacon/player-looking-for-game card.
- Add favorite-venue update card.
- Add personal-best/accomplishment card.
- Add resume-last-activity card.
- Add feed deduplication and per-product diversity rules.

### P1 — publish richer domain events

- Publish Trainer personal-best, Codex, trick, replay-highlight, and drill-completion events.
- Publish City Sessions star and Local Legend changes.
- Publish Daily Challenge rank movement and streak-risk events.
- Publish wallet eligibility/affordability events.
- Publish diagram/set/remix events.
- Complete and verify venue-revision approval, then publish approval and meaningful-field-change events.
- Add composite Venue Pulse.
- Add weekly player/local digest.
- Add ranking explanations and mute controls.

### P2 — add missing relationships and creation loops

- Ship friends/follows or a broader play-relationship graph.
- Add friend check-ins and friend activity.
- Add replay-to-challenge.
- Add adaptive coaching.
- Add creator/practice-set follows.
- Add venue events, rates, and owner posts.
- Add occupancy/table availability.
- Add venue-vs-venue and friend ghost challenges.
- Add geographic collectibles and travel mode.

## A practical first homepage mix

If only eight new/refined modules are built, use:

1. **Your Turn / Invite** — urgent and transactional.
2. **Daily Challenge** — universal habit.
3. **City Sessions Near You** — differentiates ChalkySticks from ordinary pool games and directories.
4. **Venue Pulse** — makes the physical community feel alive.
5. **Personal Best / Codex Discovery** — demonstrates Trainer depth.
6. **Live Now / Starts Soon** — adds time and media.
7. **What’s Your Out?** — signature interactive content.
8. **Resume / Recommended Next** — turns history into retention.

That mix touches multiplayer, competition, real venues, local community, training, media, Pad, and personalization without requiring the unfinished friend graph on day one.

# Research Basis

The catalog was assembled from current source, tests, API routes/controllers/models, product documentation, task/status notes, and configuration across these primary areas:

- `bin/documentation` — Pad, Trainer, SDK, API, City Sessions, product notes, and status tasks.
- `repos/v3/framework/vue/vue2-pad` — Pad editor, library, save/remix, scan, tutorial, export, embeds, and planner integration.
- `repos/v3/framework/vue/vue2-trainer` — games, rules, AI, physics integration, controls, cameras, replay, multiplayer, stats, Codex, equipment, XR, Electron, and embeds.
- `repos/v3/framework/vue/vue2-components` — shared notification, account, feed, and UI surfaces.
- `repos/v3/sdk` and package repositories — core, authentication, Pad, game, inference, physics, players, shot planner, TV, and extras.
- `bin/web-app`, `bin/web-v3`, and `bin/web-new` — Find, venue pages, maps, feeds, profiles, Watch, mobile delivery, and City Sessions.
- `bin/api-v2` — v3 API, venue/check-in/media pipelines, games, notifications, stats, accomplishments, wallet, catalog, entitlements, TV, and background jobs.
- `bin/cms-v2` — content, users, venues, moderation, TV, challenges, feature flags, and remote homepage composition.
- `prototypes/46-automated-venue-scanner` — candidate photo discovery and classification pipeline.
- `bin/quest-app` — direct-to-Trainer Quest/WebXR shell.
- `bin/mcp`, `bin/daemon`, and `bin/infrastructure` — engineering search, action/media pipelines, and delivery operations.

Counts such as venue totals, catalog sizes, accomplishment totals, modes, drills, equipment, and Codex entries are snapshots from the current repository and should be regenerated as those catalogs evolve.
