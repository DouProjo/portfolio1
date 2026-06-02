---
layout: post
title: CSSE111 Project Lesson Hub
description: Interactive mini-lessons built from the CSSE111 project objectives, evidence requirements, and assessment plan
permalink: /CSSE/Interactive
author: Me
---

<style>
body {
  background:
    radial-gradient(circle at top left, rgba(27, 111, 88, 0.16), transparent 34%),
    linear-gradient(160deg, #0f1518, #17110d 58%, #0b0f12);
  color: #f5efe4;
}

.lesson-shell {
  display: grid;
  gap: 26px;
}

.lesson-hero {
  background:
    radial-gradient(circle at top right, rgba(236, 173, 74, 0.2), transparent 35%),
    linear-gradient(145deg, rgba(15, 31, 29, 0.98), rgba(29, 20, 14, 0.98));
  border: 1px solid rgba(236, 173, 74, 0.28);
  border-radius: 26px;
  padding: 30px;
  box-shadow: 0 24px 70px rgba(0, 0, 0, 0.28);
}

.lesson-hero h1 {
  margin: 0 0 10px;
  color: #ffd27a;
  font-size: clamp(2rem, 4vw, 3.2rem);
}

.lesson-hero p {
  margin: 0;
  max-width: 74ch;
  color: #ece1d0;
  font-size: 1.05rem;
}

.lesson-callout {
  background: rgba(17, 80, 71, 0.35);
  border-left: 4px solid #50c0a7;
  border-radius: 14px;
  padding: 16px 18px;
  color: #def6ef;
}

.lesson-toolbar {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
  gap: 12px;
}

.lesson-toolbar button,
.lesson-topic button,
.lesson-popup-link {
  border: none;
  cursor: pointer;
  transition: transform 0.18s ease, filter 0.18s ease, border-color 0.18s ease;
}

.lesson-toolbar button {
  background: linear-gradient(180deg, #f0b24d, #cb8730);
  color: #17120d;
  border-radius: 18px;
  padding: 14px 16px;
  font-weight: 800;
  text-align: left;
  display: grid;
  gap: 6px;
}

.lesson-toolbar button:hover,
.lesson-topic button:hover,
.lesson-popup-link:hover {
  transform: translateY(-2px);
  filter: brightness(1.04);
}

.lesson-overview {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}

.lesson-table-wrap {
  overflow-x: auto;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 210, 122, 0.16);
  border-radius: 22px;
  padding: 14px;
}

.lesson-table {
  width: 100%;
  border-collapse: collapse;
  min-width: 920px;
}

.lesson-table th,
.lesson-table td {
  border: 1px solid rgba(255, 255, 255, 0.08);
  padding: 12px 14px;
  vertical-align: top;
  text-align: left;
}

.lesson-table th {
  background: rgba(80, 192, 167, 0.18);
  color: #ffffff;
}

.lesson-table td:first-child {
  color: #ffd27a;
  font-weight: 800;
  width: 210px;
}

.lesson-full-block {
  background: linear-gradient(180deg, rgba(20, 19, 18, 0.98), rgba(10, 11, 12, 0.96));
  border: 1px solid rgba(80, 192, 167, 0.18);
  border-radius: 22px;
  padding: 22px;
  display: grid;
  gap: 14px;
}

.lesson-full-block h2 {
  margin: 0;
  color: #8ce7d1;
  font-size: 1.45rem;
}

.lesson-full-block p,
.lesson-full-block li {
  color: #e6dac8;
}

.lesson-full-block ul {
  margin: 0;
  padding-left: 20px;
}

.lesson-toolbar button small {
  color: rgba(23, 18, 13, 0.76);
  font-size: 0.82rem;
  font-weight: 700;
}

.lesson-overview-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 210, 122, 0.16);
  border-radius: 18px;
  padding: 18px;
}

.lesson-overview-card strong {
  display: block;
  margin-bottom: 8px;
  color: #ffd27a;
}

.lesson-sections {
  display: grid;
  gap: 20px;
}

.lesson-section {
  background: linear-gradient(180deg, rgba(20, 19, 18, 0.98), rgba(10, 11, 12, 0.96));
  border: 1px solid rgba(80, 192, 167, 0.18);
  border-radius: 22px;
  padding: 22px;
  display: grid;
  gap: 16px;
}

.lesson-section-head {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: baseline;
  gap: 10px;
}

.lesson-section-head h2 {
  margin: 0;
  color: #8ce7d1;
  font-size: 1.5rem;
}

.lesson-section-head span {
  color: #ffd27a;
  font-size: 0.94rem;
}

.lesson-section p {
  margin: 0;
  color: #e6dac8;
}

.lesson-topic-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 14px;
}

.lesson-topic button {
  width: 100%;
  text-align: left;
  background: rgba(255, 255, 255, 0.035);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 18px;
  padding: 16px;
  color: inherit;
  display: grid;
  gap: 8px;
}

.lesson-topic strong {
  color: #ffffff;
  font-size: 1rem;
}

.lesson-topic em {
  color: #bfeee3;
  font-style: normal;
  font-size: 0.92rem;
}

.lesson-topic small {
  color: #c9bda9;
}

.lesson-popup-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.78);
  display: none;
  z-index: 2000;
}

.lesson-popup {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: min(940px, calc(100vw - 30px));
  max-height: 86vh;
  overflow: auto;
  background: #111516;
  border: 2px solid rgba(80, 192, 167, 0.75);
  border-radius: 22px;
  box-shadow: 0 26px 90px rgba(0, 0, 0, 0.42);
}

.lesson-popup-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  padding: 16px 18px;
  background: linear-gradient(180deg, #50c0a7, #2d8574);
  color: #08100d;
  cursor: move;
}

.lesson-popup-header h3 {
  margin: 0;
  color: inherit;
}

.lesson-popup-close {
  background: transparent;
  color: inherit;
  border: none;
  font-size: 1.4rem;
  cursor: pointer;
}

.lesson-popup-body {
  padding: 22px;
  display: grid;
  gap: 16px;
  color: #efe5d6;
}

.lesson-popup-body p,
.lesson-popup-body ul {
  margin: 0;
}

.lesson-popup-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 14px;
}

.lesson-popup-card {
  background: rgba(255, 255, 255, 0.035);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  padding: 14px;
}

.lesson-popup-card strong {
  display: block;
  margin-bottom: 8px;
  color: #ffd27a;
}

.lesson-popup-list {
  display: grid;
  gap: 12px;
}

.lesson-popup-item {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 16px;
  padding: 14px;
}

.lesson-popup-item strong {
  color: #ffffff;
}

