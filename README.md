<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<!-- FONTS -->
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>

/* FULL SCREEN FIX */
html, body {
    width: 100%;
    height: 100%;
    overflow-x: hidden;
}

/* RESET */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* BACKGROUND */
body {
    font-family: 'Poppins', sans-serif;
    color: white;
    text-align: center;
}

/* IMAGE BACKGROUND */
body::before {
    content: "";
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: url("bg1.jpg") no-repeat center center;
    background-size: cover;
    filter: blur(2px);
    z-index: -2;
}

/* DARK OVERLAY */
body::after {
    content: "";
    position: fixed;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.6);
    z-index: -1;
}

/* SECTIONS */
section {
    width: 100%;
    height: 100vh;
    display: none;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
    opacity: 0;
    transition: opacity 1s;
}

section.active {
    display: flex;
    opacity: 1;
}

#lock {
    display: flex;
    opacity: 1;
}

/* TEXT */
h1 {
    font-family: 'Great Vibes', cursive;
    font-size: 3.5em;
    margin-bottom: 20px;
    text-shadow: 0 0 15px rgba(255,255,255,0.6);
}

p {
    max-width: 600px;
    font-size: 1.2em;
    line-height: 1.8;
    opacity: 0.9;
}

/* BUTTON */
button {
    margin-top: 25px;
    padding: 12px 25px;
    border-radius: 25px;
    border: none;
    background: rgba(255,255,255,0.9);
    color: black;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}

/* INPUT */
input {
    margin-top: 15px;
    padding: 10px;
    border-radius: 10px;
    border: none;
}

/* IMAGES */
.photo {
    width: 260px;
    border-radius: 15px;
    margin-top: 20px;
    display: none;
    box-shadow: 0 0 25px rgba(255,255,255,0.3);
}

/* VIDEO */
video {
    width: 300px;
    border-radius: 15px;
    margin-top: 20px;
}

/* FINAL SCENE */
#end {
    background: rgba(0,0,0,0.8);
}

#finalText {
    font-size: 2.2em;
    max-width: 700px;
    text-shadow: 0 0 20px rgba(255,255,255,0.7);
}

/* HEARTS */
.heart {
    position: fixed;
    color: pink;
    animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
}

</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
    <h1>This is not just a website</h1>
    <p>It is something I made for you</p>

    <input type="password" id="pass">
    <p style="margin-top:10px; opacity:0.7;">
        Hint: Who is better for Akanksha over Yogesh???
    </p>

    <button onclick="check()">Enter</button>
</section>

<!-- MAIN -->
<div id="main">

<section id="s1">
    <h1 id="typing"></h1>
    <button onclick="next('s2')">Continue</button>
</section>

<section id="s2">
    <p>You changed my life in a way I never expected.</p>
    <button onclick="reveal('m1')">Tap to reveal memory</button>
    <img src="Ira3.jpg" id="m1" class="photo">
    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3">
    <p>You became the person I go to without thinking.</p>
    <button onclick="reveal('m2')">Tap to reveal memory</button>
    <img src="Ira1.jpg" id="m2" class="photo">
    <button onclick="next('s4')">Continue</button>
</section>

<section id="s4">
    <p>These moments meant more than I ever said.</p>
    <video controls>
        <source src="Ira Video.mp4" type="video/mp4">
    </video>
    <button onclick="next('s5')">Continue</button>
</section>

<section id="s5">
    <p>It is not just the big memories. It is everything in between.</p>
    <button onclick="reveal('m3')">Tap to reveal memory</button>
    <img src="Ira2.jpg" id="m3" class="photo">
    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6">
    <p>You are not just my best friend. You are my safe place.</p>
    <button onclick="reveal('m4')">Tap to reveal</button>
    <img src="Ira 7.jpeg" id="m4" class="photo">
    <button onclick="next('end')">Last</button>
</section>

<!-- FINAL -->
<section id="end">
    <h1 id="finalText"></h1>

    <button onclick="reveal('m5')">Tap to reveal</button>
    <img src="Ira4.jpg" id="m5" class="photo">

    <button onclick="location.reload()">Replay</button>
</section>

</div>

<!-- MUSIC -->
<audio id="music">
    <source src="London Thumakda .mp3" type="audio/mpeg">
</audio>

<script>

/* PASSWORD */
function check() {
    if (document.getElementById("pass").value === "Gauresh") {

        document.getElementById("lock").style.display = "none";
        document.getElementById("main").style.display = "block";
        document.getElementById("s1").classList.add("active");

        let music = document.getElementById("music");
        music.currentTime = 47;
        music.play();

    } else {
        alert("Wrong password");
    }
}

/* NAVIGATION */
function next(id) {
    document.querySelectorAll("#main section").forEach(s => {
        s.classList.remove("active");
    });

    document.getElementById(id).classList.add("active");

    if (id === "end") {
        finalType();
    }
}

/* TYPE INTRO */
const text = "Hey Ira";
let i = 0;

function typeEffect() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 80);
    }
}
typeEffect();

/* FINAL TYPE */
const finalMsg = "If I had to choose again, I would still choose you.";

let j = 0;
function finalType() {
    document.getElementById("finalText").innerHTML = "";
    j = 0;

    function typing() {
        if (j < finalMsg.length) {
            document.getElementById("finalText").innerHTML += finalMsg.charAt(j);
            j++;
            setTimeout(typing, 70);
        }
    }
    typing();
}

/* REVEAL */
function reveal(id) {
    document.getElementById(id).style.display = "block";
}

/* HEARTS */
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "♥";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
}
setInterval(createHeart, 400);

</script>

</body>
</html>
