---
layout: post
codemirror: true
title: CS111 Interactive Concept Demonstrator
description: Interactive buttons and animations showing how CS111 concepts are used in the Pirate Boss game
permalink: /CSSE/Interactive
author: Me
---

# CS111 Interactive Concept Demonstrator

Click a lesson below to see how the Pirate Boss fight actually uses each CS111 concept. Each popup is meant to help you read the level like a programmer, not just memorize a definition.

<style>
body {
  background: #000000;
  color: #ffffff;
}

.concept-btn {
  background: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
  transition: background 0.3s;
  margin: 0;
  font-weight: 600;
}

.concept-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin: 18px 0 22px;
}
.concept-btn:hover {
  background: #45a049;
}

/* Draggable Popup Styles */
.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: none;
  z-index: 1000;
}

.popup-content {
  position: absolute;
  background: #1a1a1a;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.8);
  max-width: 900px;
  max-height: 90vh;
  overflow-y: auto;
  cursor: move;
  border: 2px solid #4CAF50;
  color: #ffffff;
}

.popup-header {
  background: #4CAF50;
  color: white;
  padding: 10px 15px;
  border-radius: 6px 6px 0 0;
  cursor: move;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.popup-close {
  background: none;
  border: none;
  color: white;
  font-size: 20px;
  cursor: pointer;
  padding: 0;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.popup-body {
  padding: 20px;
  line-height: 1.6;
  color: #e0e0e0;
}

.code-snippet {
  background: #0a0a0a;
  border-left: 4px solid #4CAF50;
  padding: 10px 15px;
  margin: 10px 0;
  font-family: 'Courier New', monospace;
  font-size: 13px;
  overflow-x: auto;
  color: #66ff66;
}

.concept-highlight {
  background: #0d3d0d;
  padding: 15px;
  border-radius: 5px;
  margin: 10px 0;
  border-left: 4px solid #4CAF50;
}

.lesson-note {
  background: #1a1a1a;
  border-left: 4px solid #ff9800;
  padding: 10px 15px;
  margin: 8px 0;
  font-size: 13px;
}

h3 {
  color: #4CAF50;
}

h4 {
  color: #66ff66;
}

ul {
  color: #e0e0e0;
}

strong {
  color: #4CAF50;
}

code {
  color: #8fffa2;
}

@media (max-width: 640px) {
  .concept-btn {
    width: 100%;
    text-align: left;
  }
}

</style>

<div class="concept-grid">
  <button class="concept-btn" onclick="openPopup('oop')">Pirate Boss OOP</button>
  <button class="concept-btn" onclick="openPopup('control')">Pirate Boss Control</button>
  <button class="concept-btn" onclick="openPopup('datatypes')">Pirate Boss Data</button>
  <button class="concept-btn" onclick="openPopup('operators')">Pirate Boss Operators</button>
  <button class="concept-btn" onclick="openPopup('io')">Pirate Boss Input/Output</button>
  <button class="concept-btn" onclick="openPopup('documentation')">Pirate Boss Comments</button>
  <button class="concept-btn" onclick="openPopup('debugging')">Pirate Boss Debugging</button>
  <button class="concept-btn" onclick="openPopup('testing')">Pirate Boss Testing</button>
</div>

<!-- Popup Overlay -->
<div id="popup-overlay" class="popup-overlay" onclick="closePopup()">
  <div id="popup-content" class="popup-content" onclick="event.stopPropagation()">
    <div id="popup-header" class="popup-header">
      <h3 id="popup-title">Concept Title</h3>
      <button class="popup-close" onclick="closePopup()">×</button>
    </div>
    <div id="popup-body" class="popup-body">
      <!-- Content will be inserted here -->
    </div>
  </div>
</div>

<script>
// Draggable popup functionality
let isDragging = false;
let dragOffset = { x: 0, y: 0 };

document.addEventListener('DOMContentLoaded', function() {
  const popup = document.getElementById('popup-content');
  const header = document.getElementById('popup-header');

  header.addEventListener('mousedown', startDrag);
  document.addEventListener('mousemove', drag);
  document.addEventListener('mouseup', stopDrag);

  function startDrag(e) {
    isDragging = true;
    const rect = popup.getBoundingClientRect();
    dragOffset.x = e.clientX - rect.left;
    dragOffset.y = e.clientY - rect.top;
  }

  function drag(e) {
    if (!isDragging) return;
    const x = e.clientX - dragOffset.x;
    const y = e.clientY - dragOffset.y;
    popup.style.left = x + 'px';
    popup.style.top = y + 'px';
  }

  function stopDrag() {
    isDragging = false;
  }
});

function openPopup(concept) {
  const overlay = document.getElementById('popup-overlay');
  const title = document.getElementById('popup-title');
  const body = document.getElementById('popup-body');
  const popup = document.getElementById('popup-content');

  // Set popup content based on concept
  const content = getConceptContent(concept);
  title.textContent = content.title;
  body.innerHTML = content.body;

  // Center the popup
  popup.style.left = '50%';
  popup.style.top = '50%';
  popup.style.transform = 'translate(-50%, -50%)';

  overlay.style.display = 'block';
}

function closePopup() {
  document.getElementById('popup-overlay').style.display = 'none';
}

function getConceptContent(concept) {
  const contents = {
    oop: {
      title: 'Pirate Boss Lesson: OOP',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The Pirate Boss fight uses object-oriented programming by giving different jobs to different classes. The boss object handles boss behavior. The level object handles the battle system.
        </div>

        <h4>What to notice in the fight</h4>
        <ul>
          <li><code>BlackbreadBoss</code> owns orbiting, cannonball timing, and cannonball movement.</li>
          <li><code>GameLevelPirateBoss</code> owns battle state, health values, menu state, bullets, and the soul box.</li>
          <li>That separation makes the fight easier to read: boss logic lives in the boss class, battle logic lives in the level class.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
class BlackbreadBoss extends Character {
    constructor(data, gameEnv) {
        super(data, gameEnv);
        this.attackTimer = 0;
        this.cannonballs = [];
    }

    update() {
        this._tickCannonballs();
        this.draw();
    }
}

class GameLevelPirateBoss {
    constructor(gameEnv) {
        this.state = 'INTRO';
        this.bossHp = 250;
        this.bullets = [];
    }
}
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> OOP is not just "using classes." In this level it is how the code splits responsibility so one file can run a whole boss fight without becoming impossible to debug.
        </div>

        <p><strong>Where to look:</strong> Boss behavior is around lines 7-81. Battle setup starts around lines 85-187 in <code>assets/js/GameEnginev1.1/GameLevelPirateBossV1.js</code>.</p>
      `
    },

    control: {
      title: 'Pirate Boss Lesson: Control Flow',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The fight feels alive because control structures decide when phases change, when attacks begin, when bullets disappear, and when the turn ends.
        </div>

        <h4>What to notice in the fight</h4>
        <ul>
          <li>The boss changes phase when HP crosses 60% and 30%.</li>
          <li>Loops update every bullet every frame.</li>
          <li>Conditionals decide whether the player takes damage, whether a bullet should be removed, and whether the round returns to the menu.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
const ratio = this.bossHp / this.bossMaxHp;
const newPhase = ratio > 0.6 ? 1 : ratio > 0.3 ? 2 : 3;
if (newPhase !== this.bossPhase) {
    this.bossPhase = newPhase;
}

for (let i = this.bullets.length - 1; i >= 0; i--) {
    const b = this.bullets[i];
    b.x += b.vx;
    b.y += b.vy;
    if (b.life <= 0) {
        this.bullets.splice(i, 1);
    }
}

if (this.attackTimer >= this.attackDur) {
    this.attackActive = false;
    this.state = 'MENU';
}
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> The boss battle is really a chain of decisions. If you want to understand the level, follow the <code>if</code> statements and loops before you worry about the art or UI.
        </div>

        <p><strong>Where to look:</strong> Phase logic is around lines 287-296. Bullet updates and turn flow are around lines 395-427.</p>
      `
    },

    datatypes: {
      title: 'Pirate Boss Lesson: Data Types',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The level works because it stores battle information in the right kinds of data: numbers for timing and HP, strings for state names, arrays for projectiles, and objects for grouped values.
        </div>

        <h4>What to notice in the fight</h4>
        <ul>
          <li>Numbers track things that change every frame, like <code>bossHp</code>, <code>attackTimer</code>, and <code>soulX</code>.</li>
          <li>Strings store readable states like <code>'INTRO'</code>, <code>'MENU'</code>, and <code>'LOSE'</code>.</li>
          <li>Arrays store collections like <code>messageQueue</code>, <code>bullets</code>, and <code>cannonballs</code>.</li>
          <li>Objects keep related values together, like <code>velocity</code> and the battle <code>box</code>.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
this.state        = 'INTRO';
this.bossHp       = 250;
this.playerHp     = 100;
this.bossPhase    = 1;
this.bullets      = [];
this.messageQueue = [];
this.box = { x: 0, y: 0, w: 240, h: 200 };

this.velocity = { x: 0, y: 0 };
this.cannonballs.push({ x: bx, y: by, vx, vy, life: 140, r: 9 });
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> If the fight is doing something weird, ask which piece of data controls it. Most game bugs become easier once you know which number, boolean, array, or object is responsible.
        </div>

        <p><strong>Where to look:</strong> Core battle variables are declared around lines 93-117. Boss projectile data appears around lines 10-16 and 54-80.</p>
      `
    },

    operators: {
      title: 'Pirate Boss Lesson: Operators',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          Operators are what make the boss move in a circle, aim shots at the player, clamp the soul inside the box, and scale the difficulty across phases.
        </div>

        <h4>What to notice in the fight</h4>
        <ul>
          <li><code>+</code>, <code>-</code>, <code>*</code>, and <code>/</code> build the orbit and projectile motion.</li>
          <li><code>&lt;</code>, <code>&gt;</code>, and <code>===</code> decide when bullets expire or phases change.</li>
          <li>Ternary expressions quickly choose phase numbers, damage values, and UI colors.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
this.position.x = W / 2 + Math.cos(this.patrolAngle) * r - (this.width || 80) / 2;
this.position.y = H / 2 + Math.sin(this.patrolAngle) * r - (this.height || 100) / 2;

const dx = px - bx, dy = py - by;
const mag = Math.sqrt(dx * dx + dy * dy) || 1;
this.cannonballs.push({ x: bx, y: by, vx: dx / mag * spd, vy: dy / mag * spd, life: 140, r: 9 });

this.soulX = Math.max(box.x + 8, Math.min(box.x + box.w - 8, this.soulX));
const dmg = this.bossPhase === 3 ? 12 : this.bossPhase === 2 ? 8 : 5;
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> In a game level, operators are not abstract math practice. They are the reason the boss looks like a boss instead of a still image.
        </div>

        <p><strong>Where to look:</strong> Orbit and aiming math is around lines 23-26 and 46-54. Soul clamping and damage logic are around lines 389-410.</p>
      `
    },
    
    io: {
      title: 'Pirate Boss Lesson: Input and Output',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          This level is a great input/output lesson because it turns key presses into movement and menu choices, then turns battle state into visible output on a full-screen canvas.
        </div>

        <h4>What to notice in the fight</h4>
        <ul>
          <li>The level listens for keys like arrow keys, WASD, Enter, and Z.</li>
          <li>During the boss turn, those inputs move the blue soul around the battle box.</li>
          <li>The output is the overlay canvas: HP bars, bullets, phase labels, dialogue, and win/lose screens.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
this._keyDown = (e) => {
    this.keys[e.code] = true;
    this._handleMenuKey(e.code);
};
this._keyUp = (e) => { this.keys[e.code] = false; };
window.addEventListener('keydown', this._keyDown);
window.addEventListener('keyup', this._keyUp);

this.canvas = document.createElement('canvas');
this.canvas.style.cssText = 'position: fixed; width: 100%; height: 100%;';
document.body.appendChild(this.canvas);

if (this.keys['ArrowLeft'] || this.keys['KeyA']) this.soulX -= spd;
if (this.keys['ArrowRight'] || this.keys['KeyD']) this.soulX += spd;
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> Input/output in this fight is not a separate chapter. It is the whole conversation between the player and the level.
        </div>

        <p><strong>Where to look:</strong> Keyboard input setup is around lines 133-145. Rendering starts around lines 431-558.</p>
      `
    },

    documentation: {
      title: 'Pirate Boss Lesson: Comments and Readability',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The Pirate Boss file does not rely on big textbook definitions. Instead, it uses short comments to show the reader what each section is trying to do.
        </div>

        <h4>What to notice in the file</h4>
        <ul>
          <li>Section comments break the file into boss logic, helper logic, attack patterns, and rendering.</li>
          <li>Small comments explain intent, like why the boss orbits or why the player sprite is hidden.</li>
          <li>That makes the file easier to teach from because a reader can skim for purpose before reading syntax.</li>
        </ul>

        <h4>Code to read</h4>
        <div class="code-snippet">
// Orbit the centre of the screen
this.patrolAngle += 0.010;

// Fire cannonballs toward the player
if (this.attackTimer >= this.attackCycle) {
    this._fire();
}

// effectively hidden — battle UI takes over
SCALE_FACTOR: 999,

// phase label
const phaseLabel = this.bossPhase === 3 ? '★ PHASE III — ENRAGED' : '';
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> The best comments in a game file explain why a block exists or what the player should experience, not just repeat the code.
        </div>

        <p><strong>Where to look:</strong> Good example comments are scattered through lines 22-35, 169-180, 287-296, and 481-558.</p>
      `
    },

    debugging: {
      title: 'Pirate Boss Lesson: Debugging',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          This level is a good debugging lesson because almost every bug can be traced to a small set of state variables: phase, HP, attack timer, bullet count, and soul position.
        </div>

        <h4>Best things to debug in this fight</h4>
        <ul>
          <li>If the boss never changes behavior, inspect <code>bossHp</code> and <code>bossPhase</code>.</li>
          <li>If the soul gets stuck or escapes the box, inspect <code>soulX</code>, <code>soulY</code>, and the clamp logic.</li>
          <li>If damage feels unfair, inspect <code>invincFrames</code> and the collision radius check.</li>
        </ul>

        <h4>Useful temporary debug block</h4>
        <div class="code-snippet">
console.log({
    state: this.state,
    phase: this.bossPhase,
    playerHp: this.playerHp,
    bullets: this.bullets.length,
    attackTimer: this.attackTimer,
    soulX: this.soulX,
    soulY: this.soulY
});
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> Debugging this level works best when you watch the few variables that drive the whole fight, instead of logging everything on screen.
        </div>

        <p><strong>Where to look:</strong> Phase and battle state live around lines 93-117 and 287-296. Collision and invincibility logic are around lines 395-418.</p>
      `
    },

    testing: {
      title: 'Pirate Boss Lesson: Testing',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The Pirate Boss file does not include automated tests, so the lesson here is how to turn the real gameplay states into a clean test checklist.
        </div>

        <h4>What should be tested in this fight</h4>
        <ul>
          <li>The intro should advance into the menu instead of getting stuck.</li>
          <li>The boss should shift from Phase I to II to III at the right HP thresholds.</li>
          <li>Each attack pattern should end cleanly and return control to the menu.</li>
          <li>The player should lose HP on collision, gain temporary invincibility, and hit the lose screen at 0 HP.</li>
        </ul>

        <h4>Manual test checklist</h4>
        <div class="code-snippet">
// 1. Intro messages finish and MENU appears.
// 2. FIGHT starts a boss turn and bullets spawn.
// 3. Soul stays inside the box while moving.
// 4. Phase changes happen near 60% and 30% boss HP.
// 5. attackTimer reaches attackDur and returns to MENU.
// 6. WIN and LOSE screens both render correctly.
        </div>

        <div class="lesson-note">
          <strong>Lesson takeaway:</strong> A strong game test is just a list of important state changes you can prove are working.
        </div>

        <p><strong>Where to look:</strong> State values are initialized around lines 93-117. Turn resolution is around lines 422-427. Win/lose rendering is around lines 624-654.</p>
      `
    }
  };
  
  return contents[concept] || { title: 'Unknown Concept', body: 'Content not found.' };
}
</script>

## Check for Lessons on Other Pages

Click these links to verify lessons are available on other pages:

- [CS111 Game Runner](/CSSE111/GameRunner) - Interactive Pirate Boss game
- [CS111 Review](/CSSE/Review) - Detailed code explanations
- [Game Runner Examples](/rpg/game) - Additional game examples


```javascript
%%javascript

function toggleConcept(conceptId) {
    const content = document.getElementById(conceptId);
    if (content.style.display === 'block') {
        content.style.display = 'none';
    } else {
        // Hide all others first
        const allContents = document.querySelectorAll('.concept-content');
        allContents.forEach(el => el.style.display = 'none');
        // Show this one
        content.style.display = 'block';
    }
}

// Make sure the function is available globally
window.toggleConcept = toggleConcept;
```
