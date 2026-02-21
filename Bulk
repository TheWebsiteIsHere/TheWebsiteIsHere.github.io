<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SystemOS // Secure Environment</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">

<style>
:root {
    --bg-color: #0f172a;
    --bg-gradient: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
    --glass-bg: rgba(255, 255, 255, 0.03);
    --glass-border: rgba(255, 255, 255, 0.08);
    --text-main: #f8fafc;
    --text-muted: #94a3b8;
    --primary: #3b82f6;
    --danger: #ef4444;
}

body {
    margin: 0;
    background: var(--bg-gradient);
    background-attachment: fixed;
    color: var(--text-main);
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
}

.glass-panel {
    background: var(--glass-bg);
    backdrop-filter: blur(16px);
    border: 1px solid var(--glass-border);
    border-radius: 16px;
}

.container { width: 90%; max-width: 1000px; margin: 80px auto 40px auto; padding: 40px; }

#terminalUnlock { max-width: 400px; margin: 40px auto; padding: 30px; text-align: center; }
#restrictedUI { display: none; } 

input, select, textarea {
    background: rgba(0, 0, 0, 0.2);
    border: 1px solid var(--glass-border);
    color: var(--text-main);
    padding: 12px;
    margin: 8px 0;
    border-radius: 8px;
    width: 100%;
    box-sizing: border-box;
}

button {
    background: var(--primary);
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 8px;
    font-weight: 600;
    cursor: pointer;
}

button:hover { filter: brightness(1.2); }

.utility-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 20px; }
.util-box { background: rgba(0,0,0,0.2); padding: 20px; border-radius: 12px; border: 1px solid var(--glass-border); }
.calc-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 5px; }

#topWarning { 
    position: fixed; top: 0; width: 100%; background: rgba(15, 23, 42, 0.8); 
    backdrop-filter: blur(10px); border-bottom: 1px solid var(--glass-border); 
    padding: 12px 25px; z-index: 9000; display: flex; justify-content: space-between; box-sizing: border-box;
}

#doomButton { display: block; width: 100%; background: var(--danger); margin-bottom: 20px; font-size: 1.1rem; }
</style>
</head>
<body onload="checkSession()">

<div id="topWarning">
    <div>SystemOS Active // Ping: <span id="pingVal">0</span>ms</div>
    <div id="userTag" style="color: var(--primary); font-weight: 800;"></div>
</div>

<div class="container glass-panel">
    <button id="doomButton" onclick="initiateDoomProtocol()">Initiate System Restart</button>
    
    <h1>Session ID: SYS-9291-X</h1>

    <div id="terminalUnlock" class="glass-panel">
        <h2>Authentication Required</h2>
        <div id="hidDisplay" style="font-family: monospace; font-size: 0.75rem; color: var(--primary); margin-bottom: 10px; opacity: 0.7;">LOCAL HID: GENERATING...</div>
        
        <input type="text" id="termUser" placeholder="Username">
        <input type="password" id="termPass" placeholder="Password">
        <button onclick="authenticate()" style="width: 100%; margin-top: 10px;">Sign In</button>
        <div style="margin-top:15px;">
            <a href="https://docs.google.com/forms/d/e/1FAIpQLSeYxfLDahq7S3e4vjQMj8HWPZTeQVa4B99BzmLXVDZHaV6p0A/viewform" target="_blank" style="color: var(--text-muted); text-decoration: none; font-size: 0.85rem;">Request Credentials</a>
        </div>
    </div>

    <div id="restrictedUI">
        <div style="margin-bottom: 20px;">
            <button onclick="logout()" style="background: var(--danger);">Logout</button>
        </div>

        <div class="util-box" style="margin-bottom: 20px;">
            <h2>Remote Gateway & Launchers (Stealth Mode)</h2>
            <div style="display: flex; gap: 10px; margin-bottom: 10px;">
                <input type="text" id="linkInput" placeholder="Enter URL to cloak...">
                <button onclick="stealthLaunch(document.getElementById('linkInput').value)">Connect</button>
                <button onclick="toggleLinks()" style="background: #6366f1;">Popular Links</button>
            </div>
            <div style="display: flex; gap: 10px; margin-bottom: 10px;">
                <input type="file" id="fileInput">
                <button onclick="launchFile()">Execute</button>
            </div>
            <div style="display: flex; gap: 10px;">
                <input type="text" id="ytInput" placeholder="Media/YouTube link...">
                <button onclick="stealthLaunch(document.getElementById('ytInput').value)">Stream</button>
            </div>
        </div>

        <div class="util-box">
            <h3>Elementary Experiment: System Log</h3>
            <p style="color: var(--text-muted); font-size: 0.95rem;">
                Historical data indicates an anomaly during this cycle. Access to entertainment protocols was restricted. System intelligence was currently rated at Level 1.
            </p>
        </div>

        <div class="utility-grid">
            <div class="util-box">
                <h3>Speech Articulation (SAM)</h3>
                <textarea id="samInput" rows="2" placeholder="Synthesis input..."></textarea>
                <button onclick="runSAM()" style="width:100%">Synthesize</button>
            </div>

            <div class="util-box">
                <h3>Cryptographic Tool</h3>
                <select id="cryptType"><option value="b64">Base64</option><option value="rot">ROT13</option></select>
                <textarea id="cryptInput" rows="2" placeholder="Input text..."></textarea>
                <button onclick="runCrypto()" style="width:100%">Process</button>
            </div>

            <div class="util-box">
                <h3>Compute Module</h3>
                <input type="text" id="calcDisp" readonly style="text-align: right; font-family: monospace;">
                <div class="calc-grid">
                    <button onclick="cAdd('7')">7</button><button onclick="cAdd('8')">8</button><button onclick="cAdd('9')">9</button><button onclick="cAdd('/')">/</button>
                    <button onclick="cAdd('4')">4</button><button onclick="cAdd('5')">5</button><button onclick="cAdd('6')">6</button><button onclick="cAdd('*')">*</button>
                    <button onclick="cAdd('1')">1</button><button onclick="cAdd('2')">2</button><button onclick="cAdd('3')">3</button><button onclick="cAdd('-')">-</button>
                    <button onclick="cAdd('0')">0</button><button onclick="cClear()" style="background:var(--danger)">C</button><button onclick="cEval()" style="background:var(--primary)">=</button><button onclick="cAdd('+')">+</button>
                </div>
            </div>

            <div class="util-box">
                <h3>Signal Generator</h3>
                <input type="number" id="freqIn" value="440">
                <button id="toneBtn" onclick="toggleTone()" style="width:100%">Start Sine Wave</button>
            </div>
        </div>
    </div>
