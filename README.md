<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Death Note Theme Website</title>
  <style>
    body {
      margin: 0;
      font-family: "Georgia", serif;
      background: radial-gradient(circle at top, #1a1a1a, #000000 70%);
      color: #e5e5e5;
    }

    header {
      min-height: 100vh;
      background:
        linear-gradient(rgba(0,0,0,0.75), rgba(0,0,0,0.95)),
        url('https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&w=1500&q=80');
      background-size: cover;
      background-position: center;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 20px;
    }

    header h1 {
      font-size: 3.5rem;
      letter-spacing: 4px;
      margin-bottom: 10px;
    }

    header p {
      font-size: 1.2rem;
      color: #b91c1c;
      letter-spacing: 2px;
    }

    section {
      max-width: 900px;
      margin: 60px auto;
      padding: 0 20px;
    }

    .card {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.1);
      padding: 25px;
      border-radius: 10px;
      box-shadow: 0 0 30px rgba(0,0,0,0.6);
      margin-bottom: 30px;
      backdrop-filter: blur(6px);
    }

    .card h2 {
      color: #dc2626;
      letter-spacing: 2px;
      margin-bottom: 10px;
    }

    footer {
      text-align: center;
      padding: 25px;
      background: #000;
      color: #9ca3af;
      font-size: 0.9rem;
      letter-spacing: 1px;
    }

    .quote {
      font-style: italic;
      text-align: center;
      margin-top: 40px;
      color: #fca5a5;
    }
  
    /* Falling Death Note animation */
    .note {
      position: fixed;
      top: -50px;
      color: rgba(220,38,38,0.8);
      font-size: 14px;
      animation: fall linear infinite;
      pointer-events: none;
      z-index: 0;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh);
        opacity: 0;
      }
    }

    /* Split section */
    .split {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }

    @media(max-width:768px){
      .split{grid-template-columns:1fr}
    }
  
    /* Floating apples (Ryuk style) */
    .apple {
      position: fixed;
      top: -60px;
      font-size: 22px;
      animation: appleFall linear infinite;
      pointer-events: none;
      z-index: 1;
    }

    @keyframes appleFall {
      to {
        transform: translateY(120vh) rotate(360deg);
        opacity: 0;
      }
    }
  
    /* Cinematic intro */
    #intro {
      position: fixed;
      inset: 0;
      background: black;
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      animation: introFade 5s forwards;
    }

    .intro-text {
      color: #dc2626;
      font-size: 3rem;
      letter-spacing: 4px;
      font-family: 'Georgia', serif;
      animation: typing 2s steps(10), blink .7s step-end infinite alternate;
      border-right: 2px solid #dc2626;
      white-space: nowrap;
      overflow: hidden;
      width: 8ch;
    }

    @keyframes typing {
      from { width: 0 }
      to { width: 8ch }
    }

    @keyframes blink {
      50% { border-color: transparent }
    }

    @keyframes introFade {
      0% { opacity: 1 }
      70% { opacity: 1 }
      100% { opacity: 0; visibility: hidden }
    }
  </style>
</head>
<body>
  <div id="intro">
    <div class="intro-text">I am Kira.</div>
  </div>
  <script>
    // Remove intro after animation
    setTimeout(() => {
      const intro = document.getElementById('intro');
      if(intro) intro.remove();
    }, 5200);

    // Falling Death Notes
    const words = ['DEATH NOTE','KIRA','JUSTICE'];
    setInterval(() => {
      const note = document.createElement('div');
      note.className = 'note';
      note.innerText = words[Math.floor(Math.random()*words.length)];
      note.style.left = Math.random()*100 + 'vw';
      note.style.animationDuration = 5 + Math.random()*5 + 's';
      document.body.appendChild(note);
      setTimeout(()=>note.remove(),10000);
    }, 400);

    // Floating Apples 🍎
    setInterval(() => {
      const apple = document.createElement('div');
      apple.className = 'apple';
      apple.innerText = '🍎';
      apple.style.left = Math.random()*100 + 'vw';
      apple.style.animationDuration = 6 + Math.random()*6 + 's';
      document.body.appendChild(apple);
      setTimeout(()=>apple.remove(),12000);
    }, 700);
  </script>

  <header>
    <div>
      <h1>KIRA</h1>
      <p>"I will become the god of the new world."</p>
    </div>
  </header>

  <section>
    <div class="card">
      <h2>About</h2>
      <p>This website is inspired by the dark, psychological theme of Death Note. Power, justice, and morality collide in a world ruled by intellect.</p>
    </div>

    <div class="card">
        <h2>Kira's Justice</h2>
        <p>I am justice. I stand at the top of the world. Those who oppose me are evil, and those who follow me are righteous.</p>
        <p>This world will be reborn through fear, order, and absolute judgment.</p>
      </div>

      <div class="card">
        <h2>L</h2>
        <p>Justice must follow law and truth. No one has the right to play god.</p>
      </div>
    </div>

    <div class="card">
      <h2>Contact</h2>
      <p>Enter at your own risk. Only those who seek truth should reach out.</p>
    </div>

    <p class="quote">— Justice will prevail, you say? But of course it will… whoever wins becomes justice.</p>
  </section>

  <footer>
    <p>© 2026 Kira | God of the New World</p>
  </footer>

</body>
</html>

