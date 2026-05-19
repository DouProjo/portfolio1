---
layout: post
codemirror: true
title: CS111 Interactive Concept Demonstrator
description: Interactive buttons and animations showing how CS111 concepts are used in the boss fight game
permalink: /CSSE/Interactive
author: Me
---

# CS111 Interactive Concept Demonstrator

Click a lesson below to see how the boss fight actually uses each CS111 concept. Each popup is meant to help you read the level like a programmer, not just memorize a definition.

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

.concept-link-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
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

.concept-mermaid-card {
  background: linear-gradient(180deg, rgba(18, 18, 18, 0.98), rgba(9, 9, 9, 0.98));
  border-radius: 18px;
  padding: 20px 22px;
  margin: 20px 0 24px;
}

.concept-mermaid-card h3 {
  margin-top: 0;
}

.concept-mermaid-card p {
  margin: 0 0 12px;
  color: #ddd5c6;
}

.concept-mermaid-wrap {
  overflow-x: auto;
  padding-top: 6px;
}

.lesson-table-card {
  background: linear-gradient(180deg, rgba(18, 18, 18, 0.98), rgba(9, 9, 9, 0.98));
  border-radius: 18px;
  padding: 20px 22px;
  margin: 20px 0 24px;
}

.lesson-table-card h3 {
  margin-top: 0;
}

.lesson-table-card p {
  margin: 0 0 12px;
  color: #ddd5c6;
}

.lesson-table-wrap {
  overflow-x: auto;
}

.lesson-accordion {
  display: grid;
  gap: 12px;
}

.lesson-details {
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 14px;
  background: rgba(255, 255, 255, 0.03);
  overflow: hidden;
}

.lesson-details summary {
  list-style: none;
  cursor: pointer;
  padding: 14px 16px;
  font-weight: 700;
  color: #ffffff;
  background: rgba(76, 175, 80, 0.14);
}

.lesson-details summary::-webkit-details-marker {
  display: none;
}

.lesson-details[open] summary {
  border-bottom: 1px solid rgba(255, 255, 255, 0.12);
}

.lesson-details-body {
  padding: 14px;
}

.lesson-table {
  width: 100%;
  min-width: 920px;
  border-collapse: collapse;
}

.lesson-table th,
.lesson-table td {
  border: 1px solid rgba(255, 255, 255, 0.12);
  padding: 12px 14px;
  text-align: left;
  vertical-align: top;
}

.lesson-table th {
  background: rgba(76, 175, 80, 0.2);
  color: #ffffff;
}

