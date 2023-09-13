
# Runtime Importer Documentation

## Import Codes
1:   Create mod file from source files without caching; save to persistent data path.
11:  Create mod file from source files without caching; export to external mod directory; save to persistent data path.
100: Load directly from source files.
101: Load directly from source files; save to persistent data path.
111: Load directly from source files; export to external mod directory; save to persistent data path.
200: Load from persistent data path.
210: Load from persistent data path; export to external mod directory.
301: Load from external mod directory; save to persistent data path.
999: Full process (debug)"

## Project Goals

1. The importer works in a standalone build of *Big Boy Boxing* at runtime, as well as in the Unity editor.
2. After defining a link between Aseprite and the build (or the editor), animators can quickly and easily preview updates to Aseprite animations in-game.
4. The entire import process is asynchronous, in the sense that the game should run at a regular framerate during the import process.
5. The mod creation and mod loading processes are independent, but able to be seemlessly executed consecutively.
6. Mod files are converted to in-game animation data upon entering a fight, or using a console command.
7. Mod files are device-independent. That is, they can be shared between devices and platforms and represent the same in-game animation data.
8. Generated in-game animation data is stored in memory, and memory usage should be well optimised.
9. Import times should be well optimised.

## Subtasks

The general philosophy of dividing tasks into pre-contract tasks and post-contract tasks is the following: Completed pre-contract tasks had a high degree of uncertainty, in that the technical possibilities and limitations were not well known. The project is now in a state where the core technical parts are in place, and there is a much clearer path forward for the remaining subtasks.

### Completed Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Asynchronous Importer** |  Convert .ase files to in-game animations and metadata asynchronously at runtime. |
| **Mod Creation/Loading**  | Serialize character animation data as a .adat file, and load .adat files into the game. Saving and loading are separate processes. |
| **Optimisation** | Fast and small. |

### Planned Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Refactoring, Integration, Error-handling** | Essentially, have the system be in a state that is stable, extensible, and usable by developers and players. |
| **Mod Bundles** | As a natural extension of the animation mod system, characters should be represented by a single mod file that contains animation, sound and behaviour data. A single mod file could also contain multiple characters. |
| **Adaptive Optimisation** |  Adapt the import process to different platforms and hardware specs. We aim to balance speed with asynchronicity; file size with serialization speed; memory usage with loading times, etc. |

### Proposed Future Subtasks

| Task | Aim |
| ------------- |  ------------- | 
| **Online Mod Browser** | A system to upload and search characters that other people have created. |
| **Continuous Integration Pipeline** | Changes made to character data are automatically reflected on co-developers' devices, subject to some validity condition. |
| **Other** | Other cool things to do. |

## Rates and Estimations

| Phase | Includes | Period |
| ------------- |  ------------- |  ------------- |  
| **Pre-contract** | Research and preproduction, completed subtasks | Aug 10 - Aug 29 | 
| **Post-contract + Extras**  | Planned subtasks, revisions, testing, support, future tasks | Aug 30 - ? |
### Main

| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Research and Preproduction** | $20/hr | 40 | $800 |
| **Completed Subtasks**  | $20/hr | 60 | $1200 |
| **Optimisation Bonus** | - | - | $400 |
| **Planned Subtasks**  | $20/hr | 60 | $1200 |
| **Research for Future Subtasks, Revisions, Testing, Support** | $20/hr | 40 | $800 |
| **ChatGPT Plus Subscription**  | $20/month | - | $20 |
| **Total** | - | - | **$4420** |

### Future
| Task | Rate | Estimated Working Hours | Subtotal |
| ------------- |  ------------- |  ------------- |  ------------- |
| **Online Mod Browser**  | $20/hr | Discuss in future | Discuss in future |
| **Continuous Integration Pipeline**  | $20/hr | Discuss in future | Discuss in future |
