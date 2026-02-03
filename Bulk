<!DOCTYPE html>
<html>
<head>
<style>
/* ===== INSTRUCTION SCREEN STYLES ===== */
#instructionScreen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: black;
    color: white;
    z-index: 2147483647; /* Highest priority */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    cursor: pointer;
    opacity: 0;
    animation: fadeInDrop 1.5s ease forwards;
}

#instructionScreen h1 {
    font-size: 32px;
    margin-bottom: 20px;
    font-family: "Courier New", monospace;
    text-shadow: 0 0 10px white;
}

#instructionScreen h2 {
    font-size: 48px;
    color: #ffd700;
    font-family: monospace;
    border: 2px solid #ffd700;
    padding: 10px 20px;
    border-radius: 10px;
    animation: pulseText 2s infinite;
}

#instructionScreen p {
    margin-top: 50px;
    color: gray;
    font-size: 14px;
    animation: blink 1s infinite;
}

@keyframes fadeInDrop {
    0% { opacity: 0; transform: translateY(-50px); }
    100% { opacity: 1; transform: translateY(0); }
}

@keyframes pulseText {
    0% { transform: scale(1); box-shadow: 0 0 0px #ffd700; }
    50% { transform: scale(1.05); box-shadow: 0 0 20px #ffd700; }
    100% { transform: scale(1); box-shadow: 0 0 0px #ffd700; }
}

@keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.3; } }


/* ===== ORIGINAL GAME STYLES ===== */
body {
  margin: 0;
  /* Default: Light Blue Background */
  background: #4dabf7; 
  /* Default: White Text */
  color: white;
  font-family: "Courier New", monospace;
  overflow: hidden;
  transition: background 0.5s, color 0.5s;
}

.hidden { display: none !important; }

/* Wrapper for transitions */
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  width: 100%;
  transition: opacity 0.3s ease;
  opacity: 1;
  z-index: 100;
}

/* Page Transition Classes */
.fade-out-page { opacity: 0 !important; }
.fade-in-page { animation: fadeInEffect 0.5s ease forwards; }

@keyframes fadeInEffect {
  from { opacity: 0; transform: translate(-50%, -40%); }
  to { opacity: 1; transform: translate(-50%, -50%); }
}

/* Button Animations */
.anim-zoom {
  animation: zoomFade 0.25s ease-in forwards !important;
  pointer-events: none;
}

@keyframes zoomFade {
  0% { transform: scale(1); opacity: 1; }
  100% { transform: scale(5); opacity: 0; }
}

/* STANDARD BUTTONS */
input, button {
  padding: 12px;
  background: #ffd700; 
  color: black;
  border: 2px solid white;
  margin-top: 10px;
  font-size: 16px;
  cursor: pointer;
  transition: transform 0.2s, background 0.2s;
  font-weight: bold;
  position: relative;
  z-index: 10;
}

button:hover {
    background: #ffec8b;
    transform: scale(1.05);
}

img {
  position: absolute;
  width: 120px;
  cursor: pointer;
  animation: float 6s infinite alternate ease-in-out;
}

@keyframes float {
  from { transform: translateY(0); }
  to { transform: translateY(-40px); }
}

.earthquake { animation: quake 0.07s infinite; }
@keyframes quake {
  0% { transform: translate(0,0); }
  20% { transform: translate(-20px,10px); }
  40% { transform: translate(20px,-10px); }
  60% { transform: translate(-25px,15px); }
  80% { transform: translate(25px,-15px); }
  100% { transform: translate(0,0); }
}

.key {
  width: 50px;
  height: 50px;
  background-color: #ffd700;
  position: absolute;
  transition: left 1s ease, top 1s ease, background 0.2s; 
  border-radius: 6px;
  border: 2px solid white;
  cursor: pointer;
  z-index: 20;
}

#limboText, #reactionText, #cpsText, #welcomeText {
  font-size: 32px;
  margin-top: 20px;
  text-shadow: 1px 1px 2px black;
}

#reactionArea { width: 100vw; height: 100vh; cursor: pointer; }
#menuScreen h1 { font-size: 36px; margin-bottom: 30px; text-shadow: 2px 2px 0px #000; }
.menuButton { display:block; margin: 10px auto; }

/* ===== VIRUS COUNTDOWN + GLITCH ===== */
#countdown {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 64px;
  color: red;
  z-index: 9999;
  font-weight: bold;
  text-shadow: 2px 2px 0px white;
}

.glitch { animation: glitchFlash 0.1s infinite alternate; }
@keyframes glitchFlash { 0% { filter: invert(0); } 100% { filter: invert(1); } }
.blank { background: black !important; color: black !important; }

