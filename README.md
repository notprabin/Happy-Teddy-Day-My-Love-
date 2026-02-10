<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Teddy Day 🧸</title>

<!-- Signature font -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">

<style>
body{
  margin:0;
  background:#800000;
  overflow:hidden;
  font-family:'Pacifico', cursive;
  text-align:center;
}

/* Screens */
.screen{
  display:none;
  position:absolute;
  inset:0;
  justify-content:center;
  align-items:center;
  flex-direction:column;
}
.active{ display:flex; }

h1, p{
  color:#000;
  z-index:5;
}

h1{
  font-size:2.8em;
}

p{
  font-size:1.4em;
}

/* Buttons */
button{
  padding:15px 40px;
  font-size:1.3em;
  border:none;
  border-radius:40px;
  cursor:pointer;
  margin:15px;
  position:relative;
  transition:none; /* no movement effect */
}

.yes{ background:#ff69b4; }
.no{ background:#ffb6c1; }

/* Name glow */
.name{
  font-size:3.2em;
  animation:pulse 1.5s infinite;
}

@keyframes pulse{
  0%{ text-shadow:0 0 5px pink; }
  50%{ text-shadow:0 0 25px hotpink; }
  100%{ text-shadow:0 0 5px pink; }
}

/* Fireworks */
.firework{
  position:absolute;
  font-size:40px;
  animation:boom 1s ease-out forwards;
}

@keyframes boom{
  from{ transform:scale(0); }
  to{ transform:scale(2); opacity:0; }
}

/* Floating hearts and teddies */
.emoji{
  position:absolute;
  font-size:30px;
  animation:float 10s linear infinite;
  opacity:0.8;
}

@keyframes float{
  0%{transform:translateY(100vh);}
  100%{transform:translateY(-10vh);}
}
</style>
</head>

<body>

<!-- Romantic music -->
<audio autoplay loop>
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_5a2c6f8e61.mp3">
</audio>

<!-- Floating emojis -->
<script>
const emojis = ["🧸","💖","❤️"];
for(let i=0;i<25;i++){
  let e = document.createElement("div");
  e.className="emoji";
  e.style.left=Math.random()*100+"vw";
  e.style.fontSize = (20+Math.random()*30) + "px";
  e.innerHTML = emojis[Math.floor(Math.random()*emojis.length)];
  document.body.appendChild(e);
}
</script>

<!-- Screen 1 -->
<div class="screen active" id="s1">
  <h1>Happy Teddy Day 🧸<br><span class="name">Jenika</span></h1>
  <p>Do you want to continue?</p>
  <button class="yes" id="yes1">YES</button>
  <button class="no" id="no1">NO</button>
</div>

<!-- Screen 2 -->
<div class="screen" id="s2">
  <h1>Sorry my love 💖<br>
  I am not there to give you a teddy bear<br>
  But sending lots of love to you ❤️</h1>
  <button class="yes" id="yes2">OK</button>
</div>

<!-- Screen 3 -->
<div class="screen" id="s3">
  <h1>
    This teddy carries my hugs, my love, and my heart 🧸❤️<br><br>
    For my Jenika — always 💖
  </h1>
</div>

<script>
/* Screen 1 → 2 */
yes1.onclick = () => {
  s1.classList.remove("active");
  s2.classList.add("active");
};

/* Screen 2 → 3 */
yes2.onclick = () => {
  s2.classList.remove("active");
  s3.classList.add("active");
  fireworks();
};

/* Fireworks */
function fireworks(){
  for(let i=0;i<15;i++){
    let f = document.createElement("div");
    f.className = "firework";
    f.innerHTML = "🎆";
    f.style.left = Math.random()*100 + "vw";
    f.style.top = Math.random()*100 + "vh";
    document.body.appendChild(f);
    setTimeout(()=>f.remove(),1000);
  }
}
</script>

</body>
</html>
