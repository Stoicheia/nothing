
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

## Notes
### Asset Creation
- Objects that can only be created on the main thread (e.g. Texture2D) can be created async using one of these techniques:
  - Save png to disk, then use UnityWebRequestTexture to create texture from disk. Brief testing shows this technique is very slow, but could be optimised if we rewrite some low-level functionality.
  - Use coroutines. The number of objects processed per frame should ideally scale to guarantee a stable framerate while minimising process time.
  - Some testing has shown that png operations are very expensive, but coroutines may have weird caveats to deal with. The goal is to either optimise png encoding/decoding from disk, or to elegantly work around the limitations of coroutines.
- Load all relevant boss information (except perhaps audio) into memory at runtime, either during boss selection or during the loading screen (model after existing AseBank class (or straight up use the existing AseBank class)). The main thread should be able to play animations smoothly while loading.
- Coroutines may be used if multithreading is truly impossible.
- Look into UnityWebRequestTexture.GetTexture() (https://docs.unity3d.com/ScriptReference/Networking.UnityWebRequestTexture.GetTexture.html)

### Aseprite Workflow Optimisation
- A dirty flag on Aseprite chunks/frames could somehow be set to determine which chunks/frames to regenerate, and which ones to simply read off the old AseFile object. Dirty flagging can be simulated via other means if the Aseprite file doesn't contain such information. (e.g. simply compare subarrays)
- Some continuous integration architecture so that remote (dropbox) changes are immediately reflected in the Unity editor/in the build (not sure how hard this is).

### Serialization
- Use binary Odin Serializer to convert Aseprite files.
- Place all serialized AseFile objects into a folder.
- Compress the folder into a zip file, maybe do some extra steps to convert the zip file into a file with a custom extension?
- To deserialize, reverse this process.

### Optimisations
- Texture2D creation operations should be minimised as much as possible. All draw/combine operations should act on color arrays until the final step.
- The game should do its best to guess when to pre-load and release fighter data. Garbage collection should be called manually during non-core gameplay.


## Rates and Estimations
### Main Task
| Task | Rate | Estimated Working Days | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** |  $9/hr | 3 (24hrs, completed) | $216 |
| **Production**  | $18/hr | 14 (112hrs) | $2016 |
| **ChatGPT Plus Subscription**  | $20/month | - | $20 |
| **Subtotal**| - | - | **$2252** |

### Partial Importing
| Task  | Rate | Estimated Working Days | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** |  $9/hr | 2 (16hrs) | $144 |
| **Production** | $18/hr | 5 (40hrs) | $720 |
| **Subtotal** | - | - | **$864** |