.lesson-popup-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: fit-content;
  margin-top: 10px;
  background: linear-gradient(180deg, #f0b24d, #cb8730);
  color: #17120d;
  text-decoration: none;
  border-radius: 999px;
  padding: 10px 14px;
  font-weight: 800;
}

.lesson-checklist {
  display: grid;
  gap: 10px;
}

.lesson-checklist div {
  background: rgba(80, 192, 167, 0.08);
  border: 1px solid rgba(80, 192, 167, 0.18);
  border-radius: 14px;
  padding: 12px 14px;
}

@media (max-width: 720px) {
  .lesson-hero,
  .lesson-section {
    padding: 18px;
  }

  .lesson-toolbar button {
    width: 100%;
  }
}
</style>

<div class="lesson-shell">
  <section class="lesson-hero">
    <h1>CSSE111 Project Lesson Hub</h1>
    <p>
      This page turns the CSSE111 project requirements into teachable mini-lessons. Each section explains what students
      must build, what evidence they need, and how that work will be checked in code review, demos, or portfolio review.
    </p>
  </section>

  <div class="lesson-callout">
    The gold buttons below are the actual lessons from your rubric. Each button opens the matching learning objective,
    project evidence required, and assessment method.
  </div>

  <section class="lesson-full-block">
    <h2>Full Rubric Table</h2>
    <div class="lesson-table-wrap">
      <table class="lesson-table">
        <thead>
          <tr>
            <th>Category</th>
            <th>Learning Objective</th>
            <th>Project Evidence Required</th>
            <th>Assessment Method</th>
            <th>Example</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Writing Classes</td>
            <td>Create minimum 2 custom character classes extending base classes</td>
            <td>Code review: Player.js, NPC.js, Enemy.js</td>
            <td><pre><code>class Player extends Character { constructor(){ super(); } }</code></pre></td>
          </tr>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Methods &amp; Parameters</td>
            <td>Implement methods with parameters such as <code>collisionHandler(other, direction)</code></td>
            <td>Code review: Method signatures with 2+ parameters</td>
            <td><pre><code>function collisionHandler(other,direction){ /* ... */ }</code></pre></td>
          </tr>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Instantiation &amp; Objects</td>
            <td>Instantiate game objects in GameLevel configuration</td>
            <td>Code review: GameLevel setup objects</td>
            <td><pre><code>const player = new Player('Hero',100,200);</code></pre></td>
          </tr>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Inheritance (Basic)</td>
            <td>Create class hierarchy with 2+ levels such as GameObject to Character to Player</td>
            <td>Code review: <code>extends</code> keyword, inheritance chain</td>
            <td><pre><code>class Character extends GameObject { /* ... */ }</code></pre></td>
          </tr>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Method Overriding</td>
            <td>Override parent methods such as <code>update()</code>, <code>draw()</code>, <code>handleCollision()</code></td>
            <td>Code review: Polymorphic implementations</td>
            <td><pre><code>update(dt){ super.update(dt); /* extra */ }</code></pre></td>
          </tr>
          <tr>
            <td>Object-Oriented Programming</td>
            <td>Constructor Chaining</td>
            <td>Use <code>super()</code> to chain constructors</td>
            <td>Code review: <code>super(data, gameEnv)</code> calls</td>
            <td><pre><code>constructor(...){ super(...); }</code></pre></td>
          </tr>

          <tr>
            <td>Control Structures</td>
            <td>Iteration</td>
            <td>Use loops for game object arrays and animation frames</td>
            <td>Code review: <code>for</code>, <code>forEach</code>, <code>while</code> loops</td>
            <td></td>
          </tr>
          <tr>
            <td>Control Structures</td>
            <td>Conditionals</td>
            <td>Implement collision detection and state transitions</td>
            <td>Code review: <code>if/else</code>, nested conditions</td>
            <td></td>
          </tr>
          <tr>
            <td>Control Structures</td>
            <td>Nested Conditions</td>
            <td>Complex game logic such as power-up plus collision plus direction</td>
            <td>Code review: Multi-level conditionals</td>
            <td></td>
          </tr>

          <tr>
            <td>Data Types</td>
            <td>Numbers</td>
            <td>Position, velocity, score tracking</td>
            <td>Code review: Numeric properties</td>
            <td></td>
          </tr>
          <tr>
            <td>Data Types</td>
            <td>Strings</td>
            <td>Character names, sprite paths, game states</td>
            <td>Code review: String manipulation</td>
            <td></td>
          </tr>
          <tr>
            <td>Data Types</td>
            <td>Booleans</td>
            <td>Flags such as <code>isJumping</code>, <code>isPaused</code>, <code>isVulnerable</code></td>
            <td>Code review: Boolean logic</td>
            <td></td>
          </tr>
          <tr>
            <td>Data Types</td>
            <td>Arrays</td>
            <td>Game object collections, level data</td>
            <td>Code review: Array operations</td>
            <td></td>
          </tr>
          <tr>
            <td>Data Types</td>
            <td>Objects (JSON)</td>
            <td>Configuration objects, sprite data</td>
            <td>Code review: Object literals</td>
            <td></td>
          </tr>

          <tr>
            <td>Operators</td>
            <td>Mathematical</td>
            <td>Physics calculations such as gravity, velocity, collision</td>
            <td>Code review: <code>+</code>, <code>-</code>, <code>*</code>, <code>/</code> in physics</td>
            <td></td>
          </tr>
          <tr>
            <td>Operators</td>
            <td>String Operations</td>
            <td>Path concatenation, text display</td>
            <td>Code review: Template literals, concatenation</td>
            <td></td>
          </tr>
          <tr>
            <td>Operators</td>
            <td>Boolean Expressions</td>
            <td>Compound conditions in game logic</td>
            <td>Code review: <code>&amp;&amp;</code>, <code>||</code>, <code>!</code></td>
            <td></td>
          </tr>

          <tr>
            <td>Input/Output</td>
            <td>Keyboard Input</td>
            <td>Arrow keys, space, WASD controls using event listeners</td>
            <td>Testing: Key event handlers respond correctly</td>
            <td></td>
          </tr>
          <tr>
            <td>Input/Output</td>
            <td>Canvas Rendering</td>
            <td>Draw sprites, backgrounds, platforms using Canvas API</td>
            <td>Code review: <code>draw()</code> method implementations</td>
            <td><pre><code>ctx.fillRect(x,y,w,h);</code></pre></td>
          </tr>
          <tr>
            <td>Input/Output</td>
            <td>GameEnv Configuration</td>
            <td>Set canvas size, difficulty levels, game settings</td>
            <td>Code review: <code>GameEnv.create()</code> and <code>GameSetup.js</code></td>
            <td></td>
          </tr>
          <tr>
            <td>Input/Output</td>
            <td>API Integration</td>
            <td>Implement Leaderboard API with POST and GET scores</td>
            <td>Code review: Fetch calls with error handling</td>
            <td><pre><code>await fetch('/api/leaderboard', { method:'POST' })</code></pre></td>
          </tr>
          <tr>
            <td>Input/Output</td>
            <td>Asynchronous I/O</td>
            <td>Use <code>async/await</code> or promises for API calls</td>
            <td>Code review: <code>async/await</code> or <code>.then()</code> chains</td>
            <td><pre><code>async function load(){ const data = await fetch(url); }</code></pre></td>
          </tr>
          <tr>
            <td>Input/Output</td>
            <td>JSON Parsing</td>
            <td>Parse API responses such as leaderboard data or AI responses</td>
            <td>Code review: <code>JSON.parse()</code>, object destructuring</td>
            <td><pre><code>const data = await res.json();</code></pre></td>
          </tr>

          <tr>
            <td>Documentation</td>
            <td>Code Comments</td>
            <td>JSDoc comments for classes and methods</td>
            <td>Code review: Comment density &gt;10%</td>
            <td><pre><code>/** @param {number} dt */</code></pre></td>
          </tr>
          <tr>
            <td>Documentation</td>
            <td>Mini-Lesson Documentation</td>
            <td>Create a comic or visual post with embedded runtime game demo</td>
            <td>Portfolio review: Mini-lesson in personal portfolio</td>
            <td></td>
          </tr>
          <tr>
            <td>Documentation</td>
            <td>Code Highlights</td>
            <td>Annotate key code snippets in documentation such as OOP, APIs, and collision</td>
            <td>Portfolio review: Highlighted code examples with explanations</td>
            <td></td>
          </tr>

          <tr>
            <td>Debugging</td>
            <td>Console Debugging</td>
            <td>Use <code>console.log</code> to track game state, variables, and method calls</td>
            <td>Code review: Strategic logging in update/collision methods</td>
            <td><pre><code>console.log(player.x, player.y);</code></pre></td>
          </tr>
          <tr>
            <td>Debugging</td>
            <td>Hit Box Visualization</td>
            <td>Draw or visualize collision boundaries to refine detection</td>
            <td>Demo: Toggle hit box display, adjust collision rectangles</td>
            <td><pre><code>ctx.strokeRect(obj.x,obj.y,obj.width,obj.height);</code></pre></td>
          </tr>
          <tr>
            <td>Debugging</td>
            <td>Source-Level Debugging</td>
            <td>Set breakpoints in DevTools and step through code execution</td>
            <td>Demo: Use Sources tab to pause and inspect code flow</td>
            <td></td>
          </tr>
          <tr>
            <td>Debugging</td>
            <td>Network Debugging</td>
            <td>Examine Network tab for API calls, CORS errors, and response status</td>
            <td>Demo: Inspect fetch requests, response data, error messages</td>
            <td></td>
          </tr>
          <tr>
            <td>Debugging</td>
            <td>Application Debugging</td>
            <td>Examine cookies, localStorage, and session data for login or state issues</td>
            <td>Demo: Application tab inspection of stored data</td>
            <td></td>
          </tr>
          <tr>
            <td>Debugging</td>
            <td>Element Inspection</td>
            <td>Use Element Viewer to inspect canvas, DOM elements, and styles</td>
            <td>Demo: Inspect element properties and game object state</td>
            <td></td>
          </tr>

          <tr>
            <td>Testing &amp; Verification</td>
            <td>Gameplay Testing</td>
            <td>Test level completion, character interactions, and collision detection</td>
            <td>Live demo: Play through level without critical bugs</td>
            <td></td>
          </tr>
          <tr>
            <td>Testing &amp; Verification</td>
            <td>Integration Testing</td>
            <td>Test API integration such as Leaderboard or NPC AI with live backend</td>
            <td>Demo: Successful score saving and AI responses</td>
            <td></td>
          </tr>
          <tr>
            <td>Testing &amp; Verification</td>
            <td>API Error Handling</td>
            <td>Use <code>try/catch</code> blocks for API calls and network error handling</td>
            <td>Code review: Error handling for fetch failures</td>
            <td><pre><code>try{ await fetch(...) }catch(e){/* handle */}</code></pre></td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

  <section class="lesson-full-block">
    <h2>Example JavaScript Code for Table Subjects</h2>
    <p>Below are illustrative JavaScript code examples for the key subjects in the rubric table.</p>
  </section>