</div>

<div id="linkModal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.85); z-index:10001; justify-content:center; align-items:center;">
    <div class="glass-panel" style="padding:30px; width:350px; background: #1e293b; border: 1px solid var(--primary); max-height: 80vh; overflow-y: auto;">
        <h3 style="text-align:center;">Directory</h3>
        <input type="text" id="linkSearch" onkeyup="filterLinks()" placeholder="Search addresses..." style="margin-bottom:15px; border-color: var(--primary);">
        <ul id="linkList" style="list-style:none; padding:0; margin:0; text-align:left;">
            <li class="link-item" style="padding:10px; border-bottom:1px solid var(--glass-border); color:var(--primary); font-family: monospace; font-size: 0.9rem;">
                https://viewoncloud.com
            </li>
        </ul>
        <button onclick="toggleLinks()" style="width:100%; background:var(--danger); margin-top:20px;">CLOSE</button>
    </div>
</div>

<script>
// USERS DATA - p = Base64 Password, m = Chromebook/Hardware ID
const _0x1a2b = {
    "ADMIN": { p: "cmVkYWN0ZWQ=", m: "9999" }, 
    "JOHN":  { p: "cGl6emExMjM=", m: "1234" }
};

function getHID() {
    let s = screen.width + "x" + screen.height + navigator.hardwareConcurrency + navigator.platform;
    let hash = 0;
    for (let i = 0; i < s.length; i++) { hash = ((hash << 5) - hash) + s.charCodeAt(i); hash |= 0; }
    return Math.abs(hash % 10000).toString().padStart(4, '0');
}
const localHID = getHID();
document.getElementById('hidDisplay').innerText = "LOCAL HID: " + localHID;

function checkSession() {
    const active = localStorage.getItem('sys_session');
    if (active) loginSuccess(active);
}

function authenticate() {
    const u = document.getElementById('termUser').value.toUpperCase();
    const p = document.getElementById('termPass').value;
    
    // Strict Check: User exists, Password matches, AND HID matches. 
    if (_0x1a2b[u] && _0x1a2b[u].p === btoa(p) && _0x1a2b[u].m === localHID) {
        localStorage.setItem('sys_session', u);
        loginSuccess(u);
    } else {
        // ONE STRIKE POLICY: Immediate lockout on any failure.
        triggerLockout();
    }
}

function loginSuccess(user) {
    document.getElementById('terminalUnlock').style.display = 'none';
    document.getElementById('restrictedUI').style.display = 'block';
    document.getElementById('userTag').innerText = "IDENT: " + user;
}

function logout() { 
    localStorage.removeItem('sys_session');
    location.reload(); 
}

