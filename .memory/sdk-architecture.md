# SDK Architecture Reference

## Namespace Structure

The SDK exports a unified `ChalkySticks` namespace:

```typescript
ChalkySticks.Collection.*      // All collections from all packages
ChalkySticks.Model.*           // All models from all packages
ChalkySticks.Factory.*         // All factories from all packages
ChalkySticks.Enum.*            // All enumerations
ChalkySticks.Authentication    // Full auth module
ChalkySticks.Core              // Full core module
ChalkySticks.Extras            // Full extras module
ChalkySticks.Game              // Full game module
ChalkySticks.Pad               // Full pad module
ChalkySticks.Players           // Full players module
ChalkySticks.TV                // Full TV module
ChalkySticks.Constants         // Global constants
ChalkySticks.Environment       // Environment configuration
ChalkySticks.Exception         // Exception classes
ChalkySticks.Utility           // Core utilities
```

---

## Package Standard Exports

Each domain package follows this pattern:

```typescript
export * as Collection from './Collection'
export * as Core from '@chalkysticks/sdk-core'
export * as Factory from './Factory'
export * as Model from './Model'
export * as Enum from './Enum'        // where applicable
export * as Utility from './Utility'  // where applicable
```

---

## SDK-Core Modules

| Module | Contents |
|--------|----------|
| Collection | Advertisement, Comment, Content, Feed, Media, Message, Meta, Reaction, User, UserMedia, UserWallet, Venue, VenueCheckin, VenueDetail, VenueHour, VenueMedia, VenueRevision |
| Model | Data model representations of all collections |
| Factory | Factory methods to instantiate models |
| Enum | Achievement, ContentType, ContentMediaType, Currency, MediaType, MediaGroup, MediaSubgroup, MediaShareType, ProductType, ReactionType, VenueStatus, VenueType, VenueMediaType |
| Event | Event dispatching system |
| Exception | Error/exception classes |
| Input | Sensor, pointer, keyboard, video input handling |
| Provider | Data providers and services |
| Strategy | Subscription and media strategies |
| Utility | Geolocation, hysteresis, intervals, latching, shortcuts |
| Data | Data access layer |
| Sound | Audio management |
| Common | ChalkySticks main class, Environment, Constants |

---

## Build Outputs

Each package provides:
- **ESM:** `build/esm/index.js`
- **CJS:** `build/cjs/index.cjs`
- **Web Bundle:** `build/web/chalkysticks-*.js`

---

## Dependency Graph

```
sdk (root)
├── sdk-core (FOUNDATION)
│   ├── restmc
│   ├── tus-js-client
│   └── @types/googlemaps
│
├── sdk-authentication
│   └── sdk-core + Capacitor OAuth2
│
├── sdk-pad
│   └── sdk-core
│
├── sdk-players
│   └── sdk-core
│
├── sdk-game
│   └── sdk-core + luxon + reflect-metadata
│
├── sdk-tv
│   └── sdk-core
│
├── sdk-venues
│   └── sdk-core + luxon + reflect-metadata
│
├── sdk-extras
│   └── sdk-core + luxon + reflect-metadata
│
└── sdk-inference (OPTIONAL)
    └── sdk-core + sdk-extras + inferencejs
```
