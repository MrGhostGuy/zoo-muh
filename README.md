# Zoo-muh

An original marble shooter built for the Rabbit R1.

Fire coloured marbles from a dusty old-school cannon at a chain emerging from a
mystical portal, and **match three** to clear it before the chain reaches the
black-void vortex.

## Controls (Rabbit R1)

| Input | Action |
|-------|--------|
| **Scroll wheel** | Aim (in the wardrobe: browse categories) |
| **Side button** | Shoot (in the wardrobe: back) |
| Long-press side | Swap marble (wardrobe: exit) |
| Tap | Swap marble / use the UI |

Desktop also supports `Space` / `Enter` to shoot, arrows to aim, `S` to swap,
`M` for music, `Esc` to title, and arrow keys to browse the wardrobe.

## Features

- 16 Zuma-style tracks (halo, horseshoe, serpentine, spiral, rose, lemniscate,
  twin loops, grand spirals...)
- Stone tunnels that hide the chain on late tracks
- Chain-reverse panic moments
- 6 powerups: bomb, lightning, reverse, accuracy, slow, score x2
- Combo chains, plus a random powerup every 5 combo steps
- Adventure, endless **Gauntlet** and one-life **Iron Frog** modes
- Procedural tribal music and classic spring-launch / marble-clack effects
- Hidden secret stage (flip the device upside-down, then click the side
  button 1-2-3)

### Sound

The audio was rebuilt for the R1's little speaker:

- **Launch** — a spring thump (230 Hz body, 660 Hz click, 1180 Hz air) plus a
  filtered noise burst, so the cannon reads as a real launcher.
- **Clack** — the satisfying ball-on-ball knock that Zuma is remembered for:
  a bright square-wave click, a wooden sine body and a noise tap, with a
  random pitch per impact so it never sounds like a machine gun.
- The clack only fires when a collision does **not** make three of a colour —
  real matches get the match sound instead.
- A master compressor stops stacked clacks and combo pops from clipping, and a
  24 ms rate limiter keeps a settling chain from re-triggering every frame.

### Difficulty

- The speed curve was re-tuned: 12.5 px/s on level 1 rising to 33.2 on level
  16, with monotonic growth and no difficulty cliff.
- Marble counts grow 38 → 230, and the colour count steps 4 → 7.
- The spawn colour picker now uses a bag system, so lucky 3-runs from the
  portal are far less common and the chain feels fairer.
- The shooter only ever offers a colour that is actually on the board (weighted
  by how many of each remain), which removes useless "dead" shots.
- Endless **Gauntlet** waves keep scaling, with a faster, denser "rush wave"
  every fifth wave.
- Every clear pays a reward chest — two on a first clear, one on a replay.
  Endless waves pay every third wave. An extra life every fourth level.

### Reward chests and cosmetics

Reward chests drop when you clear a level and open in the **Wardrobe**
(Chest icon on the title screen). Twenty unlocks across five categories, in
Common / Rare / Epic / Legendary rarities:

| Category | Common | Rare | Epic | Legendary |
|---|---|---|---|---|
| Ball Bursts | Spark Burst | Confetti Pop | Nova Flare | Quantum Nova |
| Launchers | Classic Cannon | Chrome Blaster | Neon Muzzle | Plasma Rail |
| Aiming Guides | Standard Line | Dotted Path | Tracer Beam | Laser Array |
| Shot Trails | Warm Glow | Comet Tail | Prism Wake | Void Streak |
| Frog Auras | No Aura | Frost Halo | Solar Crown | Abyss Orbit |

- Rarity odds are tuned (Common 55 / Rare 30 / Epic 12 / Legendary 3) and a
  **pity timer** guarantees you can never grind commons forever.
- Epic and Legendary reveals fire confetti and their own jingles.
- Tap an item to equip it; every cosmetic actually changes the game.
- Everything persists in `localStorage` (`z1chests`, `z1pity`, `z1own`,
  `z1eq`, `z1clr`).

## Live

https://mrghostguy.github.io/zoo-muh/

## Notes

Original art, code and audio — no copyrighted characters, levels or music.
Built by Jeff H. (Mr. Ghost).

Previously hosted at `3-of-a-kind`, which now redirects here, and before that
at `zuma-r1`, which redirects here too.