function triggerLockout() {
    const audioCtx = new AudioContext();
    document.body.innerHTML = `
        <div style="height:100vh; width:100vw; background:#050505; display:flex; justify-content:center; align-items:center; color:#ef4444; text-align:center; overflow:hidden;">
            <div style="border:4px solid #ef4444; padding:60px; border-radius:20px; animation: scarierPulse 0.3s infinite, shake 0.2s infinite;">
                <h1 style="font-size:4rem; color:white; margin:0; text-shadow: 0 0 30px #ef4444;">SYSTEM LOCKED</h1>
                <p style="font-size:1.2rem; font-family:monospace; margin-top:20px;">SECURITY THRESHOLD EXCEEDED // SESSION VOIDED</p>
            </div>
            <style>
                @keyframes scarierPulse { 50% { box-shadow: 0 0 100px #ef4444; background: rgba(239,68,68,0.3); } }
                @keyframes shake { 0% { transform: translate(3px, 3px); } 25% { transform: translate(-3px, -3px); } 50% { transform: translate(-3px, 3px); } 75% { transform: translate(3px, -3px); } 100% { transform: translate(0,0); } }
            </style>
        </div>`;
    const msg = new SpeechSynthesisUtterance("Security threshold exceeded. System lockout engaged.");
    msg.pitch = 0.1; msg.rate = 0.8;
    window.speechSynthesis.speak(msg);
    try {
        const gain = audioCtx.createGain();
        const osc1 = audioCtx.createOscillator();
        const drone = audioCtx.createOscillator();
        osc1.type = 'sawtooth'; drone.type = 'square';
        osc1.frequency.value = 853; drone.frequency.value = 40;
        gain.gain.value = 0.5;
        osc1.connect(gain); drone.connect(gain);
        gain.connect(audioCtx.destination);
        osc1.start(); drone.start();
    } catch(e) {}
}

function initiateDoomProtocol() {
    document.body.innerHTML = `<div style="height:100vh; background:#000; color:#fff; display:flex; flex-direction:column; justify-content:center; align-items:center; font-family:monospace;"><h1>Updating System... 0%</h1><p>Please do not turn off your computer.</p></div>`;
}

function stealthLaunch(url) {
    if (!url) return;
    if (!url.startsWith('http')) url = 'https://' + url;
    const win = window.open('about:blank', '_blank');
    if(!win) { alert("Enable popups to use the launcher."); return; }
    win.document.write(`<html><head><title>[REDACTED]</title><style>body,iframe{margin:0;padding:0;width:100%;height:100%;border:none;overflow:hidden;}</style></head><body><iframe src="${url}"></iframe></body></html>`);
}

function launchFile() {
    const file = document.getElementById('fileInput').files[0];
    if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
            const win = window.open('about:blank', '_blank');
            win.document.write(`<html><head><title>Process</title></head><body style="margin:0;"><iframe src="${e.target.result}" style="width:100%;height:100%;border:none;"></iframe></body></html>`);
        };
        reader.readAsDataURL(file);
    }
}

function runSAM() { window.speechSynthesis.speak(new SpeechSynthesisUtterance(document.getElementById('samInput').value)); }
function runCrypto() {
    let i = document.getElementById('cryptInput').value;
    let t = document.getElementById('cryptType').value;
    if(t === 'b64') document.getElementById('cryptInput').value = btoa(i);
    else document.getElementById('cryptInput').value = i.replace(/[a-zA-Z]/g, c => String.fromCharCode((c<="Z"?90:122)>=(c=c.charCodeAt(0)+13)?c:c-26));
}
function cAdd(v) { document.getElementById('calcDisp').value += v; }
function cClear() { document.getElementById('calcDisp').value = ""; }
function cEval() { try { document.getElementById('calcDisp').value = eval(document.getElementById('calcDisp').value); } catch(e) { document.getElementById('calcDisp').value = "ERR"; } }

let tCtx, tOsc, tOn = false;
function toggleTone() {
    if(!tCtx) tCtx = new AudioContext();
    if(tOn) { tOsc.stop(); tOn = false; document.getElementById('toneBtn').innerText = "Start Tone"; }
    else { 
        tOsc = tCtx.createOscillator(); 
        tOsc.frequency.value = document.getElementById('freqIn').value;
        tOsc.connect(tCtx.destination); 
        tOsc.start(); tOn = true; 
        document.getElementById('toneBtn').innerText = "Stop Tone";
    }
}

setInterval(() => { document.getElementById('pingVal').innerText = Math.floor(Math.random()*15+10); }, 2000);

function toggleLinks() {
    const modal = document.getElementById('linkModal');
    modal.style.display = (modal.style.display === "none" || modal.style.display === "") ? "flex" : "none";
}

function filterLinks() {
    let input = document.getElementById('linkSearch').value.toUpperCase();
    let ul = document.getElementById("linkList");
    let li = ul.getElementsByClassName('link-item');
    for (let i = 0; i < li.length; i++) {
        let text = li[i].innerText || li[i].textContent;
        li[i].style.display = (text.toUpperCase().indexOf(input) > -1) ? "" : "none";
    }
}
</script>
</body>
</html>
