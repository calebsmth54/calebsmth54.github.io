---
layout: default
title: The Dying of the Light
modal-id: 4
categories: portfolio
date: 2019-01-28
img: DotLPreview.png
alt: The Dying of the Light Preview Image
project-date: July 2017
client: Ludum Dare 39
clientURL: https://ldjam.com/events/ludum-dare/39/the-dying-of-the-light/
category: Game Designer and Programmer
description: A project me and a group of others developed for the Ludum Dare 39 competitiontheme "Running out of Power".

---

### Let's Play by Pyc K.
<iframe src="https://www.youtube.com/embed/W37CbVgPvhA?rel=0" width="650" height="366" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Battle System

[![Event Graph](/img/LD/BP_BattleSystem0_EventGraph_Preview.PNG)](/img/LD/BP_BattleSystem0_EventGraph.PNG){:target="_blank"}

The battle system is easily the most complex script I wrote for the project. It handles numerous tasks, including setting up the visuals for the battle area (lighting, background, enemy and player), resolving player/enemy actions, and offering notifications for other scripts to poll the state of the battle. Inspired by the combat in _Superbrothers: Sword & Sorcery_, combat happens in real time. To resolve a block, the combat system checks whether the swing happened during the blocks active window. See the Action Component section below.

[Functions & Variables](/img/LD/BP_BattleSystem0_VarsFuncs.PNG){:target="_blank"} -
[Event Graph Part 2](/img/LD/BP_BattleSystem2_EventGraph2.PNG){:target="_blank"} -
[Event Graph Part 3](/img/LD/BP_BattleSystem3_EventGraph3.PNG){:target="_blank"} -
[Start Battle](/img/LD/BP_BattleSystem11_BattleSetup.PNG){:target="_blank"} -
[End Battle](/img/LD/BP_BattleSystem9_EndBattle.PNG){:target="_blank"} -
[Cache World Lighting](/img/LD/BP_BattleSystem7_CacheWorldLights.PNG){:target="_blank"} -
[Show Spotlight](/img/LD/BP_BattleSystem8_ShowSpotlight.PNG){:target="_blank"} -
[Dim World Lights](/img/LD/BP_BattleSystem12_DimWorldLights.PNG){:target="_blank"} -
[Spawn Battle Ground](/img/LD/BP_BattleSystem13_SpawnBattleGround.PNG){:target="_blank"} -
[Handle Melee Attacks Part 1](/img/LD/BP_BattleSystem15_HandleMeleeAttacks1.PNG){:target="_blank"} -
[Handle Melee Attacks Part 2](/img/LD/BP_BattleSystem16_HandleMeleeAttacks2.PNG){:target="_blank"} -
[Handle Melee Attacks Part 3](/img/LD/BP_BattleSystem18_HandleMeleeAttacks3.PNG){:target="_blank"} -
[Handle Melee Attacks Part 4](/img/LD/BP_BattleSystem19_HandleMeleeAttacks4.PNG){:target="_blank"} -
[Handle Melee Attacks Part 5](/img/LD/BP_BattleSystem20_HandleMeleeAttacks5.PNG){:target="_blank"}

	
### Player Blueprint

[![Event Graph](/img/LD/Player/BP_Player1_Preview.PNG)](/img/LD/Player/BP_Player1.PNG){:target="_blank"}

You will notice that the character has several components (Attack, Block, Heal, Quake). This are inherited from the Action Component script. More on that below.

[Components](/img/LD/Player/BP_Player2.PNG){:target="_blank"} -
[Functions](/img/LD/Player/BP_Player3.PNG){:target="_blank"} -
[Variables](/img/LD/Player/BP_Player4.PNG){:target="_blank"} -
[Event Dispatchers](/img/LD/Player/BP_Player5.PNG){:target="_blank"} -
[Graph Events](/img/LD/Player/BP_Player21.PNG){:target="_blank"} -
[Event Graph](/img/LD/Player/BP_Player7.PNG){:target="_blank"} -
[Begin Play](/img/LD/Player/BP_Player6.PNG){:target="_blank"} -
[Combat Events](/img/LD/Player/BP_Player8.PNG){:target="_blank"}

### UI Blueprints

[![Event Graph](/img/LD/Player/HUD1_Preview.PNG)](/img/LD/Player/HUD1.PNG){:target="_blank"}

This is where the meat of the player's interaction with the game takes place. The UI informs the player of their health, the enemy's health and their available actions. These buttons are updated with cooldown info after the player has used an associated action. Over the course of the game, some of the buttons are disabled as the player character loses strength.

[Functions](/img/LD/Player/HUD2.PNG){:target="_blank"} -
[Variables](/img/LD/Player/HUD3.PNG){:target="_blank"} -
[Graph Events](/img/LD/Player/HUD4.PNG){:target="_blank"} -
[Event Graph Part 1](/img/LD/Player/HUD5.PNG){:target="_blank"} -
[Event Graph Part 2](/img/LD/Player/HUD6.PNG){:target="_blank"} -
[Event Graph Part 3](/img/LD/Player/HUD7.PNG){:target="_blank"} -
[Event Graph Part 4](/img/LD/Player/HUD8.PNG){:target="_blank"}

### Action Component Blueprint

[![Event Graph](/img/LD/BP_Action1_StartAction_Preview.PNG)](/img/LD/BP_Action1_StartAction.PNG){:target="_blank"}

This class drives both player and enemy actions. It provides a simple data driven interface to tweak the length, active window and other such timing properties of an action. Using this component I was able to easily hookup player and enemy actions and their associated effects without copying a lot of code over and over. This little component turned out to be a life saver on the project, and the small amount of investment time I put into creating it paid off well.

[Functions and Variables](/img/LD/BP_Action2_VariableFunctionList.PNG){:target="_blank"} -
[Start Action](/img/LD/BP_Action1_StartAction.PNG){:target="_blank"} -
[Finish Action](/img/LD/BP_Action3_ActionFinished.PNG){:target="_blank"} -
[Can Attack](/img/LD/BP_Action4_CanAttack.PNG){:target="_blank"} -
[Is Attacking](/img/LD/BP_Action5_IsActing.PNG){:target="_blank"} -
[In Attack Window?](/img/LD/BP_Action6_IsInWindow.PNG){:target="_blank"} -
[Is Cooling Down?](/img/LD/BP_Action7_IsCoolingDown.PNG){:target="_blank"} -
[Get Time](/img/LD/BP_Action8_GetTime.PNG){:target="_blank"} -
[Get Cooldown Time](/img/LD/BP_Action9_GetCoolDownTime.PNG){:target="_blank"} -
[On Cooldown Finished](/img/LD/BP_Action10_CoolDownFinished.PNG){:target="_blank"}

### Level Editing and Scripting

By the end of the project we had a level filled with static props and other environment art with a general idea of the pathway the player would take through the world. I came in and placed all of the enemy encounters, defined the player level boundaries, scripted all of the narration and music triggers, and tweaked the level's geometry to extend gameplay for narration length and cue the player to environmental details.

[![Event Graph](/img/LD/LevelScripting1_Preview.PNG)](/img/LD/LevelScripting1.PNG){:target="_blank"}

[Choke Point to Delay Player Progression](/img/LD/LevelScripting2.PNG){:target="_blank"} -
[Narration and Level Events Part 1](/img/LD/LevelScripting3.PNG){:target="_blank"} -
[Narration and Level Events Part 2](/img/LD/LevelScripting4.PNG){:target="_blank"}