/* ===== BORDER CONVEYOR ===== */
.conveyor { position: fixed; z-index: 99998; background: #4dabf7; overflow: hidden; pointer-events: none; }
.conveyor img { position: static; width: 50px; height: 50px; margin: 0; padding: 0; animation: none; vertical-align: middle; }
.conveyor-track { display: flex; }
.c-horz { left: 0; width: 100%; height: 50px; }
.c-top { top: 0; border-bottom: 2px solid white; }
.c-bottom { bottom: 0; border-top: 2px solid white; }
.c-horz .conveyor-track { width: 200%; animation: slideLeft 10s linear infinite; }
.c-vert { top: 50px; bottom: 50px; width: 50px; }
.c-left { left: 0; border-right: 2px solid white; }
.c-right { right: 0; border-left: 2px solid white; }
.c-vert .conveyor-track { flex-direction: column; height: 200%; animation: slideUp 10s linear infinite; }
@keyframes slideLeft { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }
@keyframes slideUp { 0% { transform: translateY(0); } 100% { transform: translateY(-50%); } }

/* ===== HUB STYLES ===== */
.hub-row { display: flex; justify-content: center; align-items: flex-start; width: 90vw; margin: 0 auto; }
.hub-column { flex: 1; text-align: center; border-right: 2px solid white; padding: 0 10px; }
.hub-column:last-child { border-right: none; }
.hub-column h2 { color: white; text-shadow: 2px 2px 0px #000; margin-bottom: 20px; font-size: 18px; text-transform: uppercase; letter-spacing: 1px; }
.hub-btn { display: block; width: 90%; margin: 10px auto; }

/* Locked Hub State */
.hub-locked .hub-btn {
    pointer-events: none;
    filter: grayscale(100%);
    opacity: 0.6;
    position: relative;
}
.hub-locked .hub-btn::after {
    content: "🔒";
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    font-size: 24px;
}
#hubEndings {
    position: absolute;
    top: 20px;
    right: 30px;
    font-size: 20px;
    font-weight: bold;
    text-shadow: 1px 1px 0 #000;
}

/* ===== SECURLY SCREEN STYLES ===== */
#securlyScreen {
    position: fixed; top: 0; left: 0; width: 100vw; height: 100vh;
    background: #f8f9fa; z-index: 9999999; color: #333;
    font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
    display: flex; flex-direction: column; align-items: center; justify-content: flex-start;
    padding-top: 100px; box-sizing: border-box; cursor: default;
}
.securly-logo { position: absolute; top: 40px; left: 40px; font-size: 24px; font-weight: bold; color: #007bff; display: flex; align-items: center; }
.securly-logo::before { content: '🛡'; margin-right: 5px; }
#securlyScreen h1 { font-size: 36px; font-weight: 600; margin-bottom: 10px; color: #212529; text-shadow: none; }
#securlyScreen .subtitle { color: #6c757d; font-size: 18px; margin-bottom: 60px; }
.securly-content { display: flex; align-items: center; gap: 50px; }
.dog-placeholder {
    width: 300px; height: 250px; background-color: #ffeeb0;
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    position: relative; display: flex; justify-content: center; align-items: flex-end;
}
.dog-placeholder img { position: static; width: 200px; animation: none; }
.securly-details { text-align: left; color: #495057; }
.securly-details h3 { font-size: 18px; margin-bottom: 15px; font-weight: normal; }
.securly-details p { margin: 5px 0; font-size: 14px; color: #6c757d; }
#gravityBall { position: absolute; width: 50px; height: 50px; background: gray; border-radius: 50%; cursor: grab; z-index: 10000000; }
#gravityBall:active { cursor: grabbing; }

/* ===== TERMINAL & SECRET STYLES ===== */
#terminalScreen { background: black; color: #00ff00; font-family: 'Courier New', monospace; text-align: left; padding: 20px; box-sizing: border-box; height: 100vh; width: 100vw; z-index: 999999; }
#terminalContent { height: 80%; overflow: hidden; margin-bottom: 20px; }
#terminalInputLine { display: flex; align-items: center; }
#terminalInput { background: transparent; border: none; color: #00ff00; font-family: inherit; font-size: 18px; width: 100%; outline: none; }
#secretScreen { position: fixed; top: 0; left: 0; background: #050000; color: #ff0000; display: flex; flex-direction: column; justify-content: center; align-items: center; height: 100vh; width: 100vw; z-index: 200000000; }
#watchingOverlay {
    position: fixed; top:0; left:0; width:100%; height:100%;
    background: black; z-index: 100000000;
    display: flex; flex-direction: column; justify-content: center; align-items: center;
    pointer-events: none; opacity: 0;
}
#watchingOverlay img { position: static; width: 400px; }

/* ===== DARK MODE & ANGERED STYLES ===== */
body.dark-mode {
    background: black !important;
    color: white !important;
}
body.dark-mode .conveyor { background: black; border-color: white; }
body.dark-mode input, 
body.dark-mode button {
    background: white !important;
    color: black !important;
    border: 2px solid black !important;
}
body.dark-mode .key {
    background-color: white !important; /* White keys */
    border-color: gray !important;
}

/* Broken Start Button in Dark Mode */
button.broken-btn {
    background: repeating-linear-gradient(
      45deg,
      #ffffff,
      #ffffff 10px,
      #000000 10px,
      #000000 20px
    ) !important;
    color: black !important;
    border: 2px solid white !important;
    cursor: not-allowed;
    opacity: 0.6;
}

/* Yellow Flash Overlay */
#yellowFlash {
    position: fixed; top: 0; left: 0; width: 100vw; height: 100vh;
    background: rgba(255, 255, 0, 0.4);
    z-index: 999999999;
    pointer-events: none;
    opacity: 0;
    transition: opacity 0.1s;
}

#angeredScreen {
    background: black;
    color: white;
    z-index: 300000;
}

