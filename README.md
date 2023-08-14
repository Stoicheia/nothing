
# Asynchronous Aseprite Importer for Mod Support

## Overview
The aim is to extend the existing Aseprite-Unity asset pipeline so that Aseprite files can be converted to in-game animations at runtime using a standalone build of *Big Boy Boxing*. The Aseprite importer consists of two principal parts: 
1. **Mod creation**: The translation of .ase file data into a usable format (mod files).
2. **Mod loading**: The conversion of the mod files to in-game animation data.

## Project Goals

1. The importer works in a standalone build of *Big Boy Boxing* at runtime, as well as in the Unity editor.
2. After defining a link between Aseprite and the build (or the editor), animators can quickly and easily preview updates to Aseprite animations in-game.
4. The entire import process is asynchronous, in the sense that the game should run at a regular framerate during the import process.
5. The mod creation and mod loading processes are independent, but able to be seemlessly executed consecutively.
6. Mod files are converted to in-game animation data upon entering a fight, or using a console command.
7. Mod files are device-independent. That is, they can be shared between devices and platforms and represent the same in-game animation data.
8. Generated in-game animation data is stored in memory, and memory usage should be well optimised.
9. Import times should be well optimised.

## Stretch Goal: Partial Importing
By updating only parts of mod files that correspond to parts of the Aseprite file that were actually updated, the mod creation process can be sped up significantly.

## Plan
### Serialization
Aseprite files will be interpreted as usable, primitive data, and serialized somewhere as a custom mod file using the binary Odin Serializer. Each mod file corresponds to the animation data of a character, and mod files are grouped into zip files corresponding to *mod packs* - one mod pack per developer.

### Asset Creation
Object that can only be created on the main thead (e.g. Texture2D) will be incrementally constructed in coroutines.

### Partial Importing

## Rates and Estimations
### Main Task
| Task  | Description | Rate | Estimated Working Days | Subtotal |
| ------------- | ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** | etc |  $9/hr |  4 (32hrs, completed) | $288 |
| **Production** | etc | $18/hr | 13 (104hrs) | $1872 |
| **ChatGPT Plus Subscription** | etc | $20/month | - | $20 |
| **Subtotal** | - | - | - | **$2190** |

### Stretch Goal
| Task  | Description | Rate | Estimated Working Days | Subtotal |
| ------------- | ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** | etc |  $9/hr | 2 (16hrs) | $144 |
| **Production** | etc | $18/hr | 5 (40hrs) | $720 |
| **Subtotal** | - | - | - | **$864** |
