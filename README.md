## Screenshots
<img width="1920" height="1080" alt="lvl1_screen10" src="https://github.com/user-attachments/assets/81a91b65-2b3b-4718-b4f0-18394e200d84" />
<img width="1920" height="1080" alt="lvl1_screen12" src="https://github.com/user-attachments/assets/f3ab9be6-beae-4f40-af69-8232183261be" />
<img width="1920" height="1080" alt="settings_screen1" src="https://github.com/user-attachments/assets/074abdf4-ad73-4476-8d72-d7bdd943086b" />
<img width="1920" height="1080" alt="lvl1_screen14" src="https://github.com/user-attachments/assets/6540034c-5881-4d64-847f-0db62342c2e7" />
<img width="1920" height="1080" alt="lvl2_screen2" src="https://github.com/user-attachments/assets/eb5c07e7-e36c-4fe2-a630-c8ccce78679a" />
<img width="1920" height="1080" alt="lvl1_screen5" src="https://github.com/user-attachments/assets/c946676c-dcbf-4878-b5fb-840acb9102a3" />
<img width="1920" height="1080" alt="lvl3_screen1" src="https://github.com/user-attachments/assets/7789a891-d7bf-481a-b874-2a2b90ef8eaf" />
<img width="1920" height="1080" alt="lvl1_screen6" src="https://github.com/user-attachments/assets/15780e26-78b3-4552-9018-2f18adf655f2" /><img width="1920" height="1080" alt="lvl1_screen7" src="https://github.com/user-attachments/assets/df1f17ae-01ea-4dad-bc5f-4b912ac5692b" />
<img width="1920" height="1080" alt="settings_screen3" src="https://github.com/user-attachments/assets/3bcd04dd-02d5-4b0c-8490-a46396a88e5e" />
<img width="1920" height="1080" alt="lvl1_screen8" src="https://github.com/user-attachments/assets/f26485c3-0bea-48e7-8747-44cbfcd7cfec" />
<img width="1920" height="1080" alt="lvl1_screen11" src="https://github.com/user-attachments/assets/a7774049-1794-4a1a-b02d-1a1c9ca02b75" />

--- 

## Weapon System

A complete weapon system with dedicated weapon slots:

**Weapon Slots**
- Slot 1 — Rifle  
- Slot 2 — Pistol  
- Slot 3 — Sniper  
- Slot 4 — Shotgun  

### Features
- Fire / Reload logic
- ADS / Iron Sights (aiming = scope / ads)
- Spray pattern
- Shotgun-specific reload & firing logic
- Weapon raise / equip / reload / jog / crouched jog / inspect animations
- GTA 5 style **weapon wheel**
- scroll through available weapons
- Ammo tracking (centralized, notify-driven)
- Camera shake on fire
- Weapon-specific animation poses
- Movement-based recoil

---

## First-Person Animation System

All first-person animations were created manually using Sequencer:

- Jog
- Raise / Equip
- Reload (magazine & shotgun loop)
- Fire
- Inspect
- ADS / Aiming
- Sprint
- Crouched Jog
- Stand to Jump

### Animation Blueprint
- Blend Pose per Bone
- State Machines
- Speed-driven, state-driven transitions

### Footstep System
- Main Character: physical material based surface sound playback after reaching certain horizontal or vertical distance
- AI: anim notify footsteps
---

## AI System

- Vision & hearing perception, chasing player
- Patrol logic
- Bots can fire and throw grenades
- Controlled spawn lifecycle
- Wave-based enemy logic

---

## Modular Damage System

- Directional damage indicators (HUD)
- Fall damage system
- **Bone-based damage multipliers**
  - Head / Body / Limbs

### Projectile Master System
- Centralized projectile base class
- Line-trace registration
- Physical material based impact effects
- Surface-based Niagara emitters:
  - `NS_Blood` (player and AI mesh hit)
  - `NS_Spark` (headshot)
- Impact differentiation (enemy / environment / self)

---

## Loot & Interaction System

- Weapon pickups
- Ammo pickups
- Grenades
- First aid kits
- kevlar pickups
- Water bottle pickups for stamina
- All pickups use a shared Interact interface.
- Modular Drop System
- Pickup sound effects (including object drop sounds)

### Interaction Feedback
- `WBP_Take` widget
- Triggered via interaction sphere collision

---

## Round & Progression System

- Centralized round lifecycle handled by GameMode
- Enemy kill tracking
- Spawner registration & completion tracking
- Win / Lose conditions

---

## Movement & Mechanics

