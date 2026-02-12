# FPS Collapse

**Collapse** — одиночный FPS-проект, разработанный на **Unreal Engine 5.6** в соло. 

---

## Screenshots
![menu1](https://github.com/user-attachments/assets/b70c3031-b821-461c-ba83-dde8926f8ca6)
![gameplay2](https://github.com/user-attachments/assets/470e274f-2cd0-4b21-9c72-d7df902d8a89)
![gameplay7](https://github.com/user-attachments/assets/54b9340e-a470-423e-aa9b-fc398a8d4fed)
![gameplay10](https://github.com/user-attachments/assets/c1c3f8c6-1bf8-42ed-bda8-b9ed1f5c32b4)
![menu3](https://github.com/user-attachments/assets/3186f2dd-6d7c-4d2e-8752-f22eb84f49a6)
![animation3](https://github.com/user-attachments/assets/c7433ba0-e0d1-4a82-879d-838d080d5b86)
![gameplay12](https://github.com/user-attachments/assets/7c45f9cd-fe82-4bff-a64b-6846e82868af)
![animation4](https://github.com/user-attachments/assets/61afb606-939c-4f79-afa0-ce101e69379d)
![gameplay1](https://github.com/user-attachments/assets/216ab110-5e1a-4e72-80b4-87b3cf93b9c6)
![gameplay5](https://github.com/user-attachments/assets/7f5e9ea4-efce-4461-9e5e-55f4b0195191)
![animation1](https://github.com/user-attachments/assets/fb2617d7-669a-401b-9a54-9353e3e78851)
![menu4](https://github.com/user-attachments/assets/43fa7a92-458b-44b3-a3a0-5d3d28c361f9)
![gameplay6](https://github.com/user-attachments/assets/828f4a2e-6896-4261-8536-515eb9ec0bc3)
![gameplay11](https://github.com/user-attachments/assets/3ce92b4c-7369-496b-8870-3dd99ccd5e08)
![animation2](https://github.com/user-attachments/assets/e7b247db-5729-48c6-b900-f70471e4eadf)
![gameplay9](https://github.com/user-attachments/assets/88f46ae0-dab0-4f70-915d-cd91a1b7b2cf)
![gameplay3](https://github.com/user-attachments/assets/0c31da1b-5610-41fa-8a78-3ebe948daf8a)
![gameplay8](https://github.com/user-attachments/assets/486026d2-a946-4c33-8d9d-4a56ee90ce5a)
![menu2](https://github.com/user-attachments/assets/8a05f5fa-ca27-4660-83da-7809289a4b98)
![gameplay4](https://github.com/user-attachments/assets/5126c8ce-ae1f-412b-a3e7-012258a02730)

--- 

## Weapon System

Полноценная оружейная система с фиксированными слотами:

**Weapon Slots**
- Slot 1 — Rifle  
- Slot 2 — Pistol  
- Slot 3 — Sniper  
- Slot 4 — Shotgun  

### Основные возможности
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

Все анимации первого лица **созданы вручную в Sequencer**:

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
- Animation Notify driven footsteps (`AN_Footsteps`)
- Physical material based surface sound playback

---

## AI System

- Vision & hearing perception
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
  - `NS_Blood` (enemy / self hit)
  - `NS_Spark` (headshot / metal impact)
- Impact differentiation (enemy / environment / self)

---

## Loot & Interaction System

- Weapon pickups
- Ammo pickups
- Grenades
- First aid kits
- Water bottle pickups for stamina
- Все пикапы используют **общий Interact интерфейс**
- Drop-system с модульной логикой
- Pickup-звуки (включая падение объектов)

### Interaction Feedback
- `WBP_Take` widget
- Triggered via interaction sphere collision

---

## Round & Progression System

- Centralized round lifecycle handled by GameMode
- Enemy kill tracking
- Spawner registration & completion tracking
- Win / Lose conditions
- Portal activation after full enemy elimination
- Clean separation between level logic and game progression

---

## Movement & Mechanics

- Bunnyhop (timing-based)
- Ground friction tuning
- Air control tuning
- Sprint / Crouch modes
- Stamina system
- Water restores stamina
- Medkits restore health
- Flashlight

---

## Input System

- Enhanced Input (action-based)
- Fully rebindable controls
- Decoupled input → gameplay logic
- Clean handling of conflicting actions (reload / aim / fire / inspect)

---

## Animated HUD & UI System

### HUD
- Crosshair
- Health / Stamina prog bars (animated)
- Ammo information, First Aid kits, Water Bottles, Grenades count
- Weapon slots with highlight
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

Полноценная **Common UI** система меню:

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
- All widgets pushed to a single layout
- Reusable sub-widgets:
  - Slider
  - Option Cycle
  - Key Button
  - Menu Button
  - Option Panel
  - Confirmation Dialog
- UI sounds (hover / click / apply / reset)

---

## Level Design & World Building

- Custom landscapes
- Manual LODs (Nanite removed for performance)
- Baked static lighting (no Lumen for performance)
- Spline meshes (road)
- Auto materials (snow + grass + terrain)
- Custom modeling (light roads, asphalt + fence)

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

---

## Architecture & Engineering Focus

Проект целенаправленно строился вокруг:

- Clean architecture
- Separation of responsibilities
- Single Responsibility Principle
- OOP patterns (Template Method, Observer, Strategy)
- Maintainability > quick hacks
- Centralized round & goal management

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

- Save system via GameInstance
- Cross-level saves
- Separate save slot for settings

---

## Engineering Challenges

- Refactoring scattered gameplay logic into centralized systems
- Eliminating animation-state bugs via state-driven design
- Solving cross-level persistence via GameInstance
- Performance optimization via manual LODs and baked lighting
