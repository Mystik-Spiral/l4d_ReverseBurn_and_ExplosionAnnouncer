### `ReverseBurn and ExplosionAnnouncer`
(l4d_ReverseBurn_and_ExplosionAnnouncer) by *_Mystik Spiral_*  

Smart reverse of burn damage from explodables (gascans, fireworks, etc.) if the victim is burned instantly and continuously.  
It was created to help mitigate the damage by griefers attempting to kill/incap their teammates by burning them.  
  
Reverses the following explodable burn types:  
Gas can, barricade gas can, fuel barrel, gas pump, and fireworks crate.  
  
Announces the following explosion types:  
Gas can, barricade gas can, fuel barrel, gas pump, fireworks crate, propane tank, and oxygen tank.  
  
  
Features:  
  
- Burn damage is reversed only if victim(s) are burned instantly (within 0.75 second of ignition) and continuously (takes burn damage more than once per second).  
- If player runs into fire more than 0.75 seconds after ignition, burn damage is treated normally.  
- When burn damage is reversed, during each burn cycle (approximately 6x per second):  
  - Attacker takes 70% damage for each instantly/continuously burned victim  
  - Standing burn victims lose 1PermHP which is converted to 2TempHP as incentive to move out of the fire quickly.  
  - Before ignition, any players already incapped or with only 1TotalHP do not take any burn damage.  
- Bots do not take burn damage but do move out of the fire as quickly as possible.  
- Griefers cannot kill or incap a victim by burning them (victims still take some damage as stated above).  
- In all other scenarios, burn damage behaves normally.  
- Option to reverse burn/blast damage if attacker is an admin.  [RBaTA_admin, default: 0/false]  
- Option to reverse blast/explosion damage.  [RBaTA_blast, default: 1/true]  
  - If both RBaEA and RBaTA plugins are loaded, RBaEA takes precedence to avoid both plugins reversing blast/explosion damage.  
- Option to ban attacker (griefer) that disconnects during reverse burn. [RBaTA_banburndisconnect, default: 1/true]  
- Option to set ban duration in minutes. [RBaTA_banduration, default: 2880 (2 days)]  
  
  
Common Scenarios:  
  
- Griefer attempts to kill the whole team by burning them.  
Usual end result: Griefer takes 210% damage (70% per victim x 3 victims) plus possible additional self-damage and everyone else takes relatively minor damage.  
  
- Player starts fire (which does not burn anyone within 0.75 seconds) and griefer runs into it.  
Usual end result: Griefer takes normal damage and player that started the fire takes no damage.  
  
 
Suggestion:  
  
To minimize griefer impact, use the ReverseBurn and ExplosionAnnouncer plugin along with...  
  
ReverseBurn and ThrowableAnnouncer (l4d_ReverseBurn_and_ThrowableAnnouncer)  
- Smart reverse of burn damage from throwables, like molotovs.  
- Option to reverse blast damage, like pipe bombs.  
  
Reverse Friendly-Fire (l4d_reverse_ff)  
- Reverse friendly-fire weapon damage.  Attacker takes damage, victim does not.  
  
When these three plugins are combined, griefers will usually get frustrated and leave since they cannot damage anyone other than themselves.  
Although griefers will take significant damage, other players may not notice any difference in game play (except laughing at stupid griefer fails).  
  
  
Credits:  

This plugin began life as **[Explosion Announcer](https://forums.alliedmods.net/showthread.php?t=328006)** by Marttt.  The original plugin kept track of explodable entities, when they were exploded, and announced who did it. I hooked on to that announcement to track whether that explodable (gascan, fireworks, etc.) instantly burned any other players, and if so, to ensure the attacker took the vast majority of the damage. If no other players are instantly burned, then burn damage is treated normally.  


Want to contribute code enhancements?  
Create a pull request using this GitHub repository:  
https://github.com/Mystik-Spiral/l4d_ReverseBurn_and_ExplosionAnnouncer  

Plugin discussion: https://forums.alliedmods.net/showthread.php?t=331164  

The phrases file (l4d_ReverseBurn_and_ExplosionAnnouncer.phrases.txt) is REQUIRED and must be copied to the "addons\sourcemod\translations" directory.