/* ===== CHASE TIMER BAR ===== */
#chaseUI {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 80px;
    z-index: 999999998; /* Under flash, above everything else */
    pointer-events: none;
    background: transparent;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    padding-top: 10px;
}

#chaseTimerText {
    font-size: 24px;
    font-weight: bold;
    color: #ff0000;
    text-shadow: 2px 2px 0 #000;
    margin-bottom: 5px;
    background: rgba(0,0,0,0.5);
    padding: 2px 10px;
}

#chaseBarContainer {
    width: 80%;
    height: 30px;
    background: #333;
    border: 2px solid white;
    position: relative;
    border-radius: 15px;
    overflow: visible;
}

/* The LeBron head moving across the bar */
#chaseIcon {
    position: absolute;
    top: -15px; /* stick up a bit */
    left: 0;
    width: 50px;
    height: 50px;
    background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQl7pJ8BfXJUsWLD4TYbULz2P9R9nOJRdJYSTYR-VX8R6PjjZGXyiTlneFiMJVdsuQN-CIr3T-th-DMhVYVpjsgwENdJcO2gnDJicmDVLLD&s=10");
    background-size: cover;
    border-radius: 50%;
    border: 2px solid red;
    box-shadow: 0 0 10px red;
    transform: translateX(-50%); /* Center the head on the progress point */
    transition: left 0.1s linear;
}

#chaseLabel {
    position: absolute;
    top: -20px;
    left: 50%;
    transform: translateX(-50%);
    color: red;
    font-weight: bold;
    font-size: 12px;
    text-shadow: 1px 1px 0 black;
    white-space: nowrap;
}

/* ===== CAUGHT SCREEN ===== */
#caughtScreen {
    position: fixed;
    top: 0; left: 0;
    width: 100vw; height: 100vh;
    background: black;
    color: red;
    z-index: 9999999999; /* Max Priority */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
#caughtNumbers {
    font-family: monospace;
    font-size: 16px;
    color: #444;
    word-break: break-all;
    position: absolute;
    top:0; left:0; width:100%; height:100%;
    opacity: 0.3;
    pointer-events: none;
    overflow: hidden;
}

</style>
</head>

<body>

<div id="instructionScreen" onclick="dismissInstructions()">
    <h1>put in fullscreen and minimize the screen a little bit</h1>
    <h2>Ctrl and -</h2>
    <p>[ CLICK ANYWHERE TO CONTINUE ]</p>
</div>

<div id="yellowFlash"></div>

<div id="chaseUI" class="hidden">
    <div id="chaseTimerText">00:00:00</div>
    <div id="chaseBarContainer">
        <div id="chaseIcon">
            <div id="chaseLabel">lebron</div>
        </div>
    </div>
</div>

<div id="caughtScreen" class="hidden">
    <div id="caughtNumbers"></div>
    <h1 style="z-index:2; font-size:60px; text-shadow:2px 2px 0 white;">It has caught you.</h1>
</div>

<div id="watchingOverlay">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQl7pJ8BfXJUsWLD4TYbULz2P9R9nOJRdJYSTYR-VX8R6PjjZGXyiTlneFiMJVdsuQN-CIr3T-th-DMhVYVpjsgwENdJcO2gnDJicmDVLLD&s=10">
    <h1 style="color:red; font-size: 50px;">HE IS WATCHING.</h1>
</div>

<div id="securlyScreen">
    <div class="securly-logo">securly</div>
    <h1>Looks like this page isn't allowed</h1>
    <p class="subtitle">This page has been blocked by Classroom.</p>
    
    <div class="securly-content">
        <div class="dog-placeholder">
            <img src="https://openclipart.org/image/800px/279836" alt="Sleeping Dog">
        </div>
        <div class="securly-details">
            <h3>Blocking details</h3>
            <p>URL: sites.google.com</p>
            <p>Blocking plan: *Non-Academic Blocked Sites*</p>
        </div>
    </div>
</div>
<div id="gravityBall"></div>

<div id="terminalScreen" class="hidden">
    <div id="terminalTarget" style="font-weight: bold; font-size: 24px; border: 1px solid #00ff00; padding: 5px; display: inline-block;">CODE: LOADING...</div>
    <div id="terminalContent"></div>
    <div id="terminalInputLine">
        <span>root@system:~$&nbsp;</span>
        <input type="text" id="terminalInput" autofocus>
    </div>
</div>

<div id="secretScreen" class="hidden">
    <h1 style="font-size: 40px;">YOU ARE NOT SUPPOSED TO BE HERE</h1>
    <p id="sessionIdDisplay" style="font-size: 20px; color: gray;"></p>