```javascript
// -------------------------
// Game model: OOP classes
// -------------------------
class GameObject {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
}

class Character extends GameObject {
  constructor(name, x, y) {
    super(x, y);
    this.name = name;
    this.health = 100;
    this.width = 32;
    this.height = 48;
  }

  update(dt) {
    // shared character behavior
  }
}

class Player extends Character {
  constructor(name, x, y, gameEnv) {
    super(name, x, y);
    this.gameEnv = gameEnv;
    this.score = 0;
    this.isJumping = false;
  }

  update(dt) {
    super.update(dt);
    this.handleInput();
  }

  handleInput() {
    // read keyboard state and move the player
  }
}

class Enemy extends Character {
  update(dt) {
    super.update(dt);
    this.patrol(dt);
  }

  patrol(dt) {
    // enemy movement logic
  }
}

function collisionHandler(actor, direction) {
  if (direction === 'left') {
    actor.health -= 10;
  }
}

// -------------------------
// Configuration and state
// -------------------------
const gameEnv = {
  width: 960,
  height: 540,
  difficulty: 'medium',
};

const player = new Player('Hero', 100, 200, gameEnv);
const enemy = new Enemy('Goblin', 400, 200);

const gameLevel = {
  objects: [player, enemy],
  settings: { difficulty: 'medium' },
};

const score = 0;
const spritePath = 'sprites/player.png';
const isPaused = false;
const levelObjects = [player, enemy];

// -------------------------
// Control structures
// -------------------------
for (const obj of gameLevel.objects) {
  obj.update(16);
}

if (!isPaused && player.health > 0) {
  player.update(16);
} else {
  console.log('Game paused or player defeated');
}

if (player.isJumping && enemy.health > 0) {
  collisionHandler(enemy, 'bottom');
}

// -------------------------
// Math and string operators
// -------------------------
const dx = player.x - enemy.x;
const dy = player.y - enemy.y;
const distance = Math.sqrt(dx * dx + dy * dy);
const titleText = `Score: ${score} / Difficulty: ${gameLevel.settings.difficulty}`;
const canMove = !isPaused && player.health > 0;

// -------------------------
// Input / output examples
// -------------------------
window.addEventListener('keydown', (event) => {
  if (event.key === 'ArrowLeft') player.x -= 4;
  if (event.key === 'ArrowRight') player.x += 4;
});

const canvas = document.querySelector('#gameCanvas');
const ctx = canvas?.getContext('2d');

function draw() {
  if (!ctx) return;
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = 'blue';
  ctx.fillRect(player.x, player.y, player.width, player.height);
}

async function postScore(scoreValue) {
  return fetch('/api/leaderboard', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ name: player.name, score: scoreValue }),
  });
}

async function fetchLeaderboard() {
  try {
    const response = await fetch('/api/leaderboard');
    return response.json();
  } catch (error) {
    console.error('API error', error);
    return [];
  }
}

// -------------------------
// Documentation and debugging
// -------------------------
/**
 * Update the player state for a single frame.
 * @param {number} dt - Time delta in milliseconds.
 */
Player.prototype.update = function (dt) {
  // Player update logic goes here.
};

console.log({ player, enemy, gameState: 'running' });

function drawHitBox(obj) {
  if (!ctx) return;
  ctx.strokeStyle = 'red';
  ctx.strokeRect(obj.x, obj.y, obj.width, obj.height);
}

debugger;

// -------------------------
// Testing examples
// -------------------------
function runGameplayTest() {
  player.x = 100;
  player.y = 200;
  draw();
  console.log('Gameplay test completed');
}

async function safeFetchScores() {
  try {
    return await fetchLeaderboard();
  } catch (error) {
    console.error('Fetch failed', error);
    return [];
  }
}
```

    <section class="lesson-full-block">
      <h2>Targeted Code Snippets</h2>
      <p>Short, focused examples for common rubric items (copy/paste into your project).</p>

  ```javascript
  // Writing classes - minimal, focused example
  class GameObject {
    constructor(x = 0, y = 0, w = 32, h = 32) {
      this.x = x; this.y = y; this.width = w; this.height = h;
    }
  }

  class Character extends GameObject {
    constructor(name, x, y) {
      super(x, y);
      this.name = name; this.health = 100;
    }
    update(dt) { /* shared behavior */ }
  }

  class Player extends Character {
    constructor(name, x, y) { super(name, x, y); this.score = 0; }
    update(dt) { super.update(dt); /* input & movement */ }
  }
  ```

  ```javascript
  // Simple AABB collision detection (used in many 2D games)
  function rectsOverlap(a, b) {
    return a.x < b.x + b.width &&
           a.x + a.width > b.x &&
           a.y < b.y + b.height &&
           a.y + a.height > b.y;
  }

  // usage
  if (rectsOverlap(player, enemy)) {
    collisionHandler(player, enemy);
  }
  ```

  ```javascript
  // Robust API call with error handling (async/await)
  async function postScore(name, score) {
    try {
      const res = await fetch('https://example.com/api/leaderboard', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ name, score })
      });
      if (!res.ok) throw new Error(`${res.status} ${res.statusText}`);
      return await res.json();
    } catch (err) {
      console.error('Leaderboard post failed', err);
      return null;
    }
  }
  ```

  ```javascript
  /**
   * Move the player by a delta.
   * @param {number} dx
   * @param {number} dy
   * @returns {void}
   */
  Player.prototype.move = function (dx, dy) {
    this.x += dx; this.y += dy;
  };
  ```

  ```javascript
  // Draw hitbox for debugging (canvas)
  function drawHitBox(ctx, obj) {
    ctx.save();
    ctx.strokeStyle = 'rgba(255,0,0,0.9)';
    ctx.lineWidth = 2;
    ctx.strokeRect(obj.x, obj.y, obj.width, obj.height);
    ctx.restore();
  }
  ```

      <h3>Further resources (working links)</h3>
      <ul>
        <li><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes" target="_blank" rel="noopener">MDN: JavaScript Classes &amp; Inheritance</a></li>
        <li><a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API" target="_blank" rel="noopener">MDN: Canvas API</a></li>
        <li><a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API" target="_blank" rel="noopener">MDN: Fetch API</a></li>
        <li><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function" target="_blank" rel="noopener">MDN: async/await</a></li>
        <li><a href="https://developer.mozilla.org/en-US/docs/Games/Techniques/2D_collision_detection" target="_blank" rel="noopener">MDN: 2D Collision Detection Techniques</a></li>
        <li><a href="https://jsdoc.app/" target="_blank" rel="noopener">JSDoc: Documentation Guide</a></li>
      </ul>

    <section class="lesson-overview">
    <div class="lesson-overview-card">
      <strong>What this page teaches</strong>
      OOP, control flow, data types, operators, input/output, APIs, documentation, debugging, testing, grading, and project pacing.
    </div>
    <div class="lesson-overview-card">
      <strong>What students should leave with</strong>
      A playable custom level, a documented portfolio post, code highlights, and proof that they can explain their implementation.
    </div>
    <div class="lesson-overview-card">
      <strong>How to use it in class</strong>
      Open a section, teach the concept, assign the build target, then verify the evidence checklist before moving on.
    </div>
    <div class="lesson-overview-card">
      <strong>Grading Scale</strong>
      A: mastery with creative implementation. B: meets all CS111 required objectives with solid understanding.
    </div>
    <div class="lesson-overview-card">
      <strong>Schedule</strong>
      Sprint 4 planning and portfolio work, Sprint 5 teaching and homework, Sprint 6 development, then final demo and N@tM showcase.
    </div>
  </section>

  <section class="lesson-full-block">
    <h2>Grading Scale</h2>
    <p><strong>A (90-100%)</strong>: Demonstrates mastery of objectives with creative implementation.</p>
    <p><strong>B (80-89%)</strong>: Meets all CS 111 required objectives with solid understanding.</p>
  </section>

  <section class="lesson-full-block">
    <h2>Required Evidence Checklist</h2>
    <ul>
      <li>2+ custom character classes extending base classes such as Character, Enemy, or NPC</li>
      <li>5+ methods with parameters and return values such as override <code>update()</code>, <code>draw()</code>, and <code>handleCollision()</code></li>
      <li>GameLevel configuration using object literals to instantiate game objects</li>
      <li>JSDoc comments on custom classes and methods with comment density greater than 10%</li>
      <li>API integration: Leaderboard POST/GET scores plus NPC AI interaction with error handling</li>
      <li>Debugging competency: use DevTools such as Console, Network, Application, and Sources to debug game logic, APIs, and login/state</li>
      <li>Mini-lesson documentation in personal portfolio with comic or visual style and embedded runtime demo</li>
      <li>Code highlights showing OOP hierarchy, API calls, collision logic, and state management</li>
      <li>Complete playable custom level tested in GameBuilder and team repository</li>
    </ul>
  </section>

  <section class="lesson-full-block">
    <h2>Schedule</h2>
    <p><strong>The Final Project will be completed in the last sprint.</strong></p>
    <p><strong>CSSE 1 (Trimester 1, Weeks 1-12, Sprints 1-3)</strong></p>
    <ul>
      <li>Fundamental learning and Engineering Practices</li>
      <li>All classroom prototype game due at the end of week 12</li>
    </ul>
    <p><strong>CSSE 2 (Trimester 2, Weeks 13-24, Sprints 4-6)</strong></p>
    <p><strong>Project Planning (Weeks 13-16, Sprint 4)</strong></p>
    <ul>
      <li>During the planning weeks, build individual and group skills</li>
      <li>Individual Portfolio: create a comic or visual style blog post in your personal portfolio using GameRunner notebook</li>
      <li>Embed a runtime demo of your game feature</li>
      <li>Highlight and explain key code pieces such as classes, methods, and APIs</li>
      <li>Demonstrate your expertise area with annotated examples</li>
      <li>Mini-Lesson: develop instruction on how to enhance the game</li>
      <li>Create a lesson to teach group-level expertise topics in groups of 3</li>
      <li>Submit PRs for instructional level(s) and notebooks/posts</li>
    </ul>
    <p><strong>Project Teaching/Homework (Weeks 17-18, Sprint 5)</strong></p>
    <ul>
      <li>Individual portfolio due at the beginning of Sprint 5</li>
      <li>Project expertise, plans, code, and retrospective memories/help system</li>
      <li>Blogs on homework created and technical topics learned</li>
      <li>Group Teaching/Demonstration</li>
      <li>Teach lesson on expertise topics in groups of 3</li>
      <li>Assign homework for students to add expertise topics to their game</li>
      <li>Grade student homework</li>
    </ul>
    <p><strong>Project Development (Weeks 19-24, Sprint 6)</strong></p>
    <ul>
      <li>Set and achieve at least one milestone per sprint</li>
      <li>Continue the iterative cycle of development</li>
      <li>Integrate features into your team’s custom game</li>
    </ul>
    <p><strong>Finals Week -1</strong></p>
    <ul>
      <li>Wednesday: Demo your team’s custom level to the teacher</li>
      <li>Thursday: N@tM (Night at the Museum) showcase at 6pm</li>
    </ul>
  </section>

  <div id="lesson-toolbar" class="lesson-toolbar"></div>
  <div id="lesson-sections" class="lesson-sections"></div>
