
# Big Boy Boxing Programming Tasks for December 5 to December 31

## Overview
Various in-person tasks centered around rewriting the gameplay scripting system (Moonsharp/Lua) to facilitate a better game design workflow.

## Summary of Tasks

| Task | Aim |
| ------------- |  ------------- | 
| **Lua-based Scene Scripting** |  Backend to create Unity scenes via Lua. Scenes are defined by a three-tier node system, consisting of a single **scene script**, containing various **entity scripts**, which contain **components**.  |
| **Nested State Machines**  | Reworked state machine system to support nested state machines. Both states and state machines inherit a common class which can be transitioned to/from, and which can receive custom callbacks. |
| **Cam2D Studio** | The game is now rendered using a layering shader, compositing 32 GameObject layers. VFX such as parallax and pixel perfection can be applied to each layer individually. Composition algorithm uses standard alpha blending for transparent objects. |
| **Lua UI Components** | CSS-style Lua scripting for constructing menus and HUDs. |
| **VFX** | DOTween based tweening through Lua for tweens; AseStudio based system for particle effects; AllInOneSpriteShader based system for controlling sprite VFX. |
| **Addressable Asset Pipeline** | Aseprite, Lua and FMOD assets can be prepackaged into addressables before the game is built. |
| **Custom Build Script** | Three presets of custom builds, depending on where content files (Ase, Lua, FMOD) should be sourced from (Raw files, addressables, both). |
| **Custom Scene Transitions** | Lua-based custom scene transition logic. |
| **Cutscenes** | Created example cutscene and menu->cutscene->fight transition logic. Individual cutscene layers can have VFX applied to them independently. |
| **New Hitbox System** | Hitboxes as Lua components. Hitboxes are independent from fight logic and receive custom callbacks through an *Event Report* object. |
| **Stage Crowd Simulation** | Randomized, parallax-layered crowd for fight stage. |
| **Challenges** | Created per-fight custom challenge system, using DATAStudio and LOCStudio to load/save challenge completion data. |
| **Gameplay Scripting** | Created example WildDude fight, HUD, and menus. To feature parity with pre-refactor Lua scripting system. |
| **General Debugging, Optimisation, Refactoring** | General debugging, optimisation, and refactoring as needed. |

## Rates and Estimations
Amounts in USD.
| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** | (By Negotiation) | (By Negotiation) | $2860 |
| **ChatGPT Plus Subscription**  | $20/month | 2 Months | $40 |
| **Total** | - | - | **$2900** |