.lesson-table td:first-child {
  color: #8fffa2;
  font-weight: 700;
  width: 220px;
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

<div class="lesson-table-card">
  <h3>Lessons About To Be Taught</h3>
  <p>
    Each section below collapses by category and follows the same format: Learning Objective, Project Evidence Required, and Assessment Method.
  </p>
  <div class="lesson-accordion">
    <details class="lesson-details" open>
      <summary>Object-Oriented Programming</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Writing Classes</td><td>Create minimum 2 custom character classes extending base classes</td><td>Code review: Player.js, NPC.js, Enemy.js</td></tr>
            <tr><td>Methods &amp; Parameters</td><td>Implement methods with parameters such as <code>collisionHandler(other, direction)</code></td><td>Code review: Method signatures with 2+ parameters</td></tr>
            <tr><td>Instantiation &amp; Objects</td><td>Instantiate game objects in GameLevel configuration</td><td>Code review: GameLevel setup objects</td></tr>
            <tr><td>Inheritance (Basic)</td><td>Create class hierarchy with 2+ levels such as GameObject to Character to Player</td><td>Code review: <code>extends</code> keyword, inheritance chain</td></tr>
            <tr><td>Method Overriding</td><td>Override parent methods such as <code>update()</code>, <code>draw()</code>, and <code>handleCollision()</code></td><td>Code review: Polymorphic implementations</td></tr>
            <tr><td>Constructor Chaining</td><td>Use <code>super()</code> to chain constructors</td><td>Code review: <code>super(data, gameEnv)</code> calls</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Control Structures</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Iteration</td><td>Use loops for game object arrays and animation frames</td><td>Code review: <code>for</code>, <code>forEach</code>, <code>while</code> loops</td></tr>
            <tr><td>Conditionals</td><td>Implement collision detection and state transitions</td><td>Code review: <code>if/else</code>, nested conditions</td></tr>
            <tr><td>Nested Conditions</td><td>Complex game logic such as power-up plus collision plus direction</td><td>Code review: Multi-level conditionals</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Data Types</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Numbers</td><td>Position, velocity, score tracking</td><td>Code review: Numeric properties</td></tr>
            <tr><td>Strings</td><td>Character names, sprite paths, game states</td><td>Code review: String manipulation</td></tr>
            <tr><td>Booleans</td><td>Flags such as <code>isJumping</code>, <code>isPaused</code>, <code>isVulnerable</code></td><td>Code review: Boolean logic</td></tr>
            <tr><td>Arrays</td><td>Game object collections, level data</td><td>Code review: Array operations</td></tr>
            <tr><td>Objects (JSON)</td><td>Configuration objects, sprite data</td><td>Code review: Object literals</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Operators</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Mathematical</td><td>Physics calculations such as gravity, velocity, collision</td><td>Code review: <code>+</code>, <code>-</code>, <code>*</code>, <code>/</code> in physics</td></tr>
            <tr><td>String Operations</td><td>Path concatenation, text display</td><td>Code review: Template literals, concatenation</td></tr>
            <tr><td>Boolean Expressions</td><td>Compound conditions in game logic</td><td>Code review: <code>&amp;&amp;</code>, <code>||</code>, <code>!</code></td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Input/Output</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Keyboard Input</td><td>Arrow keys, space, WASD controls using event listeners</td><td>Testing: Key event handlers respond correctly</td></tr>
            <tr><td>Canvas Rendering</td><td>Draw sprites, backgrounds, platforms using Canvas API</td><td>Code review: <code>draw()</code> method implementations</td></tr>
            <tr><td>GameEnv Configuration</td><td>Set canvas size, difficulty levels, game settings</td><td>Code review: <code>GameEnv.create()</code> and <code>GameSetup.js</code></td></tr>
            <tr><td>API Integration</td><td>Implement Leaderboard API (POST/GET scores)</td><td>Code review: Fetch calls with error handling</td></tr>
            <tr><td>Asynchronous I/O</td><td>Use <code>async/await</code> or promises for API calls</td><td>Code review: <code>async/await</code> or <code>.then()</code> chains</td></tr>
            <tr><td>JSON Parsing</td><td>Parse API responses such as leaderboard data or AI responses</td><td>Code review: <code>JSON.parse()</code>, object destructuring</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Documentation</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Code Comments</td><td>JSDoc comments for classes and methods</td><td>Code review: Comment density &gt;10%</td></tr>
            <tr><td>Mini-Lesson Documentation</td><td>Create comic or visual post with embedded runtime game demo</td><td>Portfolio review: Mini-lesson in personal portfolio</td></tr>
            <tr><td>Code Highlights</td><td>Annotate key code snippets in documentation such as OOP, APIs, and collision</td><td>Portfolio review: Highlighted code examples with explanations</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Debugging</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Console Debugging</td><td>Use <code>console.log</code> to track game state, variables, and method calls</td><td>Code review: Strategic logging in update/collision methods</td></tr>
            <tr><td>Hit Box Visualization</td><td>Draw or visualize collision boundaries to refine detection</td><td>Demo: Toggle hit box display, adjust collision rectangles</td></tr>
            <tr><td>Source-Level Debugging</td><td>Set breakpoints in DevTools and step through code execution</td><td>Demo: Use Sources tab to pause and inspect code flow</td></tr>
            <tr><td>Network Debugging</td><td>Examine Network tab for API calls, CORS errors, and response status</td><td>Demo: Inspect fetch requests, response data, error messages</td></tr>
            <tr><td>Application Debugging</td><td>Examine cookies, localStorage, and session data for login/state</td><td>Demo: Application tab inspection of stored data</td></tr>
            <tr><td>Element Inspection</td><td>Use Element Viewer to inspect canvas, DOM elements, and styles</td><td>Demo: Inspect element properties and game object state</td></tr>
          </tbody>
        </table>
      </div>
    </details>

    <details class="lesson-details">
      <summary>Testing &amp; Verification</summary>
      <div class="lesson-details-body lesson-table-wrap">
        <table class="lesson-table">
          <thead>
            <tr>
              <th>Learning Objective</th>
              <th>Project Evidence Required</th>
              <th>Assessment Method</th>
            </tr>
          </thead>
          <tbody>
            <tr><td>Gameplay Testing</td><td>Test level completion, character interactions, and collision detection</td><td>Live demo: Play through level without critical bugs</td></tr>
            <tr><td>Integration Testing</td><td>Test API integration such as Leaderboard or NPC AI with live backend</td><td>Demo: Successful score saving and AI responses</td></tr>
            <tr><td>API Error Handling</td><td>Use <code>try/catch</code> blocks for API calls and network error handling</td><td>Code review: Error handling for fetch failures</td></tr>
          </tbody>
        </table>
      </div>
    </details>
  </div>
</div>

<div class="concept-mermaid-card">
  <h3>How The Concepts Connect</h3>
  <p>
    This Mermaid diagram gives a quick visual map of how each CS111 concept shows up in the boss fight lesson before you open the summary buttons below.
  </p>
  <div class="concept-mermaid-wrap">
    <div class="mermaid">
%%{init: {'theme': 'dark'}}%%
flowchart TD
    A["CS111 Boss Fight Lesson"]

    A --> B["Object-Oriented Programming"]
    B --> B1["Classes<br/>boss class and level class"]
    B --> B2["Inheritance<br/>extends Character and super()"]
    B --> B3["Objects<br/>this.classes builds the scene"]

    A --> C["Control Structures"]
    C --> C1["Loops<br/>update bullets and cannonballs"]
    C --> C2["Conditionals<br/>phases, menu, win and lose"]
    C --> C3["Nested Checks<br/>collision and damage rules"]

    A --> D["Data Types"]
    D --> D1["Numbers<br/>HP, speed, timers, positions"]
    D --> D2["Strings<br/>state names and messages"]
    D --> D3["Arrays and Flags<br/>bullets, queue, booleans"]
    D --> D4["Objects<br/>config data and grouped values"]

    A --> E["Operators"]
    E --> E1["Math<br/>orbiting and bullet spread"]
    E --> E2["Strings<br/>template text for the UI"]
    E --> E3["Boolean Logic<br/>compound checks"]

    A --> F["Input and Output"]
    F --> F1["Keyboard Input<br/>keydown and key maps"]
    F --> F2["Canvas Output<br/>drawImage, bars, bullets"]
    F --> F3["GameEnv Setup<br/>canvas size and space"]
    F --> F4["API and JSON<br/>fetch, await, response.json()"]

    A --> G["Documentation"]
    G --> G1["Comments<br/>JSDoc and lesson notes"]
    G --> G2["Mini-Lesson<br/>portfolio explanation page"]
    G --> G3["Highlights<br/>snippets with context"]

    A --> H["Debugging"]
    H --> H1["Console Logs<br/>state and failure checks"]
    H --> H2["Visual Inspection<br/>canvas and hitbox clues"]
    H --> H3["Network and Storage<br/>API and localStorage checks"]

    A --> I["Testing and Verification"]
    I --> I1["Gameplay Tests<br/>play through the fight"]
    I --> I2["Integration Tests<br/>frontend and backend"]
    I --> I3["Error Handling<br/>safe fallback on failure"]
    </div>
  </div>
</div>

<div class="concept-grid">
  <a class="concept-btn concept-link-btn" href="{{ site.baseurl }}/CSSE111/GameRunner">Open Boss Game Page</a>
  <button class="concept-btn" onclick="openPopup('oop')">Boss Fight OOP</button>
  <button class="concept-btn" onclick="openPopup('control')">Boss Fight Control</button>
  <button class="concept-btn" onclick="openPopup('datatypes')">Boss Fight Data</button>
  <button class="concept-btn" onclick="openPopup('operators')">Boss Fight Operators</button>
  <button class="concept-btn" onclick="openPopup('io')">Boss Fight Input/Output</button>
  <button class="concept-btn" onclick="openPopup('documentation')">Boss Fight Comments</button>
  <button class="concept-btn" onclick="openPopup('debugging')">Boss Fight Debugging</button>
  <button class="concept-btn" onclick="openPopup('testing')">Boss Fight Testing</button>
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
      title: 'Boss Fight Lesson: OOP',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The boss fight uses object-oriented programming by giving different jobs to different classes. The boss object handles boss behavior. The level object handles the battle system.
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
      title: 'Boss Fight Lesson: Control Flow',
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
      title: 'Boss Fight Lesson: Data Types',
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
      title: 'Boss Fight Lesson: Operators',
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
      title: 'Boss Fight Lesson: Input and Output',
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
      title: 'Boss Fight Lesson: Comments and Readability',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The boss fight file does not rely on big textbook definitions. Instead, it uses short comments to show the reader what each section is trying to do.
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
      title: 'Boss Fight Lesson: Debugging',
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
      title: 'Boss Fight Lesson: Testing',
      body: `
        <div class="concept-highlight">
          <strong>Lesson focus:</strong><br>
          The boss fight file does not include automated tests, so the lesson here is how to turn the real gameplay states into a clean test checklist.
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

- [CS111 Game Runner](/CSSE111/GameRunner) - Interactive boss fight game
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