</div>


<div class="conveyor c-horz c-top"><div class="conveyor-track" id="trackTop"></div></div>
<div class="conveyor c-horz c-bottom"><div class="conveyor-track" id="trackBottom"></div></div>
<div class="conveyor c-vert c-left"><div class="conveyor-track" id="trackLeft"></div></div>
<div class="conveyor c-vert c-right"><div class="conveyor-track" id="trackRight"></div></div>

<div id="menuScreen" class="center hidden">
  <h1>I mean yeah bro I guess</h1>
  <button id="menuStartBtn" class="menuButton" onclick="press(this, () => switchScreen('menuScreen', 'googleSignIn'))">START</button>
  <button id="menuFinaleBtn" class="menuButton hidden" onclick="press(this, startFinale)">Finale</button>
  
  <button class="menuButton" id="escapeButton">ESCAPE BUTTON</button>
</div>

<div id="angeredScreen" class="center hidden" style="width:100vw; height:100vh;">
    <h1 style="margin-top: 40vh;">You have angered him.</h1>
</div>

<div id="googleSignIn" class="center hidden">
  <button onclick="press(this, startKeyGame)">Sign in with Google</button>
</div>

<div id="keyGame" class="center hidden" style="width:100%; height:100%;"></div>

<div id="limboScreen" class="center hidden">
  <div id="limboText">LIMBO: let's see if you got it right</div>
</div>

<div id="welcomeScreen" class="center hidden">
  <div id="welcomeText">Welcome and Good luck. Click here to continue</div>
</div>

<div id="reactionScreen" class="center hidden">
  <div id="reactionText">Click start to begin</div>
  <button id="reactionStart">START</button>
  <div id="reactionArea" class="hidden" style="background:red;"></div>
</div>

<div id="cpsScreen" class="center hidden">
  <div id="cpsText">Press space 16 times in 1 second!</div>
  <div id="cpsResult"></div>
</div>

<div id="goatScreen" class="center hidden">
  <h1 id="goatTitle">WHO’S THE GOAT?</h1>
  <div id="goatCount">Clicks: 0</div>
</div>

<div id="login" class="center hidden">
  <div id="countdown">5</div>
  <h1>🔒 Your computer has a virus. Type the right password to eliminate it.</h1>
  <input id="code" type="password" placeholder="ENTER KEY">
  <br>
  <button onclick="press(this, checkCode)">CONTINUE</button>
</div>

<div id="quiz" class="center hidden"></div>

<div id="hubScreen" class="center hidden">
    <div id="hubEndings">Endings completed: 0/2</div>
    <h1 id="hubCongrats" class="hidden" style="text-shadow: 2px 2px 0 #000;">Congrats</h1>
    
    <div id="hubLinksContainer">
        <div class="hub-row">
            <div class="hub-column">
            <h2>Games - Experimental</h2>
            <button class="hub-btn" onclick="press(this, () => openGame('https://www.coolmathgames.com/'))">CoolMath Games</button>
            </div>
            <div class="hub-column">
            <h2>Random Fun Stuff</h2>
            <button class="hub-btn" onclick="press(this, openHideout)">Open hideout-now</button>
            <button class="hub-btn" onclick="press(this, () => openGame('https://elgoog.im/'))">elgoog.im</button>
            </div>
            <div class="hub-column">
            <h2>More to be added soon...</h2>
            </div>
        </div>
    </div>
    
    <button id="hubContinueBtn" class="hidden" style="margin-top:50px; font-size: 24px;" onclick="press(this, triggerAngeredPhase)">CONTINUE</button>
</div>

<script>
const CORRECT_CODE = "kingjames";
const LEBRON_IMG = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQl7pJ8BfXJUsWLD4TYbULz2P9R9nOJRdJYSTYR-VX8R6PjjZGXyiTlneFiMJVdsuQN-CIr3T-th-DMhVYVpjsgwENdJcO2gnDJicmDVLLD&s=10";

// Game Stages: 0 = First Run, 1 = Dark Mode Run, 2 = Complete
let gameStage = 0; 

// NEW INSTRUCTION DISMISS FUNCTION
function dismissInstructions() {
    const screen = document.getElementById('instructionScreen');
    screen.style.transition = "opacity 0.5s ease";
    screen.style.opacity = "0";
    setTimeout(() => {
        screen.remove();
    }, 500);
}

// ===== LEBRON WATCHING INTERVAL =====
setInterval(() => {
    const overlay = document.getElementById('watchingOverlay');
    overlay.style.opacity = "1";
    setTimeout(() => {
        overlay.style.opacity = "0";
    }, 400);
}, 10000);

// ===== SECURLY PUZZLE LOGIC =====
const ball = document.getElementById('gravityBall');
const securlyScreen = document.getElementById('securlyScreen');
const menuScreen = document.getElementById('menuScreen');

let mouseX = window.innerWidth / 2;
let mouseY = window.innerHeight / 2;
let ballX = window.innerWidth / 2;
let ballY = 0;
let ballVy = 0;
const gravity = 1.5; 
let isDragging = false;
let unlockStage = 0; 
let securlyActive = true;