</div>

<div id="lesson-popup-overlay" class="lesson-popup-overlay" onclick="window.closeLessonPopup && window.closeLessonPopup()">
  <div id="lesson-popup" class="lesson-popup" onclick="event.stopPropagation()">
    <div id="lesson-popup-header" class="lesson-popup-header">
      <h3 id="lesson-popup-title">Lesson</h3>
      <button class="lesson-popup-close" onclick="window.closeLessonPopup && window.closeLessonPopup()">×</button>
    </div>
    <div id="lesson-popup-body" class="lesson-popup-body"></div>
  </div>
</div>

<script>
const lessonSections = [
  {
    id: 'oop',
    title: 'Object-Oriented Programming',
    intro: 'These lessons focus on classes, inheritance, object creation, and overridden behavior.',
    topics: [
      {
        id: 'writing-classes',
        title: 'Writing Classes',
        summary: 'Create minimum 2 custom character classes extending base classes.',
        objective: 'Create minimum 2 custom character classes extending base classes.',
        evidence: 'Create minimum 2 custom character classes extending base classes.',
        assessment: 'Code review: Player.js, NPC.js, Enemy.js',
        build: 'Build at least two custom character classes with their own role in the game.',
        checks: [
          'Two or more custom classes exist.',
          'Classes extend base classes.',
          'Each class has its own behavior or properties.'
        ]
      },
      {
        id: 'methods-parameters',
        title: 'Methods & Parameters',
        summary: 'Implement methods with parameters such as collisionHandler(other, direction).',
        objective: 'Implement methods with parameters such as collisionHandler(other, direction).',
        evidence: 'Implement methods with parameters.',
        assessment: 'Code review: Method signatures with 2+ parameters',
        build: 'Write methods that use parameters to react to gameplay context.',
        checks: [
          'Methods accept meaningful parameters.',
          'Parameters affect behavior.',
          'Methods are easy to review.'
        ]
      },
      {
        id: 'instantiation-objects',
        title: 'Instantiation & Objects',
        summary: 'Instantiate game objects in GameLevel configuration.',
        objective: 'Instantiate game objects in GameLevel configuration.',
        evidence: 'Instantiate game objects in GameLevel configuration.',
        assessment: 'Code review: GameLevel setup objects',
        build: 'Use configuration objects to instantiate real game objects.',
        checks: [
          'GameLevel creates objects from config.',
          'Object literals are used clearly.',
          'Setup is readable.'
        ]
      },
      {
        id: 'inheritance-basic',
        title: 'Inheritance (Basic)',
        summary: 'Create class hierarchy with 2+ levels such as GameObject to Character to Player.',
        objective: 'Create class hierarchy with 2+ levels such as GameObject to Character to Player.',
        evidence: 'Create class hierarchy with 2+ levels.',
        assessment: 'Code review: extends keyword, inheritance chain',
        build: 'Build a class hierarchy that clearly shows parent-child relationships.',
        checks: [
          'Uses extends correctly.',
          'Hierarchy has 2 or more levels.',
          'Inheritance chain is easy to explain.'
        ]
      },
      {
        id: 'method-overriding',
        title: 'Method Overriding',
        summary: 'Override parent methods such as update(), draw(), and handleCollision().',
        objective: 'Override parent methods such as update(), draw(), and handleCollision().',
        evidence: 'Override parent methods.',
        assessment: 'Code review: Polymorphic implementations',
        build: 'Override parent methods so subclasses behave differently at runtime.',
        checks: [
          'A parent method is overridden.',
          'The override changes runtime behavior.',
          'Parent and child behavior are both clear.'
        ]
      },
      {
        id: 'constructor-chaining',
        title: 'Constructor Chaining',
        summary: 'Use super() to chain constructors.',
        objective: 'Use super() to chain constructors.',
        evidence: 'Use super() to chain constructors.',
        assessment: 'Code review: super(data, gameEnv) calls',
        build: 'Use constructor chaining so inherited setup happens before subclass setup.',
        checks: [
          'super() is called correctly.',
          'Parent setup happens first.',
          'Subclass properties are added after.'
        ]
      }
    ]
  },
  {
    id: 'control',
    title: 'Control Structures',
    intro: 'These lessons focus on loops, conditions, and more complex game logic.',
    topics: [
      {
        id: 'iteration',
        title: 'Iteration',
        summary: 'Use loops for game object arrays and animation frames.',
        objective: 'Use loops for game object arrays and animation frames.',
        evidence: 'Use loops for game object arrays and animation frames.',
        assessment: 'Code review: for, forEach, while loops',
        build: 'Use loops to update objects, frames, or repeated gameplay actions.',
        checks: [
          'A real loop structure is used.',
          'Loop updates gameplay data.',
          'Repeated work is not copied manually.'
        ]
      },
      {
        id: 'conditionals',
        title: 'Conditionals',
        summary: 'Implement collision detection and state transitions.',
        objective: 'Implement collision detection and state transitions.',
        evidence: 'Implement collision detection and state transitions.',
        assessment: 'Code review: if/else, nested conditions',
        build: 'Use conditional logic to control collisions and state changes.',
        checks: [
          'if/else logic is present.',
          'Conditions match gameplay rules.',
          'State changes are reviewable.'
        ]
      },
      {
        id: 'nested-conditions',
        title: 'Nested Conditions',
        summary: 'Build complex game logic such as power-up plus collision plus direction.',
        objective: 'Build complex game logic such as power-up plus collision plus direction.',
        evidence: 'Complex game logic with nested conditions.',
        assessment: 'Code review: Multi-level conditionals',
        build: 'Combine multiple checks when one game action depends on several factors.',
        checks: [
          'More than one condition level is used.',
          'Condition order makes sense.',
          'Students can explain each layer.'
        ]
      }
    ]
  },
  {
    id: 'data',
    title: 'Data Types',
    intro: 'These lessons focus on the specific data types that store game state and configuration.',
    topics: [
      {
        id: 'numbers',
        title: 'Numbers',
        summary: 'Track position, velocity, and score with numbers.',
        objective: 'Use numbers for position, velocity, and score tracking.',
        evidence: 'Position, velocity, score tracking.',
        assessment: 'Code review: Numeric properties',
        build: 'Use numbers for movement, timing, score, or other changing values.',
        checks: [
          'Numbers store gameplay values.',
          'Numeric state changes during play.',
          'Values are easy to identify.'
        ]
      },
      {
        id: 'strings',
        title: 'Strings',
        summary: 'Use strings for character names, sprite paths, and game states.',
        objective: 'Use strings for character names, sprite paths, and game states.',
        evidence: 'Character names, sprite paths, game states.',
        assessment: 'Code review: String manipulation',
        build: 'Use strings for labels, states, file paths, or displayed text.',
        checks: [
          'Strings are used intentionally.',
          'Labels or state names are readable.',
          'String values support gameplay or UI.'
        ]
      },
      {
        id: 'booleans',
        title: 'Booleans',
        summary: 'Use flags such as isJumping, isPaused, or isVulnerable.',
        objective: 'Use flags such as isJumping, isPaused, or isVulnerable.',
        evidence: 'Flags like isJumping, isPaused, isVulnerable.',
        assessment: 'Code review: Boolean logic',
        build: 'Use true or false flags to manage gameplay state.',
        checks: [
          'Flags are clearly named.',
          'Booleans control real decisions.',
          'True/false state is meaningful.'
        ]
      },
      {
        id: 'arrays',
        title: 'Arrays',
        summary: 'Use arrays for game object collections and level data.',
        objective: 'Use arrays for game object collections and level data.',
        evidence: 'Game object collections, level data.',
        assessment: 'Code review: Array operations',
        build: 'Store and update collections of objects or level values in arrays.',
        checks: [
          'Arrays hold related data.',
          'Array operations are used.',
          'Arrays support gameplay.'
        ]
      },
      {
        id: 'objects-json',
        title: 'Objects (JSON)',
        summary: 'Use configuration objects and sprite data.',
        objective: 'Use configuration objects and sprite data.',
        evidence: 'Configuration objects, sprite data.',
        assessment: 'Code review: Object literals',
        build: 'Group related settings into object literals or JSON-like data.',
        checks: [
          'Object literals are used.',
          'Related data is grouped well.',
          'Configuration stays readable.'
        ]
      }
    ]
  },
  {
    id: 'operators',
    title: 'Operators',
    intro: 'These lessons focus on arithmetic, text building, and compound logic.',
    topics: [
      {
        id: 'mathematical',
        title: 'Mathematical',
        summary: 'Use operators for gravity, velocity, and collision math.',
        objective: 'Use mathematical operators for gravity, velocity, and collision.',
        evidence: 'Physics calculations such as gravity, velocity, collision.',
        assessment: 'Code review: +, -, *, / in physics',
        build: 'Use arithmetic operators in movement, collision, or physics logic.',
        checks: [
          'Math operators appear in gameplay code.',
          'Calculations affect runtime behavior.',
          'Expressions are understandable.'
        ]
      },
      {
        id: 'string-operations',
        title: 'String Operations',
        summary: 'Use concatenation or template literals for paths and text display.',
        objective: 'Use string operations for path concatenation and text display.',
        evidence: 'Path concatenation, text display.',
        assessment: 'Code review: Template literals, concatenation',
        build: 'Generate readable text, labels, or paths with string operations.',
        checks: [
          'Uses template literals or concatenation.',
          'Text output is readable.',
          'String building is intentional.'
        ]
      },
      {
        id: 'boolean-expressions',
        title: 'Boolean Expressions',
        summary: 'Use compound conditions in game logic.',
        objective: 'Use compound conditions in game logic.',
        evidence: 'Compound conditions in game logic.',
        assessment: 'Code review: &&, ||, !',
        build: 'Combine multiple checks into a single gameplay condition.',
        checks: [
          'Uses &&, ||, or !.',
          'Compound logic is correct.',
          'Conditions match intended behavior.'
        ]
      }
    ]
  },
  {
    id: 'io',
    title: 'Input/Output',
    intro: 'These lessons cover controls, rendering, environment setup, and API communication.',
    topics: [
      {
        id: 'keyboard-input',
        title: 'Keyboard Input',
        summary: 'Use arrow keys, space, or WASD controls with event listeners.',
        objective: 'Use arrow keys, space, or WASD controls with event listeners.',
        evidence: 'Arrow keys, space, WASD controls using event listeners.',
        assessment: 'Testing: Key event handlers respond correctly',
        build: 'Turn keyboard input into movement or gameplay actions.',
        checks: [
          'Key events are captured.',
          'Input changes the game.',
          'Controls respond correctly.'
        ]
      },
      {
        id: 'canvas-rendering',
        title: 'Canvas Rendering',
        summary: 'Draw sprites, backgrounds, and platforms using Canvas API.',
        objective: 'Draw sprites, backgrounds, and platforms using Canvas API.',
        evidence: 'Draw sprites, backgrounds, platforms using Canvas API.',
        assessment: 'Code review: draw() method implementations',
        build: 'Render visible objects and scenes with Canvas API methods.',
        checks: [
          'Canvas output is visible.',
          'draw() methods exist.',
          'Rendering changes with state.'
        ]
      },
      {
        id: 'gameenv-configuration',
        title: 'GameEnv Configuration',
        summary: 'Set canvas size, difficulty levels, and game settings.',
        objective: 'Set canvas size, difficulty levels, and game settings.',
        evidence: 'Set canvas size, difficulty levels, game settings.',
        assessment: 'Code review: GameEnv.create() and GameSetup.js',
        build: 'Centralize game environment settings so they are easy to update.',
        checks: [
          'Configuration is explicit.',
          'Settings affect gameplay.',
          'Setup is easy to review.'
        ]
      },
      {
        id: 'api-integration',
        title: 'API Integration',
        summary: 'Implement Leaderboard API requests with POST and GET.',
        objective: 'Implement Leaderboard API requests with POST and GET.',
        evidence: 'Implement Leaderboard API (POST/GET scores).',
        assessment: 'Code review: Fetch calls with error handling',
        build: 'Connect the game to a leaderboard or other live API endpoint.',
        checks: [
          'Uses fetch requests.',
          'GET or POST behavior works.',
          'Error handling is included.'
        ]
      },
      {
        id: 'asynchronous-io',
        title: 'Asynchronous I/O',
        summary: 'Use async/await or promises for API calls.',
        objective: 'Use async/await or promises for API calls.',
        evidence: 'Use async/await or promises for API calls.',
        assessment: 'Code review: async/await or .then() chains',
        build: 'Handle network requests asynchronously in a clear way.',
        checks: [
          'Uses async/await or promises.',
          'Waits for responses correctly.',
          'Async flow is understandable.'
        ]
      },
      {
        id: 'json-parsing',
        title: 'JSON Parsing',
        summary: 'Parse API responses such as leaderboard data or AI responses.',
        objective: 'Parse API responses such as leaderboard data or AI responses.',
        evidence: 'Parse API responses such as leaderboard data or AI responses.',
        assessment: 'Code review: JSON.parse(), object destructuring',
        build: 'Parse returned JSON and use it in the game or UI.',
        checks: [
          'Response data is parsed.',
          'Parsed values are used.',
          'JSON handling is reviewable.'
        ]
      }
    ]
  },
  {
    id: 'documentation',
    title: 'Documentation',
    intro: 'These lessons focus on code comments, mini-lessons, and annotated examples.',
    topics: [
      {
        id: 'code-comments',
        title: 'Code Comments',
        summary: 'Use JSDoc comments for classes and methods.',
        objective: 'Use JSDoc comments for classes and methods.',
        evidence: 'JSDoc comments for classes and methods.',
        assessment: 'Code review: Comment density >10%',
        build: 'Document classes and methods so another student can understand them quickly.',
        checks: [
          'JSDoc comments are present.',
          'Comment density is strong.',
          'Comments help readability.'
        ]
      },
      {
        id: 'mini-lesson-documentation',
        title: 'Mini-Lesson Documentation',
        summary: 'Create a comic or visual post with embedded runtime game demo.',
        objective: 'Create a comic or visual post with embedded runtime game demo.',
        evidence: 'Create comic or visual post with embedded runtime game demo.',
        assessment: 'Portfolio review: Mini-lesson in personal portfolio',
        build: 'Create a published mini-lesson that teaches the feature and shows it running.',
        checks: [
          'Includes a runtime demo.',
          'Uses a comic or visual format.',
          'Teaches a specific topic.'
        ]
      },
      {
        id: 'code-highlights',
        title: 'Code Highlights',
        summary: 'Annotate key code snippets in documentation such as OOP, APIs, and collision.',
        objective: 'Annotate key code snippets in documentation such as OOP, APIs, and collision.',
        evidence: 'Annotate key code snippets in documentation.',
        assessment: 'Portfolio review: Highlighted code examples with explanations',
        build: 'Pick important snippets and explain what each one proves.',
        checks: [
          'Important snippets are included.',
          'Annotations explain significance.',
          'Examples match the lesson topic.'
        ]
      }
    ]
  },
  {
    id: 'debugging',
    title: 'Debugging',
    intro: 'These lessons focus on console work, DevTools, storage, and element inspection.',
    topics: [
      {
        id: 'console-debugging',
        title: 'Console Debugging',
        summary: 'Use console.log to track game state, variables, and method calls.',
        objective: 'Use console.log to track game state, variables, and method calls.',
        evidence: 'Strategic logging in update/collision methods.',
        assessment: 'Code review: Strategic logging in update/collision methods',
        build: 'Add focused logs that help explain runtime behavior.',
        checks: [
          'Logs are strategic.',
          'Logs reveal state changes.',
          'Logs help explain bugs.'
        ]
      },
      {
        id: 'hit-box-visualization',
        title: 'Hit Box Visualization',
        summary: 'Draw or visualize collision boundaries to refine detection.',
        objective: 'Draw or visualize collision boundaries to refine detection.',
        evidence: 'Draw or visualize collision boundaries to refine detection.',
        assessment: 'Demo: Toggle hit box display, adjust collision rectangles',
        build: 'Render temporary hit boxes or collision rectangles during testing.',
        checks: [
          'Collision bounds can be seen.',
          'Visualization helps tuning.',
          'Students can explain what they see.'
        ]
      },
      {
        id: 'source-level-debugging',
        title: 'Source-Level Debugging',
        summary: 'Set breakpoints in DevTools and step through code execution.',
        objective: 'Set breakpoints in DevTools and step through code execution.',
        evidence: 'Set breakpoints in DevTools, step through code execution.',
        assessment: 'Demo: Use Sources tab to pause and inspect code flow',
        build: 'Pause code during runtime and inspect the current values and flow.',
        checks: [
          'Breakpoints are used.',
          'Execution is stepped through.',
          'Code flow can be explained.'
        ]
      },
      {
        id: 'network-debugging',
        title: 'Network Debugging',
        summary: 'Examine the Network tab for API calls, CORS errors, and response status.',
        objective: 'Examine the Network tab for API calls, CORS errors, and response status.',
        evidence: 'Inspect fetch requests, response data, error messages.',
        assessment: 'Demo: Inspect fetch requests, response data, error messages',
        build: 'Use the Network tab to inspect live backend communication.',
        checks: [
          'Requests are visible in Network.',
          'Statuses and errors are readable.',
          'Students can explain the results.'
        ]
      },
      {
        id: 'application-debugging',
        title: 'Application Debugging',
        summary: 'Examine cookies, localStorage, and session data for login or state issues.',
        objective: 'Examine cookies, localStorage, and session data for login or state issues.',
        evidence: 'Examine cookies, localStorage, session data for login/state.',
        assessment: 'Demo: Application tab inspection of stored data',
        build: 'Inspect stored browser data that affects login, saves, or state.',
        checks: [
          'Stored data is visible.',
          'Application tab is used correctly.',
          'Storage inspection supports debugging.'
        ]
      },
      {
        id: 'element-inspection',
        title: 'Element Inspection',
        summary: 'Use the Element Viewer to inspect canvas, DOM elements, and styles.',
        objective: 'Use the Element Viewer to inspect canvas, DOM elements, and styles.',
        evidence: 'Inspect canvas, DOM elements, styles.',
        assessment: 'Demo: Inspect element properties and game object state',
        build: 'Inspect page elements or canvas layers while debugging layout or rendering.',
        checks: [
          'Elements can be inspected.',
          'Canvas or DOM state is visible.',
          'Inspection connects to a real bug.'
        ]
      }
    ]
  },
  {
    id: 'verification',
    title: 'Testing & Verification',
    intro: 'These lessons focus on proving gameplay, integration, and network safety.',
    topics: [
      {
        id: 'gameplay-testing',
        title: 'Gameplay Testing',
        summary: 'Test level completion, character interactions, and collision detection.',
        objective: 'Test level completion, character interactions, and collision detection.',
        evidence: 'Test level completion, character interactions, collision detection.',
        assessment: 'Live demo: Play through level without critical bugs',
        build: 'Play through the level and verify the core mechanics hold up.',
        checks: [
          'The level is playable.',
          'Core interactions work.',
          'Critical bugs are absent.'
        ]
      },
      {
        id: 'integration-testing',
        title: 'Integration Testing',
        summary: 'Test Leaderboard or NPC AI integration with the live backend.',
        objective: 'Test Leaderboard or NPC AI integration with the live backend.',
        evidence: 'Test API integration with live backend.',
        assessment: 'Demo: Successful score saving and AI responses',
        build: 'Verify that live backend-connected features work end to end.',
        checks: [
          'Backend requests succeed.',
          'Integrated features work live.',
          'Results can be demonstrated.'
        ]
      },
      {
        id: 'api-error-handling',
        title: 'API Error Handling',
        summary: 'Use try/catch blocks for API calls and network error handling.',
        objective: 'Use try/catch blocks for API calls and network error handling.',
        evidence: 'Try/catch blocks for API calls, network error handling.',
        assessment: 'Code review: Error handling for fetch failures',
        build: 'Protect API features from failed requests or broken responses.',
        checks: [
          'Uses try/catch or similar handling.',
          'Fetch failures are handled.',
          'Failure states do not crash the app.'
        ]
      }
    ]
  }
];

