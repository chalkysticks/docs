# Vue Ecosystem Reference

## Technology Stack (All Vue Projects)

- Vue 2.7.14 (NOT Vue 3)
- TypeScript 5.1.6
- vue-property-decorators (class-based syntax)
- Vuex for state management
- Vue Router 3.5
- GSAP for animations
- Three.js for 3D graphics

---

## vue2-components

**Path:** `/repos/v3/framework/vue/vue2-components`
**Package:** `@chalkysticks/vue2-components`

Reusable UI component library with `Chalky` prefix.

### Component Categories

| Category | Components |
|----------|------------|
| Authentication | AuthPanel, BasicLogin, BasicSignup, Modal, Navigation |
| UI Elements | Badge, BarGraph, CoachMark, CoachMarkSequencer, FeatureCard, ProgressBar, Tooltip |
| Forms | ImageUploader, VideoUploader, Search, UserProfile |
| Media | Feed, CardSwipe, VideoUploader |
| Branding | Standard, Badge, Splash logos |
| Reactions | Button, List, Favorite, Summary |
| Social | Chat, Comments, Events, Facts, Content |
| Video | TV/Video Theater components |
| Other | Wallet, User, Venue modules |

---

## vue2-trainer

**Path:** `/repos/v3/framework/vue/vue2-trainer`
**Package:** `@chalkysticks/vue2-trainer`

Physics-based pool simulator.

### Key Features

- Custom physics engine (60Hz timestep)
- Game variants: 8-ball, 9-ball, 10-ball, 3-ball
- Ball physics: spin, english, friction, collision
- Camera modes: overhead, side, corner, behind-cue, first-person
- Training: shot replay, undo, frame-by-frame analysis

### Architecture

```
Service Layer (Game.ts, BallManager, RackManager, ShotExecutor, FoulDetector)
       |
Engine Layer (GameLoop, PhysicsEngine, RenderManager)
       |
Physics/Rendering (CollisionDetector, CollisionResolver, TrajectoryPredictor)
```

### Console API

`window.game` provides: start, stop, shoot, rackBalls, setPower, setEnglish, etc.

---

## vue2-pad

**Path:** `/repos/v3/framework/vue/vue2-pad`
**Package:** `@chalkysticks/vue2-pad`

Diagram/notation tool using manager-based architecture.

### Managers

| Manager | Purpose |
|---------|---------|
| TableManager | Orchestrates all pad operations |
| BallManager | Add/remove/position balls |
| LineManager | Coach lines between balls |
| RailManager | Table boundary management |
| TrajectoryManager | Shot path visualization |

### Key Operations

```typescript
addBall()              // Drop balls (cue, solid, striped, ghost)
removeBall()           // Delete specific balls
clearTable()           // Wipe everything
addLine()              // Draw coach lines
moveBalls()            // Reposition selections
exportTableState()     // Persist via SDK
save()                 // Save diagram
```

### Events

- `pad.change` dispatches on every mutation

---

## web-app (Capacitor Mobile)

**Path:** `/bin/web-app`
**Version:** 3.27.4

Main cross-platform app integrating all Vue frameworks.

### Key Integrations

- Capacitor 6.x (iOS/Android)
- Firebase 10.0 (analytics, push)
- RevenueCat (in-app purchases)
- Socket.io (real-time)
- Teachable Machine (AI shot detection)

### Structure

```
App/        Pages, layouts, views, scenes, factories, enums
Core/       Core framework logic
Store/      Vuex store with modules and plugins
Manager/    Game, service managers
Theme/      ChalkySticks styling
Asset/      Images, sounds, videos, fonts, i18n, 3D models
Plugin/     Custom Vue plugins
Middleware/ Route protection, authentication
```

---

## web-pad

**Path:** `/bin/web-pad`
**Version:** 0.5.7

Browser-based diagram tool (web-only, no Capacitor mobile).

---

## Project Relationships

```
web-app (Capacitor Mobile)
    |
    +-- vue2-trainer (game engine)
    +-- vue2-components (UI library)
    +-- vue2-pad (diagram tool)
    +-- @chalkysticks/sdk

web-pad (Standalone Web)
    |
    +-- vue2-pad
    +-- vue2-components
    +-- @chalkysticks/sdk
```