window.addEventListener('mousemove', (e) => {
    mouseX = e.clientX;
    mouseY = e.clientY;
    if(isDragging) {
        ballX = mouseX - 25;
        ballY = mouseY - 25;
        ballVy = 0;
    }
});

ball.addEventListener('mousedown', () => isDragging = true);
window.addEventListener('mouseup', () => {
    if(isDragging && securlyActive) {
        isDragging = false;
        checkDropZone();
    }
});

function physicsLoop() {
    if(!isDragging) {
        ballVy += gravity;
        ballY += ballVy;
        if(ballY > window.innerHeight - 50) {
            ballY = window.innerHeight - 50;
            ballVy *= -0.4; 
        }
    }
    ball.style.left = ballX + 'px';
    ball.style.top = ballY + 'px';
    if(securlyActive) requestAnimationFrame(physicsLoop);
}
physicsLoop();

setInterval(() => {
    if(securlyActive) {
        isDragging = false; 
        ballX = mouseX - 25;
        ballY = mouseY - 25; 
        ballVy = 10; 
    }
}, 5000);

function checkDropZone() {
    const center = window.innerWidth / 2;
    const isLeft = (ballX + 25) < center;
    if(unlockStage === 0) {
        if(isLeft) { unlockStage = 1; ball.style.background = "#555"; }
        else { unlockStage = 0; ball.style.background = "gray"; }
    } else if(unlockStage === 1) {
        if(!isLeft) { unlockStage = 2; ball.style.background = "#333"; }
        else { unlockStage = 0; ball.style.background = "gray"; }
    } else if(unlockStage === 2) {
        if(isLeft) { unlockSecurly(); }
        else { unlockStage = 0; ball.style.background = "gray"; }
    }
}

function unlockSecurly() {
    securlyActive = false;
    securlyScreen.style.transition = "opacity 0.5s";
    securlyScreen.style.opacity = "0";
    ball.style.display = "none";
    setTimeout(() => {
        securlyScreen.style.display = "none";
        startTerminalPhase(); 
    }, 500);
}

// ===== TERMINAL PHASE LOGIC =====
function startTerminalPhase() {
    const term = document.getElementById('terminalScreen');
    const content = document.getElementById('terminalContent');
    const targetEl = document.getElementById('terminalTarget');
    const input = document.getElementById('terminalInput');
    
    term.classList.remove('hidden');
    input.focus();

    const words = ["GLITCH", "LEBRON", "VOID", "ACCESS", "OVERRIDE", "SECURITY", "SYSTEM"];
    let randomTarget = words[Math.floor(Math.random() * words.length)];
    targetEl.innerText = "TYPE THIS CODE: " + randomTarget;

    let logMessages = ["Scanning internal packets...", "User: Admin authenticated?", "Bypassing Classroom filter...", "Fatal Error in sector 7"];

    let logInterval = setInterval(() => {
        let p = document.createElement('div');
        p.innerText = "> " + logMessages[Math.floor(Math.random() * logMessages.length)];
        content.appendChild(p);
        if(content.children.length > 15) content.removeChild(content.firstChild);
    }, 300);

    input.onkeydown = (e) => {
        if(e.key === "Enter") {
            let val = input.value.toUpperCase();
            if(val === "SECRET") {
                clearInterval(logInterval);
                triggerSecretRoom();
            } else if(val === randomTarget) {
                clearInterval(logInterval);
                term.classList.add('hidden');
                menuScreen.classList.remove("hidden");
                menuScreen.classList.add("fade-in-page");
            }
            input.value = "";
        }
    }
}

// ===== SECRET ROOM LOGIC =====
function triggerSecretRoom() {
    const secret = document.getElementById('secretScreen');
    const term = document.getElementById('terminalScreen');
    const sessionDisplay = document.getElementById('sessionIdDisplay');
    
    term.classList.add('hidden');
    secret.classList.remove('hidden');
    sessionDisplay.innerText = "SESSION_ID: " + Math.random().toString(36).substring(2).toUpperCase() + "-" + Date.now();

    setTimeout(() => {
        document.body.classList.add('earthquake', 'glitch');
        spawnLebrons(50);
        setTimeout(() => { location.href = "about:blank"; }, 1500);
    }, 5000);
}

// ===== CORE GAME FUNCTIONS =====

function press(btn, callback) {
    if(btn.classList.contains('broken-btn')) return; // Don't click broken buttons
    btn.classList.add('anim-zoom');
    setTimeout(() => {
        btn.classList.remove('anim-zoom'); 
        callback();
    }, 250);
}

function switchScreen(hideId, showId) {
    const hideEl = document.getElementById(hideId);
    const showEl = document.getElementById(showId);
    if(!hideEl || !showEl) return;
    hideEl.classList.add('fade-out-page');
    setTimeout(() => {
        hideEl.classList.add('hidden');
        hideEl.classList.remove('fade-out-page'); 
        showEl.classList.remove('hidden');
        showEl.classList.add('fade-in-page');
        setTimeout(() => {
            showEl.classList.remove('fade-in-page');
        }, 500);
    }, 300);
}

