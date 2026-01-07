# API Endpoints Quick Reference

Base URL: `/v3`

---

## Authentication

```
POST   /auth/login                    Login with credentials
POST   /auth/logout                   Logout (auth)
POST   /auth/register                 Register new user
POST   /auth/forgot-password          Request password reset
POST   /auth/reset-password/{token}   Reset password
POST   /auth/google                   Login via Google token
GET    /auth/google                   Redirect to Google OAuth
GET    /auth/google/callback          Google OAuth callback
```

---

## Users

```
GET    /users                         List users
GET    /users/{user}                  Get user profile
PUT    /users/me                      Update current user (auth)
GET    /users/{user}/media            Get user media
POST   /users/{user}/media            Upload media (auth)
GET    /users/{user}/wallet           Get wallet (auth)
POST   /users/{user}/wallet/collect   Collect points (auth)
POST   /users/{user}/wallet/spend     Spend points (auth)
```

---

## Venues

```
GET    /venues                        List venues (location-based)
GET    /venues/{venue}                Get venue details
GET    /venues/random                 Get random venue
GET    /venues/search                 Search venues
POST   /venues                        Create venue (auth)
PUT    /venues/{venue}                Update venue (auth)
GET    /venues/{venue}/media          Get venue media
POST   /venues/{venue}/media          Upload venue media (auth)
GET    /venues/{venue}/checkins       Get check-ins
POST   /venues/{venue}/checkins       Check in (auth)
GET    /venues/{venue}/comments       Get comments
GET    /venues/{venue}/reactions      Get reactions
GET    /venues/{venue}/revisions      Get revisions
```

---

## Games & Matches

```
GET    /games                         List games
GET    /games/{game}                  Get game details
GET    /games/{game}/state            Get game state
POST   /games                         Create game (auth)
GET    /games/{game}/shots            List game shots
POST   /games/{game}/shots            Record shot (auth)
GET    /games/{game}/innings          List innings
GET    /games/{game}/innings/current  Get current inning
POST   /games/{game}/innings          Create inning (auth)

GET    /matches                       List matches
GET    /matches/{match}               Get match details
POST   /matches                       Create match (auth)
GET    /matches/{match}/games         Get games in match
POST   /matches/{match}/games         Create game in match (auth)
```

---

## Comments & Reactions

```
GET    /comments                      List comments
POST   /comments                      Create comment (auth)
PUT    /comments/{comment}            Update comment (auth)
DELETE /comments/{comment}            Delete comment (auth)
POST   /comments/{comment}/flag       Flag comment (auth)

GET    /reactions                     List reactions
POST   /reactions                     Create reaction (auth)
DELETE /reactions/me                  Delete my reaction (auth)
```

---

## Media

```
POST   /media/presigned-url           Get S3 presigned URL (auth)
POST   /media/image/create-upload     Create image record (auth)
POST   /media/video/create-upload     Create video record (auth)
GET    /media/{userMedia}/shares      Get media shares (auth)
POST   /media/{userMedia}/shares      Share media (auth)
GET    /media/{userMedia}/tags        Get media tags (auth)
POST   /media/{userMedia}/tags        Add tag (auth)
```

---

## Diagrams

```
GET    /diagrams                      List diagrams
POST   /diagrams                      Create diagram
GET    /diagrams/{hash}               Get diagram
GET    /diagrams/{hash}/svg           Get diagram SVG
GET    /diagrams/{hash}/png           Get diagram PNG
POST   /diagrams/{hash}/generate-images  Generate PNG/SVG (auth)
```

---

## Content & TV

```
GET    /content                       List content
GET    /content/{content}             Get content
GET    /rulebooks                     List rulebooks
GET    /rulebooks/{id}                Get rulebook

GET    /tv                            Get TV overview
GET    /tv/channels                   Get TV channels
GET    /tv/live                       Get live broadcasts
GET    /tv/schedule                   Get TV schedule
POST   /tv/schedule                   Create schedule (auth)
```

---

## Services

```
GET    /ads                           Get advertisements
GET    /statistics                    List statistics
GET    /beacons                       List beacons
GET    /feed                          Get user feed
GET    /data/geocode                  Geocode location
GET    /data/place                    Get place info
GET    /data/places/suggestions       Get place suggestions
```

---

## Laravel Patterns (IMPORTANT)

- Get current user: `app('user.current')` NOT `auth()->user()`
- Error responses: `$this->errorNotFound()` NOT `response()->json()`
- Use dedicated Request classes for validation
- Controllers extend `Response.php` base class
