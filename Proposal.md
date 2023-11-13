
# Miscellaneous Tasks

## Overview
A wide range of tasks, revolving around a rough central theme of making accessing various types of data (Lua, Ase, FMOD, mods) more intuitive for designers.

## List of Tasks
| **Task** | **Description** |
|-----------|-----------------------|
| Mod Preprocessing and Custom Boss Icons | When a mod is installed, certain prerequisite animation banks and scripts are automatically loaded in via TransitionManager. These requisites can be unloaded when the mod is toggled on/off. |
| DATA Studio | The DATA Studio system, which manages save files, settings, and databases. |
| Addressables | Addressables can be created/built automatically in-editor (e.g. _Ase/.. _Lua/.. _FMOD/..) and are correctly initialised/built when the game is built. |
| Lua Packaging | Use Regex to transpile Lua scripts, allowing for custom syntax like `$"stringLiteral {variableName}"`. Asset dependencies defined in Lua are automatically packaged into a LuaScriptAsset scriptable object and made into an addressable. Raw Lua scripts can be used in fights, being packaged when the fight is being loaded. |
| FMOD Packaging | Similar to above, but with FMOD banks. FMODBankAssets contain bank data which can be loaded via FMOD's RuntimeManager. |
| Refactoring New-ish Plugin System | Refactored recent changes to plugin system. In particular - dealing with duplicate names, loading/unloading plugins at runtime, ensuring the LuaPluginsRepository imports at the correct times. |
| General Build Debugging | Made the NewFight scene work in the built game again to facilitate testing. |
| Obfuscator Test | Conclusion: the obfuscator does its job, but obfuscating some assemblies breaks the game. Possibly due to our use of reflection in some scripts. |
| Other Minor Tasks | Including: Making async/sync variants of various file reading/serialization functions, converting Lists to HashSets when appropriate, fixing some "smart" string processors, bland andra. |