function initConveyors() {
  const tracks = ['trackTop', 'trackBottom', 'trackLeft', 'trackRight'];
  tracks.forEach(id => {
    const track = document.getElementById(id);
    let html = '';
    for(let i=0; i<50; i++) html += `<img src="${LEBRON_IMG}">`;
    track.innerHTML = html;
  });
}
initConveyors();

document.getElementById("escapeButton").onclick = function() {
  press(this, () => {
      for (let i = 0; i < 15; i++) {
        setTimeout(() => window.open("https://www.deltamath.com", "_blank"), i * 100);
      }
      setTimeout(() => window.close(), 1600);
  });
};

let correctKeyIndex = Math.floor(Math.random() * 10);
function startKeyGame() {
  switchScreen('googleSignIn', 'keyGame');
  const kg = document.getElementById('keyGame');
  kg.innerHTML = "";
  
  for (let i = 0; i < 10; i++) {
    const k = document.createElement("div");
    k.className = "key";
    k.dataset.index = i;
    k.style.left = window.innerWidth / 2 - 250 + Math.random() * 500 + "px";
    k.style.top = window.innerHeight / 2 - 100 + Math.random() * 200 + "px";
    k.onclick = function(e) { press(e.target, () => keyClick(e)); };
    kg.appendChild(k);
  }
  shuffleKeys();
}

function shuffleKeys() {
  const keys = document.querySelectorAll(".key");
  let c = 0;
  const isDark = document.body.classList.contains('dark-mode');
  
  const int = setInterval(() => {
    keys.forEach(k => {
      k.style.left = window.innerWidth / 2 - 250 + Math.random() * 500 + "px";
      k.style.top = window.innerHeight / 2 - 100 + Math.random() * 200 + "px";
    });
    if (c === 0) {
      // FORCE Green flash, regardless of dark mode styling
      keys[correctKeyIndex].style.setProperty("background-color", "green", "important");
      
      setTimeout(() => {
          // Revert explicitly
          if(isDark) {
            keys[correctKeyIndex].style.setProperty("background-color", "white", "important");
          } else {
            keys[correctKeyIndex].style.setProperty("background-color", "#ffd700", "important");
          }
      }, 1000);
    }
    if (++c > 25) clearInterval(int);
  }, 1000);
}

function keyClick(e) {
  switchScreen('keyGame', 'limboScreen');
  const lt = document.getElementById('limboText');
  setTimeout(() => {
    if (+e.target.dataset.index === correctKeyIndex) {
      lt.textContent = "CORRECT!";
      setTimeout(() => { switchScreen('limboScreen', 'welcomeScreen'); }, 2000);
    } else kickOut();
  }, 2000);
}

document.getElementById('welcomeText').onclick = () => {
  switchScreen('welcomeScreen', 'reactionScreen');
  startReactionTest();
};

let reactionTimes = [], tries = 0;
function startReactionTest() {
  const rs = document.getElementById('reactionStart');
  const ra = document.getElementById('reactionArea');
  const rtText = document.getElementById('reactionText');
    // 🩹 Fix for first-run bug
  ra.onclick = null;
  ra.style.background = "red";
  // Reset for subsequent runs
  reactionTimes = [];
  tries = 0;
  rs.classList.remove("hidden");
  ra.classList.add("hidden");
  
  rs.onclick = () => {
    press(rs, () => {
        rs.classList.add("hidden");
        ra.classList.remove("hidden");
        rtText.textContent = "Wait for green!";
        tries++;
        setTimeout(() => {
          ra.style.background = "green";
          const start = performance.now();
          ra.onclick = () => {
            const rt = performance.now() - start;
            reactionTimes.push(rt);
            ra.onclick = null;
            ra.classList.add("hidden");
            ra.style.background = "red";
            rs.classList.remove("hidden");
            rtText.textContent = `Reaction Time: ${Math.round(rt)} ms`;
            if (tries >= 5) {
              const avg = reactionTimes.reduce((a, b) => a + b) / reactionTimes.length;
              avg <= 300 ? (switchScreen('reactionScreen', 'cpsScreen'), startCPSTest()) : kickOut();
            }
          };
        }, 1000 + Math.random() * 2000);
    });
  };
}

function startCPSTest() {
  let clicks = 0, start = null, testing = false;
  document.getElementById('cpsResult').textContent = ""; // Reset
  
  window.onkeydown = e => {
    if (e.repeat) return;
    if (e.code !== "Space" && e.key.toLowerCase() !== "w") return;
    if (!testing) { testing = true; clicks = 0; start = performance.now(); }
    clicks++;
    const t = (performance.now() - start) / 1000;
    document.getElementById('cpsResult').textContent = `Clicks: ${clicks} | Time: ${t.toFixed(2)}s`;
    if (clicks >= 16 && t <= 1) {
      window.onkeydown = null;
      switchScreen('cpsScreen', 'goatScreen');
      startGoatScreen(); 
    } else if (t > 1) { testing = false; }
  };
}

