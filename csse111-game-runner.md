---
layout: page
title: CS111 Game Runner Examples
description: Learn how to use the GameRunner and CodeRunner examples for CS111 with GameEngine.
permalink: /CSSE111/GameRunner
author: Me
---

# CS111 Game Runner Examples

This page uses the same GameRunner example structure as the existing project lesson for code and game runner integration.

## GameRunner Example

Game Runner integrates your GameEngine lesson with an interactive code editor and game output.

### Game Runner Setup

Use the following structure to define a game lesson:

- `challenge`: Describes what the student should do
- `code`: Contains the runnable GameEngine code
- `runner_id`: Unique identifier for the runner instance

### Example Runner

{% capture challenge1 %}
Run the basic game. Use WASD or arrow keys to move Chill Guy around the desert. Walk up to R2D2 to trigger an interaction!
{% endcapture %}

{% capture code1 %}
// Import for GameRunner
import GameControl from '/assets/js/GameEnginev1/essentials/GameControl.js';
// Level Code
import GameEnvBackground from '/assets/js/GameEnginev1/essentials/GameEnvBackground.js';
import Player from '/assets/js/GameEnginev1/essentials/Player.js';

class CustomLevel {
  constructor(gameEnv) {
    const path = gameEnv.path;
    const bgData = {
      name: 'custom_bg',
      src: path + '/images/gamebuilder/bg/clouds.jpg',
      pixels: { height: 720, width: 1280 }
    };
    const playerData = {
      id: 'Hero',
      src: path + '/images/gamify/chillguy.png',
      SCALE_FACTOR: 5,
      STEP_FACTOR: 1000,
      ANIMATION_RATE: 50,
      INIT_POSITION: { x: 100, y: 300 },
      pixels: { height: 512, width: 384 },
      orientation: { rows: 4, columns: 3 },
      down: { row: 0, start: 0, columns: 3 },
      right: { row: 1, start: 0, columns: 3 },
      left: { row: 2, start: 0, columns: 3 },
      up: { row: 3, start: 0, columns: 3 },
      hitbox: { widthPercentage: 0.45, heightPercentage: 0.2 },
      keypress: { up: 87, left: 65, down: 83, right: 68 }
    };

    this.classes = [
      { class: GameEnvBackground, data: bgData },
      { class: Player, data: playerData }
    ];
  }
}
export const gameLevelClasses = [CustomLevel];
export { GameControl };
{% endcapture %}

{% include runners/game.html
   runner_id="game1"
   challenge=challenge1
   code=code1
   height="400px"
%}

## CodeRunner Example

This example shows how to build a game runner lesson with one or more levels.

{% capture challenge2 %}
Run the basic game. Use WASD or arrow keys to move Chill Guy around the desert. Walk up to R2D2 to trigger an interaction!
{% endcapture %}

{% capture code2 %}
import GameControl from '/assets/js/GameEnginev1/essentials/GameControl.js';
import GameLevelWater from '/assets/js/GameEnginev1/GameLevelWater.js';
import GameLevelParallaxFish from '/assets/js/GameEnginev1/GameLevelParallaxFish.js';
export const gameLevelClasses = [GameLevelWater, GameLevelParallaxFish];
export { GameControl };
{% endcapture %}

{% include runners/game.html
   runner_id="game2"
   challenge=challenge2
   code=code2
%}

## Best Practices

### Import Structure

Always import the core GameControl module and any level classes you need.

```javascript
import GameControl from '/assets/js/GameEnginev1/essentials/GameControl.js';
import GameLevelBasic from '/assets/js/GameEnginev1/GameLevelBasic.js';
```

### Export Requirements

Your runner code must export both:

```javascript
export { GameControl };
export const gameLevelClasses = [GameLevelBasic];
```

### Level Class Structure

Each level class must define:

- Background data
- Player/character data
- NPC or enemy data
- Collectible items
- `this.classes` with all game objects

### Controls

- **WASD or Arrow Keys**: Move the player
- **Space**: Jump (if implemented)
- **E / Enter**: Interact
- **Esc**: Pause menu or exit

### Debugging

- Check the browser console for errors
- Verify import paths start with `/assets/`
- Ensure `GameControl` and `gameLevelClasses` are exported