const toolbar = document.getElementById('lesson-toolbar');
const sectionsRoot = document.getElementById('lesson-sections');
const popupOverlay = document.getElementById('lesson-popup-overlay');
const popup = document.getElementById('lesson-popup');
const popupHeader = document.getElementById('lesson-popup-header');
const popupTitle = document.getElementById('lesson-popup-title');
const popupBody = document.getElementById('lesson-popup-body');

let isDragging = false;
let dragOffset = { x: 0, y: 0 };

function startDrag(event) {
  isDragging = true;
  const rect = popup.getBoundingClientRect();
  dragOffset = {
    x: event.clientX - rect.left,
    y: event.clientY - rect.top
  };
}

function onDrag(event) {
  if (!isDragging) return;
  popup.style.transform = 'none';
  popup.style.left = `${event.clientX - dragOffset.x}px`;
  popup.style.top = `${event.clientY - dragOffset.y}px`;
}

function stopDrag() {
  isDragging = false;
}

popupHeader.addEventListener('mousedown', startDrag);
document.addEventListener('mousemove', onDrag);
document.addEventListener('mouseup', stopDrag);

function resetPopupPosition() {
  popup.style.left = '50%';
  popup.style.top = '50%';
  popup.style.transform = 'translate(-50%, -50%)';
}