function startGoatScreen() {
  const container = document.getElementById("goatScreen");
  // Clean up previous runs
  while (container.getElementsByTagName('img').length > 0) {
      container.getElementsByTagName('img')[0].remove();
  }
  goatClicks = 0;
  goatInputBuffer = "";
  document.getElementById("goatCount").innerText = "Clicks: 0";
  
  const goatInterval = setInterval(() => {
    if(container.classList.contains("hidden")) {
        clearInterval(goatInterval);
        return;
    }
    const img = document.createElement("img");
    img.src = LEBRON_IMG;
    img.style.left = Math.random() * (window.innerWidth - 100) + "px";
    img.style.top = Math.random() * (window.innerHeight - 100) + "px";
    img.onclick = (e) => {
        e.stopPropagation();
        img.remove();
        document.getElementById("goatCount").innerText = "Clicks: " + (++goatClicks);
    };
    container.appendChild(img);
  }, 600);
  window.addEventListener("keydown", goatKeyListener);
}

let goatClicks = 0, goatInputBuffer = "";
function goatKeyListener(e) {
  goatInputBuffer += e.key.toLowerCase();
  if(goatInputBuffer.includes("lebronisthegoat1")) {
    window.removeEventListener("keydown", goatKeyListener);
    switchScreen('goatScreen', 'login');
    startCountdown();
  }
}

let countdownTimer = null, countdownTime = 5;
function startCountdown() {
  countdownTime = 5; // Reset
  document.getElementById("countdown").textContent = countdownTime;
  document.getElementById('login').classList.remove('hidden');
  document.getElementById("code").value = "";
  
  countdownTimer = setInterval(() => {
    document.getElementById("countdown").textContent = --countdownTime;
    if (countdownTime <= 0) { clearInterval(countdownTimer); triggerMeltdown(); }
  }, 1000);
}

function checkCode() {
  clearInterval(countdownTimer);
  const codeVal = document.getElementById("code").value.toLowerCase();
  if (codeVal === CORRECT_CODE) {
      showLebron();
  } else { kickOut(); }
}

function showLebron() {
  // Hide login first
  document.getElementById('login').classList.add('hidden');
  const img = document.createElement("img");
  img.src = LEBRON_IMG;
  img.style.left = "50%"; img.style.top = "50%"; img.style.transform = "translate(-50%,-50%)";
  img.onclick = () => {
      img.remove();
      // Properly transition to Quiz
      const quiz = document.getElementById('quiz');
      quiz.classList.remove("hidden");
      quiz.classList.add("fade-in-page");
      q = 0; // Reset quiz index
      startQuiz();
  };
  document.body.appendChild(img);
}

let q = 0;
const questions = [
  { t: "Who is better?", l: "Curry", r: "LeBron" },
  { t: "Who is better?", l: "Jordan", r: "LeBron" },
  { t: "Who is better?", l: "LEFT", r: "RIGHT" }
];

function startQuiz() { renderQ(); }
function renderQ() {
  const quiz = document.getElementById('quiz');
  if (q >= questions.length) {
    // QUIZ COMPLETE - Go to Hub logic
    switchScreen('quiz', 'hubScreen');
    setupHubState();
    return;
  }
  quiz.innerHTML = `
    <h2>${questions[q].t}</h2>
    <button onclick="press(this, kickOut)">${questions[q].l}</button>
    <button onclick="press(this, () => { q++; renderQ(); })">${questions[q].r}</button>
  `;
}

// ===== NEW HUB LOGIC =====
function setupHubState() {
    const endingText = document.getElementById('hubEndings');
    const linksContainer = document.getElementById('hubLinksContainer');
    const continueBtn = document.getElementById('hubContinueBtn');
    const congratsText = document.getElementById('hubCongrats');

    if (gameStage === 0) {
        // FIRST ARRIVAL
        endingText.innerText = "Endings completed: 1/2";
        linksContainer.classList.add('hub-locked'); // Lock links
        continueBtn.classList.remove('hidden'); // Show continue
        congratsText.classList.add('hidden');
    } else if (gameStage === 1) {
       portalMusic.pause(); portalMusic.currentTime = 0;
 // FINAL ARRIVAL (After Dark Mode) - WIN CONDITION
        gameStage = 2; // Finished
        stopChaseTimer(); // STOP THE TIMER
        
        endingText.innerText = "Endings completed: 2/2";
        linksContainer.classList.remove('hub-locked'); // Unlock links
        continueBtn.classList.add('hidden'); // Hide continue
        congratsText.classList.remove('hidden'); // Show congrats
        
        // Return to original theme
        document.body.classList.remove('dark-mode');
        // Stop yellow flash
        clearInterval(flashInterval);
    }
}

// ===== CHASE TIMER LOGIC =====
let chaseInterval;
let chaseStartTime;
// UPDATED: 1 min 10 seconds = 70 seconds = 70000 ms
const CHASE_DURATION = 70000; 

