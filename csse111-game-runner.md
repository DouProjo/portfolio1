---
layout: post
codemirror: true
title: CS111 Boss Game Runner
description: Play the CS111 boss fight on its own page with the game runner controls.
permalink: /CSSE111/GameRunner
author: Me
---

# CS111 Boss Game Runner

This page opens the boss fight on its own screen so you can focus on the battle without the lesson popups around it.

- Press `Play` to start the fight.
- Use `Enter`, `Space`, or `Z` to move through the intro text and menu.
- Use arrow keys or `WASD` during the dodge phase.

{% capture boss_runner_challenge %}
Start the boss fight and survive the attack patterns. Advance the dialogue first, then dodge during the battle turns.
{% endcapture %}

{% capture boss_runner_code %}
import GameControl from '/assets/js/GameEnginev1.1/essentials/GameControl.js';
import GameLevelPirateBoss from '/assets/js/GameEnginev1.1/GameLevelPirateBossV1.js';

export const gameLevelClasses = [GameLevelPirateBoss];
export { GameControl };
{% endcapture %}

{% include runners/game.html
   runner_id="csse111-boss-game"
   challenge=boss_runner_challenge
   code=boss_runner_code
   hide_edit="true"
   height="640px"
%}
