<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Great Vibes', cursive;
    color: white;
    text-align: center;
    overflow: hidden;
    background: url("bg1.jpg") center/cover no-repeat fixed;
}

/* sections */
section {
    height: 100vh;
    display: none;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 20px;
}

section.active {
    display: flex;
}

#lock {
    display: flex;
}

/* text */
h1 {
    font-size: 3em;
}

p {
    max-width: 600px;
    font-size: 1.4em;
}

/* button */
button {
    margin-top: 20px;
    padding: 12px 25px;
    border-radius: 25px;
    border: none;
    background: white;
    color: black;
    cursor: pointer;
}

button:hover {
    transform: scale(1.1);
}

/* images */
.photo {
    width: 250px;
    border-radius: 15px;
    margin-top: 20px;
    display: none;
}

/* video */
video {
    width: 300px;
    border-radius: 15px;
    margin-top: 20px;
}

/* confetti */
.confetti {
    position: fixed;
    width: 10px;
    height: 10px;
    background: gold;
    top: -10px;
    animation: fall 3s linear infinite;
}

@keyframes fall {
    to {
        transform: translateY(100vh) rotate(360deg);
    }
}
</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
    <h1>Enter something only we know</h1>
    <input type="password" id="pass">
    <p>Hint: Who is better for Akanksha??</p>
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
    <p>These moments meant everything.</p>
    <video controls>
        <source src="Ira Video.mp4" type="video/mp4">
    </video>
    <button onclick="next('s5')">Continue</button>
</section>

<section id="s5">
    <p>It is the small moments that became everything.</p>
    <button onclick="reveal('m3')">Tap to reveal</button>
    <img src="Ira2.jpg" id="m3" class="photo">
    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6">
    <p>You are not just my best friend. You are my safe place.</p>
    <button onclick="reveal('m4')">Tap to reveal</button>
    <img src="Ira7.jpeg" id="m4" class="photo" style="transform: rotate(90deg);">
    <button onclick="next('quiz')">Last</button>
</section>

<!-- QUIZ -->
<section id="quiz">
    <h1>One last thing...</h1>
    <p>Guess what I got you</p>

    <button onclick="checkGift('chocolate')">Chocolate</button>
    <button onclick="checkGift('bracelet')">Bracelet</button>
    <button onclick="checkGift('flowers')">Flowers</button>
    <button onclick="checkGift('handmade')">Handmade gift</button>

    <p id="quizResult"></p>
</section>

<!-- FINAL -->
<section id="end">
    <h1 id="countdown"></h1>

    <h1 id="finalText" style="display:none;">
        It was never just a gift.<br><br>
        It is something I made for you.
    </h1>

    <button onclick="reveal('m5')" id="finalBtn" style="display:none;">Tap to reveal</button>
    <img src="Ira6.jpg" id="m5" class="photo">

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

/* NAV */
function next(id) {
    document.querySelectorAll("#main section").forEach(s => {
        s.classList.remove("active");
    });
    document.getElementById(id).classList.add("active");

    if (id === "end") startCountdown();
}

/* TYPE */
let text = "Hey Ira";
let i = 0;
function typeEffect() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 80);
    }
}
typeEffect();

/* REVEAL */
function reveal(id) {
    document.getElementById(id).style.display = "block";
}

/* QUIZ */
function checkGift(ans) {
    let result = document.getElementById("quizResult");

    if (ans === "bracelet" || ans === "handmade") {
        result.innerHTML = "You know me too well...";
        setTimeout(() => next('end'), 1500);
    } else {
        result.innerHTML = "Nope... try again";
    }
}

/* COUNTDOWN */
function startCountdown() {
    let count = 3;
    let el = document.getElementById("countdown");

    let interval = setInterval(() => {
        el.innerHTML = count;
        count--;

        if (count < 0) {
            clearInterval(interval);
            el.style.display = "none";
            document.getElementById("finalText").style.display = "block";
            document.getElementById("finalBtn").style.display = "block";
            startConfetti();
        }
    }, 1000);
}

/* CONFETTI */
function startConfetti() {
    for (let i = 0; i < 80; i++) {
        let c = document.createElement("div");
        c.classList.add("confetti");
        c.style.left = Math.random() * 100 + "vw";
        document.body.appendChild(c);

        setTimeout(() => c.remove(), 3000);
    }
}

</script>

</body>
</html>
