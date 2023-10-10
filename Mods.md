
# Mod Support for Big Boy Boxing

## Overview
The goal is to create a framework to create and share mods for Big Boy Boxing. Mods may add additional characters or modify the behaviour of existing characters. Mods will be hosted on the Steam Workshop and mod.io.

## Project Goals

1. A mod's data is encoded in a single mod file, which can be loaded at runtime.
2. Mods can be created by using Aseprite for animations and a Lua text editor for behaviour. Aseprite project files, lua scripts, audio, and any additional metadata can be packed and exported to a mod file via an in-game console command.
3. The Mod system should make use of the existing ASE Studio system. The ASE Studio system should not have any dependencies on any systems created in this project.
4. A test environment will be set up during development using the mod.io API to upload/download mods hosted online.
5. The Steam Workshop is used to host mods for versions of the game hosted on steam.
6. An in-game mod browser will be used to browse mods hosted on mod.io, which is used for games hosted outside of steam (e.g. Nintendo Switch).
7. When the game is live, mod uploads and installs will be tied to a particular game-service account (e.g. Steam, Nintendo, Xbox) and authenticated when interacting with the online mod ecosystem.

### Core Subtasks (Phase 1 - Phase 2)

| Task | Aim |
| ------------- |  ------------- | 
| **Mod Bundles** | Mods are represented by a single mod file that contains animation, sound, behaviour, and metadata. These are created during runtime from pre-loaded objects via a console command and exported. |
| **Mod Browser UI** |  A UI that shows installed mods. These mods can be activated, deactivated, or uninstalled (either update during runtime, or require a refresh when activated mods change). |
| **Mod.io Integration** | The aforementioned UI should interface with a mod.io server that hosts mods uploaded by players. Mods will be downloaded directly from the mod.io website, and installed into a pre-determined mod directory from which the game will read at runtime. |
| **Test Player Authentication** | Players' installed mods will be tied to a certain game service account. Steam(?) will be used to test player authentication. |

### Extra Subtasks (Phase 3)

Steam-related activities might be better left to when we have to do Steam API work for other things, like achievements.

| Task | Aim |
| ------------- |  ------------- | 
| **Steam Stuff** | When the time is right, I will set up the game's Steam Workshop page for uploading/downloading mods via Steam. This will probably go hand-in-hand with other future Steam API related tasks, like achievements. |
| **Mod Approval Process** | Players should go through some approval process for mods. The Steam and mod.io processes will be treated separately. |
| **Educational Material** | An tutorial to teach developers and players how to upload and download mods. Most likely in both video (YouTube) and text (Github) form. |

## Rates and Estimations

| Phase | Includes | Period |
| ------------- |  ------------- |  ------------- |  
| **Phase 1** | Mod Bundling and UI | Oct 11 - Oct 18 |
| **Phase 2** | Mod.io Integration | Oct 21 - Nov 6(?) | 
| **Phase 3** | Future Stuff | ??? - ??? | 

### Phase 1
Phase 1 includes the local mod bundling system, as well as a UI to enable/disable mods.

| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Mod Bundles, Mod Browser UI**  | $20/hr | 60 (Completed) + 60 (Todo) | $2400 |
| **Revisions, Testing, Support** | $20/hr | 20 | $400 |
| **ChatGPT Plus Subscription**  | $20/month | September (Completed) | $20 |
| **Total** | - | - | **$2820** |

### Phase 2
Phase 2 consists of the mod.io integration, which includes being able to download and install mods hosted on mod.io, player authentication, UI linked to mod.io, and setting up the groundwork to integrate with Steam Workshop in the future.

| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Mod.io Integration, Authentication**  | $20/hr | 80 | $1600 |
| **Revisions, Testing, Support** | $20/hr | 20 | $400 |
| **ChatGPT Plus Subscription**  | $20/month | October | $20 |
| **Total** | - | - | **$2020** |

### Phase 3 (Future)
Phase 3 consists of Steam Workshop integration, creating mod tutorials, and consulting with modders to get the scripting workflow nailed down.

| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Steam Stuff, Mod Approval** | TBD | TBD | TBD |
| **Tutorial Production** | TBD | TBD | TBD |
| **Others** | TBD | TBD | TBD |
| **Total** | - | - | **TBD** |

### Phase 1 + Phase 2 Total
| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Mod Bundles, Mod Browser UI**  | $20/hr | 60 (Completed) + 60 (Todo) | $2400 |
| **Mod.io Integration, Authentication**  | $20/hr | 80 | $1600 |
| **Revisions, Testing, Support** | $20/hr | 20 + 20 | $800 |
| **ChatGPT Plus Subscription**  | $20/month | September and October | $40 |
| **Total** | - | - | **$4840** |

