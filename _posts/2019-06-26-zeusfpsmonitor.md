---
category: Template
path: '/template/zeusfpsmonitor'
title: 'Zeus FPS Monitor'
type: 'SCRIPT'

layout: default
---

## Access

Only accessable for logged admins and zeus.

![zeusfpsmonitor_white](img/zeusfpsmonitor_white.png "Zeus FPS Monitor standby")
![zeusfpsmonitor_red](img/zeusfpsmonitor_red.png "Zeus FPS Monitor signal")

## Script

The [script](https://github.com/Katalam/KAT_template/blob/master/kat_template.malden/functions/admintools/fn_initializeUI.sqf) will draw a [3D Icon](https://community.bistudio.com/wiki/drawIcon3D) with the the [mission event handler](https://community.bistudio.com/wiki/addMissionEventHandler). Every player has a variable with his fps inside. Each player has access to his fps with [diag_fps](https://community.bistudio.com/wiki/diag_fps). Because we want to have rounded number we add a [floor](https://community.bistudio.com/wiki/floor) to the output of [diag_fps](https://community.bistudio.com/wiki/diag_fps).<br/>
The [script](https://github.com/Katalam/KAT_template/blob/master/kat_template.malden/functions/admintools/fn_initializeUI.sqf) have to be as performant as possible. So we added a 3 seconds frame handler in the [initPlayerLocal.sqf](https://github.com/Katalam/KAT_template/blob/7f71140d1f323f8864e04d07abb87828672076af/kat_template.malden/initPlayerLocal.sqf#L172-L175). Now every player adds his own fps every 3 seconds in the variable.<br/>
Back to the [drawIcon3D](https://community.bistudio.com/wiki/drawIcon3D). We will now select the color based on the current fps. Under 20 fps we want to have the color red, as a signal color, and we want to increase the text size too. As the position we will take the feet of the player, so there is not a big math behind the position.<br/>
For performance we have a [distance limit](https://github.com/Katalam/KAT_template/blob/7f71140d1f323f8864e04d07abb87828672076af/kat_template.malden/functions/admintools/fn_initializeUI.sqf#L25-L27) of 1000 m from the current camera position.
