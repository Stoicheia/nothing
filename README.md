
# Asynchronous Aseprite Importer for Mod Support

## Overview
The core goal is to extend the existing Aseprite-Unity asset pipeline so that Aseprite files can be converted to in-game animations at runtime using a standalone build of *Big Boy Boxing*.

## Project Goals

1. The importer works in a standalone build of *Big Boy Boxing* at runtime, as well as in the Unity editor.
2. After defining a link between Aseprite and the build (or the editor), animators can quickly and easily preview updates to Aseprite animations in-game.
4. The entire import process is asynchronous, in the sense that the game should run at a regular framerate during the import process.
5. The mod creation and mod loading processes are independent, but able to be seemlessly executed consecutively.
6. Mod files are converted to in-game animation data upon entering a fight, or using a console command.
7. Mod files are device-independent. That is, they can be shared between devices and platforms and represent the same in-game animation data.
8. Generated in-game animation data is stored in memory, and memory usage should be well optimised.
9. Import times should be well optimised.

## Completed Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Asynchronous Importer** |  Convert .ase files to in-game animations and metadata asynchronously at runtime. |
| **Mod Creation/Loading**  | Serialize character animation data as a .adat file, and load .adat files into the game. Saving and loading are separate processes. |

## Planned Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Refactoring, Integration, Error-handling** | Essentially, have the system be in a state that is stable, extensible, and usable by developers and players. |
| **Mod Bundles** | As a natural extension of the animation mod system, characters should be represented by a single mod file that contains animation, sound and behaviour data. A single mod file could also contain multiple characters. |
| **Adaptive Optimisation** |  Adapt the import process to different platforms and hardware specs. We aim to balance speed with asynchronicity; file size with serialization speed; memory usage with loading times, etc. |

## Proposed Future Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Online Mod Browser** | A system to upload and search characters that other people have created. |
| **Continuous Integration Pipeline** | Changes made to character data are automatically reflected on co-developers' devices, subject to some validity condition. |
| **Other** | Other cool things to do. |

## Rates and Estimations

### Main
| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** | $20/hr | 30 | $600 |
| **Completed Subtasks**  | $20/hr | 60 | $1200 |
| **Planned Subtasks**  | $20/hr | 60 | $1200 |
| **Revisions, Testing, Support** | $20/hr | 30 | $600 |
| **ChatGPT Plus Subscription**  | $20/month | - | $20 |
| **Subtotal** | - | - | **$3620** |

### Future
| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Online Mod Browser**  | $20/hr | Discuss in future | Discuss in future |
| **Continuous Integration Pipeline**  | $20/hr | Discuss in future | Discuss in future |
