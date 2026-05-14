---
layout: page
title: CS111 Game Runner
permalink: /CSSE111/GameRunner
author: Me
---

# Game Runner

This page provides instructions and tools to run the Pirate Boss game and see the CS111 topics in action.

## How to Run the Game

1. **Using GameBuilder**: The primary way to run the game is through the GameBuilder interface.
   - Navigate to the GameBuilder in your development environment
   - Load the `GameLevelPirateBossV1.js` level file
   - The game will start with the pirate boss battle screen

2. **In Browser**: If running standalone:
   - Load the core engine scripts first: `GameEnv`, `GameControl`, `Character`, `Player`, etc.
   - Load `GameLevelPirateBossV1.js` as the active level
   - The game creates a canvas overlay and handles keyboard input
   - Use `Arrow` keys or `WASD` to move the soul cursor during the boss turn

3. **Key Game Features Demonstrated**:
   - **Boss AI**: Orbital movement, cannonball attacks, phase transitions
   - **Player Interaction**: HP tracking, collision detection, menu control
   - **UI Elements**: Health bars, phase status, victory/defeat popup
   - **State Management**: Intro → Menu → Boss turn → Win/Lose flow

## Interactive Demo

Below are the core game logic sections from `GameLevelPirateBossV1.js`.

<details>
<summary><strong>Boss Logic</strong></summary>

```javascript
// update() controls boss orbit and attacks
update() {
    const W = this.gameEnv.innerWidth;
    const H = this.gameEnv.innerHeight;
    this.patrolAngle += 0.010;
    const r = Math.min(W, H) * 0.28;
    this.position.x = W / 2 + Math.cos(this.patrolAngle) * r - (this.width || 80) / 2;
    this.position.y = H / 2 + Math.sin(this.patrolAngle) * r - (this.height || 100) / 2;
    this.attackTimer++;
    if (this.attackTimer >= this.attackCycle) {
        this.attackTimer = 0;
        this._fire();
    }
    this._tickCannonballs();
    this.draw();
}
```

</details>

<details>
<summary><strong>Keyboard Input</strong></summary>

```javascript
this._keyDown = (e) => {
    if (['ArrowUp','ArrowDown','ArrowLeft','ArrowRight',
         'KeyW','KeyA','KeyS','KeyD',
         'KeyZ','KeyX','Enter','Space'].includes(e.code)) {
        e.stopPropagation();
    }
    this.keys[e.code] = true;
    this._handleMenuKey(e.code);
};
window.addEventListener('keydown', this._keyDown);
window.addEventListener('keyup', this._keyUp);
```

</details>

<details>
<summary><strong>State Management</strong></summary>

```javascript
this.state = 'INTRO';
this.bossHp = 250;
this.playerHp = 100;
this.attackActive = false;

// Phase changes based on boss HP percentage
const ratio = this.bossHp / this.bossMaxHp;
const newPhase = ratio > 0.6 ? 1 : ratio > 0.3 ? 2 : 3;
if (newPhase !== this.bossPhase) {
    this.bossPhase = newPhase;
    this.messageQueue = [...msgs, ...this.messageQueue];
}
```

</details>

## Running the Full Game

To experience the complete game with all CS111 concepts:

1. Open your GameBuilder environment
2. Load the Pirate Boss level
3. Observe the inheritance hierarchy (Character → BlackbreadBoss)
4. Watch for state transitions and operator usage in real-time
5. Use browser DevTools to debug the live game (Console, Network, Sources tabs)

The game demonstrates all required CS111 competencies through interactive gameplay!
