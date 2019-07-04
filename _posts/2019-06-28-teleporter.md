---
title: Teleporter
---

## ACE Interactions

Everything in my template is based on ACE Interactions. Quick reminder how to create one:
{% highlight sqf %}
private _action = [] call ACEFUNC(interact_menu,createAction);
["", 0, [], _action] call ACEFUNC(interact_menu,addActionToClass);
{% endhighlight %}

More information about the ACE 3 Interaction menu framework can be found [here](https://ace3mod.com/wiki/framework/interactionMenu-framework.html).

## Locality

The [function](https://github.com/Katalam/KAT_template/blob/master/kat_template.malden/functions/general/fn_createTeleporter.sqf) is called in initServer.sqf and initPlayerLocal.sqf.

All instances who are true on isServer will set up the flag texture (so in the editor you just need to name the object) and all instances who are false on hasInterface will exit after that. The ACE interactions are local, so every player needs to run the script.

## Teleport Script

The real scripting behind the teleporting can be found [here](https://github.com/Katalam/KAT_template/blob/master/kat_template.malden/functions/general/fn_teleport.sqf) and is basically just a localized setPos with the execpt that if the target is in a vehicle and the vehicle has still some room,the unit will enter the vehicle. The createTeleporter function is just for the interactions for the player.

## Player ability's

The player has the ability to teleport directly to the platoon leader or the squad leader. If he is the squad leader he will be teleported to a random group member who is not unconscious and over 500&nbsp;m away. If nobody can fit these conditions a message will appear. Platoon leader teleported is hard coded to the variable name NATO_PTL_1. Interaction point is moved down for the flag object. If another object is seleted for the teleport interaction position have to changed in order to avoid strange behaviours.
