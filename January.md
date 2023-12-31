
# Miscellaneous Tasks

## Overview
A wide range of tasks, revolving around a rough central theme of making accessing various types of data (Lua, Ase, FMOD, mods) more intuitive for designers.


## List of Tasks
### Before Writing this Document (Oct 24 - Nov 13)
| **Task** | **Description** |
| ------------- | ------------- |
| DATA Studio | The DATA Studio system, which manages save files, settings, and databases. |
| Mod Preprocessing and Custom Boss Icons | When a mod is installed, certain prerequisite animation banks and scripts are automatically loaded in via TransitionManager. These requisites can be unloaded when the mod is toggled on/off. |
| Addressables Management and Building | Addressables can be created/built automatically in-editor (e.g. _Ase/.. _Lua/.. _FMOD/..) and are correctly initialised/built when the game is built. |
| Lua Packaging | Use Regex to transpile Lua scripts, allowing for custom syntax like `$"stringLiteral {variableName}"`. Asset dependencies defined in Lua are automatically packaged into a LuaScriptAsset scriptable object and made into an addressable. Raw Lua scripts can also be used in fights, being packaged when the fight is being loaded. |
| FMOD Packaging | Similar to above, but with FMOD banks. FMODBankAssets contain bank data which can be loaded via FMOD's RuntimeManager. |
| Refactoring New-ish Plugin System | Refactored recent changes to plugin system. In particular - dealing with duplicate names, loading/unloading plugins at runtime, ensuring the LuaPluginsRepository imports at the correct times. |
| General Build Debugging | Made the NewFight scene work in the built game again to facilitate testing. |
| Obfuscator Test | Conclusion: the obfuscator does its job, but obfuscating some assemblies breaks the game. Possibly due to our use of reflection in some scripts. |
| Other Minor Tasks | Including: Making async/sync variants of various file reading/serialization functions, converting Lists to HashSets when appropriate, fixing some "smart" string processors, bland andra. |
### After Writing this Document (Nov 13 - Nov 21)
| **Task** | **Description** |
| ------------- | ------------- |
| Revisiting DATA Studio | Find and implement potential improvements to DATA Studio. Including - handling errors, smart detection of serialization method, treatment of backup files, encryption solutions, make sure compression/decompression applied only when appropriate. |
| Revisiting Pixel Perfection | See if I can mix pixel-perfect and non-pixel-perfect graphics. In particular, text should be non-pixel-perfect. |
| Revisiting Event System | Look at recent applications of Lua event system; give examples of syntax for broadcasting/listening to/modifying GameEvents. |
| Other Minor Tasks | Including: Use SafeCall in place of Call for Lua functions, identify missed merge errors, look at IOStudio briefly to assess future implementation of on-screen keyboard and touch screen support. |

## Rates
| **Task** | **Rate** | **Duration** | **Subtotal** |
| ------------- | ------------- | ------------- | ------------- |
| All Aforementioned Tasks, Revision, Support | $20/hr | Oct 24 - Nov 21 (20 working days or 160 hours) | $3200 |
| ChatGPT Subscription | $20/month | October and November | $40 |
| **Total** | - | - | **$3240** |

## Extra: GameEvent Syntax
```
-- To broadcast an event that contains special, modifiable data, use:
Player.BroadcastEvent("ON_CAST_FIREBALL", function(x) 
  local damage = x.Get("damage")
  HitEnemy(damage)
end, {
  damage = 100
})

-- To *just* broadcast an event (without anything fancy), use:
Player.InvokeByString("ON_RAISE_BANNER")

-- To change the damage of the fireball, use:
Player.Listen("ON_CAST_FIREBALL", -100, function(x)
    x.Set("damage", 1000)
end, "AmplifyFireball")
```


