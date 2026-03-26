<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<!-- Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Poppins', sans-serif;
    color: white;
    text-align: center;
}

/* sections */
section {
    height: 100vh;
    display: none;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
    opacity: 0;
    transition: 1s;
    position: relative;
    overflow: hidden;
}

section.active {
    display: flex;
    opacity: 1;
}

/* TEXT */
h1 {
    font-size: 3em;
    text-shadow: 0 0 15px rgba(255,255,255,0.4);
}

p {
    max-width: 600px;
    font-size: 1.2em;
    line-height: 1.8;
    text-shadow: 0 0 10px rgba(0,0,0,0.7);
}

/* BUTTON */
button {
    margin-top: 20px;
    padding: 12px 25px;
    border-radius: 25px;
    border: none;
    background: white;
    color: black;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}

/* IMAGES */
.photo {
    width: 250px;
    border-radius: 15px;
    margin-top: 20px;
    display: none;
}

/* VIDEO */
video {
    width: 300px;
    border-radius: 15px;
    margin-top: 20px;
}

/* CHAT */
.chatbox {
    width: 300px;
    text-align: left;
}

.msg {
    padding: 10px;
    margin: 10px;
    border-radius: 15px;
    max-width: 70%;
}

.left { background: #222; }
.right {
    background: #0b93f6;
    margin-left: auto;
}

/* BACKGROUNDS */
#s1 { background: url("bg1.jpg") center/cover no-repeat; }
#s2 { background: url("bg2.jpg") center/cover no-repeat; }
#s3 { background: url("bg3.jpg") center/cover no-repeat; }
#s4 { background: black; }
#s5 { background: url("bg1.jpg") center/cover no-repeat; }
#s6 { background: url("bg2.jpg") center/cover no-repeat; }
#chat { background: #111; }
#end { background: black; }

/* OVERLAY */
section::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.6);
    top: 0;
    left: 0;
    z-index: -1;
}

/* CINEMATIC ZOOM */
@keyframes zoom {
    from { background-size: 100%; }
    to { background-size: 110%; }
}

section {
    animation: zoom 12s infinite alternate;
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

/* SHAKE */
.shake {
    animation: shake 0.5s;
}

@keyframes shake {
    0% { transform: translate(2px, 2px); }
    25% { transform: translate(-2px, -2px); }
    50% { transform: translate(2px, -2px); }
    75% { transform: translate(-2px, 2px); }
    100% { transform: translate(0, 0); }
}
</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
    <h1>This is not just a website</h1>
    <p>It is something I made for you</p>
    <input type="password" id="pass">
    <p style="opacity:0.7;">Hint: Who is better for Akanksha over Yogesh??</p>
    <button onclick="check()">Enter</button>
</section>

<!-- MAIN -->
<div id="main" style="display:none;">

<section id="s1">
    <h1 id="typing"></h1>
    <button onclick="next('s2')">Continue</button>
</section>

<section id="s2">
    <p>You changed my life in a way I never expected.</p>
    <button onclick="reveal('m1')">Tap to reveal</button>
    <img src="Ira3.jpg" id="m1" class="photo">
    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3">
    <p>You became the person I go to without thinking.</p>
    <button onclick="reveal('m2')">Tap to reveal</button>
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
    <p>It is not just the big memories, but everything in between.</p>
    <button onclick="reveal('m3')">Tap to reveal</button>
    <img src="Ira2.jpg" id="m3" class="photo">
    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6">
    <p>You are someone who stayed and made life better.</p>
    <button onclick="reveal('m4')">Tap to reveal</button>
    <img src="Ira5.jpg" id="m4" class="photo">
    <button onclick="next('chat')">Last</button>
</section>

<!-- CHAT -->
<section id="chat">
    <div class="chatbox">
        <p class="msg left">hey</p>
        <p class="msg right">what</p>
        <p class="msg left">nothing just wanted to talk</p>
        <p class="msg right">why</p>
        <p class="msg left">because you matter more than you think</p>
        <p class="msg right">shut up 😭</p>
        <p class="msg left">never</p>
    </div>
    <button onclick="next('end')">Continue</button>
</section>

<!-- FINAL -->
<section id="end">
    <h1 id="finalText"></h1>

    <button onclick="reveal('m5')">Tap to reveal</button>
    <img src="Ira6.jpg" id="m5" class="photo">

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
        typeFinal();
        document.body.classList.add("shake");
        setTimeout(() => document.body.classList.remove("shake"), 500);
    }
}

/* TYPE START */
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

/* FINAL TEXT */
const finalMessage = "If I had to choose again, I would still choose you.";
function typeFinal() {
    let i = 0;
    const el = document.getElementById("finalText");
    el.innerHTML = "";

    function typing() {
        if (i < finalMessage.length) {
            el.innerHTML += finalMessage.charAt(i);
            i++;
            setTimeout(typing, 80);
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