function findSection(sectionId) {
  return lessonSections.find((section) => section.id === sectionId);
}

function findTopic(sectionId, topicId) {
  const section = findSection(sectionId);
  if (!section) return null;
  return section.topics.find((topic) => topic.id === topicId) || null;
}

function renderToolbar() {
  toolbar.innerHTML = lessonSections.flatMap((section) =>
    section.topics.map((topic) => `
      <button type="button" data-section-id="${section.id}" data-topic-id="${topic.id}">
        <span>${topic.title}</span>
        <small>${section.title}</small>
      </button>
    `)
  ).join('');

  toolbar.querySelectorAll('button').forEach((button) => {
    button.addEventListener('click', () => openTopicPopup(button.dataset.sectionId, button.dataset.topicId));
  });
}

function renderSections() {
  sectionsRoot.innerHTML = lessonSections.map((section) => `
    <section class="lesson-section" id="section-${section.id}">
      <div class="lesson-section-head">
        <h2>${section.title}</h2>
        <span>${section.topics.length} lessons</span>
      </div>
      <p>${section.intro}</p>
      <div class="lesson-topic-grid">
        ${section.topics.map((topic) => `
          <div class="lesson-topic">
            <button type="button" data-section-id="${section.id}" data-topic-id="${topic.id}">
              <strong>${topic.title}</strong>
              <em>${topic.summary}</em>
              <small>${topic.assessment}</small>
            </button>
          </div>
        `).join('')}
      </div>
    </section>
  `).join('');

  sectionsRoot.querySelectorAll('.lesson-topic button').forEach((button) => {
    button.addEventListener('click', () => openTopicPopup(button.dataset.sectionId, button.dataset.topicId));
  });
}

function openTopicPopup(sectionId, topicId) {
  const topic = findTopic(sectionId, topicId);
  if (!topic) return;

  popupTitle.textContent = topic.title;
  popupBody.innerHTML = `
    <p>${topic.objective}</p>
    <div class="lesson-popup-grid">
      <div class="lesson-popup-card">
        <strong>Project Evidence Required</strong>
        <p>${topic.evidence}</p>
      </div>
      <div class="lesson-popup-card">
        <strong>Assessment Method</strong>
        <p>${topic.assessment}</p>
      </div>
      <div class="lesson-popup-card">
        <strong>Lesson Build Target</strong>
        <p>${topic.build}</p>
      </div>
    </div>
    <div>
      <strong>Teaching Checks</strong>
      <div class="lesson-checklist">
        ${topic.checks.map((item) => `<div>${item}</div>`).join('')}
      </div>
    </div>
  `;

  resetPopupPosition();
  popupOverlay.style.display = 'block';
}

window.closeLessonPopup = function closeLessonPopup() {
  popupOverlay.style.display = 'none';
};

renderToolbar();
renderSections();
</script>