- Bunnyhop (timing-based)
- Sprint / Crouch modes
- Stamina system
- Water restores stamina
- Medkits restore health
- Flashlight
- Armor (kevlar) system
- climbing ladder
---

## Input System

- Enhanced Input (action-based)
- Fully rebindable controls
- Decoupled input → gameplay logic
- Clean handling of conflicting actions (reload / aim / fire / inspect)

---

## Context-sensitive HUD Hints

- Animated action hints
- Pulse animations
- Dynamic key binding support
- Automatic hint evaluation
- Health / stamina / grenade usage suggestions

---

## Dynamic Input Visualization

- Runtime key binding detection
- Key texture synchronization
- HUD key hints
- Weapon slot key synchronization
- Interact widget key synchronization
- Fully compatible with rebinding

---

## Statistics System

Runtime tracking of:

- Time
- Accuracy
- Shots fired
- Shots hit
- Enemies killed

Prepared for leaderboard integration.

## Animated HUD & UI System

### HUD
- Crosshair
- Health / Stamina prog bars (animated)
- Ammo information, First Aid kits, Water Bottles, Grenades count
- Weapon slots
- Kill counter
- Directional damage indicators
- Notifications system (queue-based)
- Minimap (zoom / rotation options)
- Crouch / Staying pose representation

### Weapon Wheel
- GTA-style radial wheel
- Mouse wheel navigation
- Visual slot highlighting (green color + increasing weapon slot widget size)

---

## Common UI Main Menu System

A fully featured menu system built with Common UI:

### Graphics Settings
- Resolution
- FPS Limit
- VSync
- Textures Quality
- Shadows
- Global Illumination
- Anti-Aliasing
- Draw Distance
- Effects
- Reflections
- Post Processing
- Foliage
- Shading
- Landscape

### Audio Settings
- Master / FX / Music
- Audio sliders
- Output device selection

### Controls Settings
- Rebindable actions:
  - Movement
  - Jump
  - Fire
  - Aim / ADS
  - Reload
  - Inspect
  - Weapon Wheel
  - Slots 1–4
  - Grenade
  - Medkit
  - Water
  - Flashlight
  - Drop Weapon
  - Sprint
  - Crouch
  - Interact
  - Pause

### Gameplay Settings
- HUD Color
- Crosshair Color
- Auto Reload
- Crouch Mode
- Minimap Rotation
- Minimap Zoom
- Mouse Sensitivity
- Reverse Mouse
- FPS Counter toggle

### UI Architecture
- Base Layout + layered widgets
- All widgets pushed to certain layers of common layout HUD class
- Reusable sub-widgets:
  - Slider
  - Option Cycle
  - Key Button
  - Menu Button
  - Option Panel
  - Confirmation Dialog
- UI sounds (hover / click / apply / reset)

---

### UI Polish

- Fade animations
- Pulse animations
- Hover sounds
- Apply / Reset feedback
- Keyboard shortcuts
- Animated notifications

## Level Design & World Building

- Custom landscapes
- Manual LODs (Nanite removed for performance)
- Baked static lighting (no Lumen for performance)
- Spline meshes (road, river, glass fence)
- Auto materials (snow + grass + terrain)
- Custom modeling (light roads, asphalt + fence, manhole, ladders)
- Materials (puddles, rusty metal, wet clay, sewer stone, swamp water)
- Niagara Systems (Dust, Water Drips)

### PCG Systems
- `PCG_Meadow`
- `PCG_Forest`
- `PCG_RiverBottom`
- `PCG_RuntimeGrass`

### Ambient Audio
- Birds
- Water streams
- Forest ambience
- Wolves howling
- Crickets (night levels)
- Sewer sounds

---

### Core Roles
- **GameMode** — kills, spawners, win/lose
- **GameState** — round state
- **PlayerController** — input & UI flow
- **Character** — movement & abilities
- **GameInstance** — saves & persistence

---

## Performance (Ryzen 5 5600, GTX 1660 Super 6 GB, 32 GB DDR4 RAM)

- 150–200 FPS @ FullHD (Medium/High)
- 250–300 FPS @ 1280x1024 Low
- ~2.9GB RAM usage (Standalone, Development)
- Optimized spawning & tracking logic
- Manual LODs & baked lighting, cull distances for PCG

---

## Persistence & Saves

- Cross-level inventory persistence
- Weapon restoration after level transitions
- Runtime game progress tracking
- Current run statistics
- Persistent settings
- Rebindable input mappings persistence
- Save system via GameInstance

---
