
# Runtime Importer Documentation

## Import Codes

| Code | Description |
| ------------- |  ------------- | 
|1|Create mod file from source files without caching; save to persistent data path.|
|11|Create mod file from source files without caching; export to external mod directory; save to persistent data path.|
|100|Load directly from source files.|
|101|Load directly from source files; save to persistent data path.|
|200|Load from persistent data path.|
|210|Load from persistent data path; export to external mod directory.|
|301|Load from external mod directory; save to persistent data path.|
|999|Full process (debug).|

## File Types

| Extension | Description |
| ------------- | ------------- | 
| .bdat | The mod file that contains all data for all characters in a bundle, including audio and plugin data. |
| .cdat | Character file that contains character animation data. |
| .pdat | For plugins. |
| *.bank* | FMOD bank file. |

## File Structure Overview

Plugin and audio files are all loaded all the time. Character files are loaded/unloaded as needed.

- Mod Bundle File
  - Character Files
     - Ase Data Bundles
        - Ase Files
  - Plugin Files
  - FMOD Files
