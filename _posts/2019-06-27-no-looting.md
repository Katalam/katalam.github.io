---
title: No Looting
---

## Locality

The [function](https://github.com/Katalam/KAT_template/blob/master/kat_template.malden/functions/general/fn_noLooting.sqf) is called in initServer.sqf. It adds a [mission event handler](https://community.bistudio.com/wiki/addMissionEventHandler) which is server sided (but only instance is needed).

## Script

It will remove all [magazines](https://community.bistudio.com/wiki/magazines), [items](https://community.bistudio.com/wiki/items), [assigned items](https://community.bistudio.com/wiki/assignedItems), the [binocular](https://community.bistudio.com/wiki/binocular) and all [primary weapon items](https://community.bistudio.com/wiki/primaryWeaponItems). For balacing reasons the script adds some hard coded medical material for a minimal ability to loot dead bodys.<br/>
Also all [simulated weapon holder](https://community.bistudio.com/wiki/nearestObjects) in 5&nbsp;m radius will be deleted.
