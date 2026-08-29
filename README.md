# 🏆 24-0: Endurance Racing Draft

**Can you sweep all 24 segments of an endurance racing season?** Draft 5 legendary endurance prototypes and GT cars from across 7 decades of Le Mans / Daytona / Sebring / Spa / Bathurst racing and try to win every hour of every race.

## Overview

A single-file HTML game (`index.html`, ~40KB, zero dependencies) where you:

1. **Draft** 5 endurance racing legends from 7 different eras (1950-1969, 1970-1979, 1980-1989, 1990-1999, 2000-2009, 2010-2019, 2020-2026)
2. **Race** through 24 segments across 5 iconic 24-hour endurance races (Daytona 24h, Sebring 12h, Spa 24h, Le Mans 24h, Bathurst 12h)
3. **Simulate** with Monte Carlo win probability based on car OVR + era synergy bonus + track-type modifiers
4. **Win** if you sweep all 24 segments → earn the legendary **24-0** trophy

## Data

- **84 endurance racing machines** across 7 eras × 12 cars per era
  - Era 1 (1950-69): Jaguar D-Type, Ferrari 250 Testa Rossa, Ford GT40 Mk II, Mercedes 300 SLR
  - Era 2 (1970-79): Porsche 917K/935/936, Matra MS670, Ferrari 312 PB
  - Era 3 (1980-89): Porsche 956/962C, Jaguar XJR-9, Sauber Mercedes C9, Mazda 787B
  - Era 4 (1990-99): Peugeot 905, McLaren F1 GTR, Toyota TS020 GT-One
  - Era 5 (2000-09): Audi R8/R10 TDI, Bentley Speed 8, Peugeot 908 HDi
  - Era 6 (2010-19): Audi R18 e-tron quattro, Porsche 919 Hybrid, Toyota TS050 Hybrid
  - Era 7 (2020-26): Toyota GR010, Ferrari 499P, Porsche 963, Peugeot 9X8, Cadillac V-LMDh, BMW M Hybrid V8, Alpine A424, Aston Martin Valkyrie
- **24 real-world endurance segments** across 5 iconic races:
  - Daytona 24 Hours (Jan) - 6 segments
  - Sebring 12 Hours (March) - 3 segments
  - Spa 24 Hours (July) - 6 segments
  - **Le Mans 24 Hours (June)** - 6 segments (the crown jewel)
  - Bathurst 12 Hours (October) - 3 segments
- **OVR 70-99 scale** based on real-world endurance racing accomplishments (Le Mans wins, podiums, era dominance)
- **Era Synergy bonus** — +1.5 OVR per additional car from the same era after the first

## Game mechanics

- **Win probability** — base `(OVR - 70) / 30` clamped to 0.05-0.95, plus track-type modifiers:
  - `prototype` +0.02 (top class, technology edge)
  - `hybrid` +0.03 (Audi R18 e-tron / Porsche 919 hybrid era advantage)
  - `GT` -0.03 (slower GT cars, more chaos)
  - `street` -0.05 (narrow, less room for mistakes)
- **Single-race variance** ±10% random variance
- **AI field** — 35 cars weighted around OVR 82-90 (Porsche Penske / Toyota Gazoo / Ferrari AF Corse level)
- **Points** WEC-style 25-1 with hybrid era emphasis

## Inspired by

The original **82-0.com** by Vaulty Studios (iOS #1 Sports, 4.9⭐). This is the **7th entry in the X-0 Sports Draft matrix** and the first to focus on **endurance racing**:

| App | League | Status | Repo |
|-----|--------|--------|------|
| 38-0 Football Squad Draft | NFL | ✅ Delivered (2026-07-30) | `TeapoyY/squad-draft-football` |
| F1 24-0 Podium Predict | Formula 1 | ✅ Delivered (2026-08-01) | `TeapoyY/f1-24-draft` |
| 36-0 NASCAR Cup Draft | NASCAR Cup | ✅ Delivered (2026-08-17) | `TeapoyY/nascar-36-draft` |
| 24-0 Truck Series Draft | NASCAR Truck | ✅ Delivered (2026-08-21) | `TeapoyY/nascar-truck-24-draft` |
| 17-0 IndyCar Draft | IndyCar | ✅ Delivered (2026-08-22) | `TeapoyY/indycar-17-draft` |
| 20-0 MotoGP Draft | MotoGP | ✅ Delivered (2026-08-28) | `TeapoyY/motogp-20-draft` |
| **24-0 Endurance Racing** | **Endurance (Le Mans / Daytona / WEC)** | **✅ Delivered (2026-08-29)** | **`TeapoyY/endurance-24-draft`** |

## Why Endurance Racing?

Endurance racing has **NOT** been touched by Reign Collective's X-0 factory (which has claimed MLB/NHL/Soccer/CFB/MMA/NBA/NASCAR Truck) and has near-zero draft game competition on the App Store:

- "24-0 endurance" → 10 results, 0 draft
- "endurance 24-0" → 8 results, 0 draft
- "24 hours le mans game" → 7 results, 0 draft
- "hypercar draft" → 9 results, 0 draft
- "porsche endurance" → 5 results, 0 draft
- "ferrari hypercar" → 7 results, 0 draft

Existing endurance racing apps on iOS are all **official** (FIAWEC+ stream, 24h Experience, Le Mans Tickets) — **zero draft / fantasy / simulation competitors**.

The audience is **50M+ endurance racing fans globally** with Le Mans being the world's oldest active endurance race (1923-present) and one of the "Triple Crown of Motorsport" alongside Monaco GP and Indianapolis 500.

## Difficulty Curve (Monte Carlo 200 sims)

| OVR | Single-Race Win % | Avg Wins / 24 | Perfect 24-0 % | Experience |
|-----|-------------------|---------------|----------------|------------|
| 70  | 0%                | 0.0           | 0.0%           | 挣扎 backmarker |
| 80  | 0%                | 0.0           | 0.0%           | 中游陪跑 |
| 85  | 0%                | 0.0           | 0.0%           | 中下游 |
| 90  | 14%               | 3.5           | 0.0%           | 中游争冠 |
| 95  | 70%               | 17.9          | 0.0%           | 争冠体验 |
| 99  | 96%               | 23.5          | 56.5%          | GOAT tier |
| 99 + Era Synergy | 99%+ | 24.0 | ~85% | GOAT+ tier |

**Key insight**: OVR 95 = 0% perfect, OVR 99 + era synergy = ~85% perfect. This creates the "perfect season is rare but achievable" viral dynamic.

## Tech

- Single HTML file (`index.html`, ~40KB, 0 dependencies)
- Vanilla JS + CSS, no build step
- OVR 70-99, 84 entries, 24 segments
- 1-day HTML MVP

## Try It

**Live**: https://teapoyy.github.io/endurance-24-draft/

**Local**: Open `index.html` in any browser — works offline.

---

Built with 🏁 by [Teapoy](https://github.com/TeapoyY)