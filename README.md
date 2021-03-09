### `ReverseBurn and ExplosionAnnouncer`
(l4d_ReverseBurn_and_ExplosionAnnouncer) by *_Mystik Spiral_* and Marttt  

Left4Dead2 SourceMod plugin reverses damage if the victim is burned instantly and continously.
It was created to help mitigate the damage by griefers attempting to kill/incap their teammates by burning them.

Reverses the following explodable burn types:
Gas can, barricade gas can, fuel barrel, gas pump, and fireworks crate.

Announces the following explosion types:
Gas can, barricade gas can, fuel barrel, gas pump, fireworks crate, propane tank, and oxygen tank.

Features:  
- Burn damage is reversed only if victim(s) are burned instantly (within 0.75 second of ignition) and continously.
- If burn victim gets out of the fire for more than a second (or fire goes out), burn damage stops being reversed.
- When burn damage is reversed, during each burn cycle (approx 6x per second):
	* Attacker takes 70% damage for each instantly/continously burned victim.
	* Standing burn victims lose 1PermHP which is converted to 2TempHP as incentive to move out of the fire quickly.
	* Already incapped burn victims or burn victims with only 1TotalHP do not take any burn damage.
- Bots do not take burn damage but do move out of the fire as quickly as possible.
- In all other scenarios, burn damage behaves normally.

Common Scenarios:  
- Griefer attempts to kill the whole team by burning them. Instead, the griefer takes 210% damage (70% per victim x 3 victims) plus possible additional self-damage.  
Usual end result: Griefer is killed or incapped and everyone else takes relatively minor damage.  

- Player starts fire and griefer runs into it.  
Usual end result: Griefer takes 100% burn damage and player that started the fire takes none, which is normal behavior.  

Suggestion:  

Use this plugin in conjunction with:  

**[ReverseBurn and ThrowableAnnouncer](https://forums.alliedmods.net/showthread.php?t=331166)** (l4d_ReverseBurn_and_ThrowableAnnouncer)  
...and...  
**[Reverse Friendly-Fire](https://forums.alliedmods.net/showthread.php?t=329035)** (l4d_reverse_ff)  

When these plugins are combined, griefers cannot inflict friendly-fire, and it minimizes damage to victims for molotov and explodable burn types (gascans, fireworks, etc.).
Although griefers will take significant damage, other players may not notice any difference in game play.

Credits:  

This plugin began life as **[Explosion Announcer](https://forums.alliedmods.net/showthread.php?t=328006)** by Marttt.  The original plugin kept track of explodable entities, when they were exploded, and announced who did it. I hooked on to that announcement to track whether that explodable (gascan, fireworks, etc.) instantly burned any other players, and if so, to ensure the attacker took the vast majority of the damage. If no other players are instantly burned, then burn damage is treated normally.  

Want to contribute code enhancements?
Create a pull request using this GitHub repository:  
https://github.com/Mystik-Spiral/l4d_ReverseBurn_and_ExplosionAnnouncer  

Plugin discussion: https://forums.alliedmods.net/showthread.php?t=331164
