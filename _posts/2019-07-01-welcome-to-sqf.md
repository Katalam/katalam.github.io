---
layout: post
title:  "Welcome to SQF!"
categories: [sqf]
---

SQF stands for **S**tatus **Q**uo **F**unction - a successor of [Status Quo Script](https://community.bistudio.com/wiki/SQS_syntax), which is deprecated since Armed Assault but could still be used in Arma 3. "Status Quo" was a code name for [Operation Flash Point](https://en.wikipedia.org/wiki/Operation_Flashpoint), just like "Combined Arms" was a code name for [Arma](https://en.wikipedia.org/wiki/Arma_(video_game_series)) and "Futura" was a code name for [Arma 3](https://en.wikipedia.org/wiki/ARMA_3). SQF was first introduced in [Operation Flashpoint: Resistance](https://community.bistudio.com/wiki/Operation_Flashpoint:_Resistance_Introduction) together with the [call](https://community.bistudio.com/wiki/call) operator in update [1.85](https://community.bistudio.com/wiki/Category:Introduced_with_Operation_Flashpoint:_Resistance_version_1.85).

Here is a example:

{% highlight sqf %}
if (isArray (_config >> "loadoutUniform")) then {
    private _loadoutUniform = getArray (_config >> "loadoutUniform");
    _unit forceAddUniform selectRandom _loadoutUniform;
};
{% endhighlight %}

And a config. GVAR() is a macro and will be explained later.

{% highlight c++ %}
class GVAR(B_empty): B_Soldier_F {
    author = "Katalam";
    displayName = "empty";
    description = "empty";
    loadout = "empty";
    loadoutGroup = ""; // CASE SENSITIVE !
    loadoutLinked[] = {"ItemMap", "ItemCompass", "ItemWatch"};
};
{% endhighlight %}
