


> **Note:** The animated version below uses raw HTML, CSS and JavaScript embedded in Markdown. It runs in Markdown viewers that allow inline `<script>`/`<style>` (e.g. VS Code's Markdown preview, many static-site generators). If your Markdown host strips scripts (e.g. GitHub README), use the **Plain Markdown fallback** at the end of this file.

<!-- =========================
     Animated Matrix Terminal
     ========================= -->
<div class="matrix-terminal-wrapper" aria-hidden="false">
  <canvas id="matrixCanvas"></canvas>

  <div class="terminal-window" role="region" aria-label="Matrix terminal demo">
    <pre id="terminalOutput" aria-live="polite"></pre><span id="cursor">█</span>
  </div>
</div>

<style>
/* Container sizing - keeps the demo compact inside Markdown */
.matrix-terminal-wrapper {
  position: relative;
  width: 100%;
  max-width: 900px;
  height: 360px;
  margin: 0.6em auto;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(0,0,0,0.6);
  background: #000;
  font-family: "SFMono-Regular", Menlo, Monaco, "Courier New", monospace;
}

/* Canvas fills container */
.matrix-terminal-wrapper canvas {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  display: block;
}

/* Terminal overlay */
.terminal-window {
  position: absolute;
  inset: 16px;
  background: rgba(0,0,0,0.35);
  border-radius: 6px;
  padding: 12px;
  box-sizing: border-box;
  color: #8efc6e;
  font-size: 14px;
  line-height: 1.35;
  overflow: hidden;
  display: flex;
  align-items: flex-start;
  gap: 6px;
}

/* The typed text */
#terminalOutput {
  margin: 0;
  white-space: pre-wrap;
  word-break: break-word;
  flex: 1 1 auto;
}

/* Blinking cursor */
#cursor {
  color: #8efc6e;
  font-weight: 700;
  animation: blink 1s steps(2) infinite;
  margin-left: 2px;
}
@keyframes blink { 50% { opacity: 0; } }

/* Make sure canvas text is subtle behind terminal */
.matrix-terminal-wrapper::after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, rgba(0,0,0,0.0) 30%, rgba(0,0,0,0.55) 100%);
  pointer-events: none;
}
</style>

<script>
(() => {
  // Matrix rain
  const canvas = document.getElementById('matrixCanvas');
  const ctx = canvas.getContext('2d');

  function resize() {
    const rect = canvas.getBoundingClientRect();
    canvas.width = rect.width * devicePixelRatio;
    canvas.height = rect.height * devicePixelRatio;
    canvas.style.width = rect.width + 'px';
    canvas.style.height = rect.height + 'px';
    ctx.setTransform(devicePixelRatio, 0, 0, devicePixelRatio, 0, 0);
    initColumns();
  }

  let fontSize = 14;
  let columns, drops;
  function initColumns() {
    const width = canvas.clientWidth;
    columns = Math.floor(width / fontSize) + 1;
    drops = new Array(columns).fill(0).map(() => Math.floor(Math.random() * canvas.clientHeight));
  }

  const katakana = 'アァカサタナハマヤャラワガザダバパイィキシチニヒミリヰギジヂビピウゥクスツヌフムユュルグズヅブプエェケセテネヘメレヱゲゼデベペオォコソトノホモヨョロゴゾドボポヴ0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz';
  function draw() {
    const width = canvas.clientWidth;
    const height = canvas.clientHeight;

    ctx.fillStyle = 'rgba(0,0,0,0.075)';
    ctx.fillRect(0, 0, width, height);

    ctx.font = fontSize + 'px monospace';
    for (let i = 0; i < columns; i++) {
      const text = katakana.charAt(Math.floor(Math.random() * katakana.length));
      const x = i * fontSize;
      const y = drops[i] * fontSize;

      // Leading bright glyph
      ctx.fillStyle = 'rgba(180,255,180,0.95)';
      ctx.fillText(text, x, y);

      // Slightly faded glyph behind
      ctx.fillStyle = 'rgba(80,200,80,0.65)';
      ctx.fillText(text, x, y - fontSize);

      drops[i]++;
      if (drops[i] * fontSize > height + Math.random() * 1000) {
        drops[i] = 0;
      }
    }
  }

  // Typing terminal
  const terminal = document.getElementById('terminalOutput');
  const cursor = document.getElementById('cursor');

  const scriptLines = [
    'guest@neo:~$ whoami',
    'guest',
    'guest@neo:~$ echo "Welcome to command-line 101"',
    'Welcome to command-line 101',
    'guest@neo:~$ ls -la',
    'total 32',
    '-rw-r--r-- 1 guest staff  142 Dec 17  2025 README.md',
    'drwxr-xr-x 6 guest staff  192 Dec 17  2025 lab1',
    'guest@neo:~$ cat README.md',
    'Learning the command line gives you superpowers: navigation, automation, debugging.',
    '',
    '# Tips:',
    ' - Start simple: cd, ls, cat, mkdir, rm (careful!)',
    ' - Combine commands with pipes: grep, awk, sed',
    ' - Use the terminal to automate repetitive tasks',
    '',
    'guest@neo:~$ _' // trailing underscore to simulate prompt
  ];

  let lineIndex = 0;
  let charIndex = 0;
  let typing = true;

  function typeNextChar() {
    if (lineIndex >= scriptLines.length) {
      // loop a gentle pause and then restart
      setTimeout(() => {
        terminal.textContent = '';
        lineIndex = 0;
        charIndex = 0;
      }, 3000);
      return;
    }
    const currentLine = scriptLines[lineIndex];
    if (charIndex <= currentLine.length) {
      // update displayed text (including new line if finished)
      const before = scriptLines.slice(0, lineIndex).join('\n');
      const partial = currentLine.slice(0, charIndex);
      terminal.textContent = (before ? before + '\n' : '') + partial;
      charIndex++;
    } else {
      // move to next line after a short pause
      lineIndex++;
      charIndex = 0;
      setTimeout(typeNextChar, 220 + Math.random() * 350);
      return;
    }
    setTimeout(typeNextChar, 22 + Math.random() * 28);
  }

  // Kick things off
  let matrixInterval;
  function start() {
    resize();
    if (matrixInterval) clearInterval(matrixInterval);
    matrixInterval = setInterval(draw, 45);
    typeNextChar();
  }

  // Responsive
  let resizeTimer;
  window.addEventListener('resize', () => {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(resize, 120);
  });

  // initialize
  document.addEventListener('DOMContentLoaded', start);
  // also try immediate start in case DOMContentLoaded already fired
  if (document.readyState === 'complete' || document.readyState === 'interactive') start();
})();
</script>

<!-- =========================
     Plain Markdown fallback
     ========================= -->