function startChaseTimer() {
    const ui = document.getElementById('chaseUI');
    const timerText = document.getElementById('chaseTimerText');
    const chaseIcon = document.getElementById('chaseIcon');
    
    ui.classList.remove('hidden');
    chaseStartTime = performance.now();
    
    chaseInterval = setInterval(() => {
        const elapsed = performance.now() - chaseStartTime;
        const remaining = CHASE_DURATION - elapsed;
        
        if (remaining <= 0) {
            clearInterval(chaseInterval);
            timerText.innerText = "00:00:00";
            triggerCaughtEnding();
            return;
        }
        
        // Format Time (MM:SS:MS)
        const mins = Math.floor(remaining / 60000);
        const secs = Math.floor((remaining % 60000) / 1000);
        const ms = Math.floor((remaining % 1000) / 10);
        
        timerText.innerText = `${mins < 10 ? '0'+mins : mins}:${secs < 10 ? '0'+secs : secs}:${ms < 10 ? '0'+ms : ms}`;
        
        // Move LeBron Head
        const percent = Math.min(100, (elapsed / CHASE_DURATION) * 100);
        chaseIcon.style.left = percent + "%";
        
    }, 30);
}

function stopChaseTimer() {
    clearInterval(chaseInterval);
    document.getElementById('chaseUI').classList.add('hidden');
}

function triggerCaughtEnding() {
   portalMusic.pause(); portalMusic.currentTime = 0;
 // Remove UI
    document.getElementById('chaseUI').classList.add('hidden');
    // Show Caught Screen
    const caught = document.getElementById('caughtScreen');
    caught.classList.remove('hidden');
    
    // Number spam
    const numBg = document.getElementById('caughtNumbers');
    const spam = setInterval(() => {
        numBg.innerText += Math.random().toString().substring(2);
        if(numBg.innerText.length > 5000) numBg.innerText = "";
    }, 50);
    
    // Crash
    setTimeout(() => {
        clearInterval(spam);
        location.href = "about:blank";
    }, 3000);
}

function triggerAngeredPhase() {
    portalMusic.play();
// START THE TIMER IMMEDIATELY
    startChaseTimer();
    
    // 1. Switch to Angered Screen
    switchScreen('hubScreen', 'angeredScreen');
    
    // 2. Wait 10 seconds
    setTimeout(() => {
        // 3. Switch to Menu Screen, Activate Dark Mode
        switchScreen('angeredScreen', 'menuScreen');
        document.body.classList.add('dark-mode');
        gameStage = 1;
        
        // Modify Menu Buttons
        const startBtn = document.getElementById('menuStartBtn');
        const finaleBtn = document.getElementById('menuFinaleBtn');
        
        startBtn.classList.add('broken-btn');
        startBtn.onclick = null; // Unclickable
        
        finaleBtn.classList.remove('hidden'); // Show Finale
        
        // Start Yellow Flash Interval
        startYellowFlash();
        
    }, 10000);
}

let flashInterval;
function startYellowFlash() {
    const flashEl = document.getElementById('yellowFlash');
    flashInterval = setInterval(() => {
        flashEl.style.opacity = "1";
        setTimeout(() => { flashEl.style.opacity = "0"; }, 500); // 0.5s duration
    }, 10000);
}

function startFinale() {
    // Loop back to key game, but keep dark mode active
    switchScreen('menuScreen', 'googleSignIn');
}

function kickOut() {
  document.body.classList.add("earthquake");
  spawnLebrons(20);
  setTimeout(() => location.href = "about:blank", 2000);
}

function spawnLebrons(n) {
  for (let i = 0; i < n; i++) {
    const img = document.createElement("img");
    img.src = LEBRON_IMG;
    img.style.left = Math.random() * innerWidth + "px";
    img.style.top = Math.random() * innerHeight + "px";
    document.body.appendChild(img);
  }
}

function openHideout() {
  const win = window.open("about:blank", "_blank");
  win.document.write(`<html><head><title>Google Docs</title><style>html,body,iframe{margin:0;width:100%;height:100%;border:none;}</style></head><body><iframe src="https://hideout-now.lovable.app/" allowfullscreen></iframe></body></html>`);
  win.document.close();
}

function openGame(url) {
  const win = window.open("about:blank", "_blank");
  win.document.write(`<html><head><title>Google Docs</title><style>html,body,iframe{margin:0;width:100%;height:100%;border:none;}</style></head><body><iframe src="${url}" allowfullscreen></iframe></body></html>`);
  win.document.close();
}

function triggerMeltdown() {
  document.body.classList.add("earthquake", "glitch");
  setTimeout(() => location.href = "about:blank", 1500);
}
// --- AUDIO CONFIGURATION ---
// This takes your Google Drive ID and turns it into a streamable link
const musicUrl = "https://docs.google.com/uc?export=download&id=1wcYK39SGW-Gmag1d8wnSFNZhIzbP1Me6";
const portalMusic = new Audio(musicUrl);
portalMusic.loop = true;
portalMusic.volume = 0.6;

// Function to stop music completely
function stopPortalMusic() {
    portalMusic.pause();
    portalMusic.currentTime = 0;
}
</script>

</body>
</html>
