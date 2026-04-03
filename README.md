<!DOCTYPE html>
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
    overflow-y: auto;
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
h1 { font-size: 3em; }
p { max-width: 600px; font-size: 1.4em; }

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

/* images */
.photo {
    width: 250px;
    border-radius: 15px;
    margin-top: 20px;
    display: none;
    max-height: 70vh;
}

/* blur effect */
.blur {
    filter: blur(10px);
    transition: 0.6s;
}
.blur.show {
    filter: blur(0);
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
    width: 8px;
    height: 8px;
    top: -10px;
    animation: fall linear forwards;
}

@keyframes fall {
    to {
        transform: translateY(100vh) rotate(720deg);
    }
}
</style>
</head>

<body>

<!-- PASSWORD -->
<section id="lock" class="active">
    <h1>Enter something only we know</h1>
    <input type="password" id="pass">
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
    <img src="Ira3.jpg" id="m1" class="photo blur" onclick="this.classList.toggle('show')">
    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3">
    <p>You became the person I go to without thinking.</p>
    <button onclick="reveal('m2')">Tap to reveal</button>
    <img src="Ira1.jpg" id="m2" class="photo blur" onclick="this.classList.toggle('show')">
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
    <img src="Ira2.jpg" id="m3" class="photo blur" onclick="this.classList.toggle('show')">
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
    <h1 id="fakeEnd">The End</h1>

    <h1 id="realEnd" style="display:none;">
        wait… one more thing
    </h1>

    <h2 id="giftText" style="display:none;">
        now check behind you
    </h2>

    <button onclick="reveal('finalPic')" id="finalBtn" style="display:none;">
        Tap to reveal
    </button>

    <img src="Ira6.jpg" id="finalPic" class="photo">
    
    <br><br>

    <button onclick="document.getElementById('voice').play()" id="voiceBtn" style="display:none;">
        Play this
    </button>

</section>

</div>

<!-- MUSIC -->
<audio id="music">
    <source src="London Thumakda .mp3" type="audio/mpeg">
</audio>

<!-- VOICE -->
<audio id="voice">
    <source src="voice.mp3" type="audio/mpeg">
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

    if (id === "end") startEnding();
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

/* ENDING */
function startEnding() {
    setTimeout(() => {
        document.getElementById("fakeEnd").style.display = "none";
        document.getElementById("realEnd").style.display = "block";

        setTimeout(() => {
            document.getElementById("giftText").style.display = "block";
            document.getElementById("finalBtn").style.display = "block";
            document.getElementById("voiceBtn").style.display = "block";
            startConfetti();
        }, 1500);

    }, 2000);
}

/* CONFETTI */
function startConfetti() {
    for (let i = 0; i < 100; i++) {
        let c = document.createElement("div");
        c.classList.add("confetti");

        c.style.left = Math.random() * 100 + "vw";
        c.style.backgroundColor = `hsl(${Math.random()*360},100%,50%)`;
        c.style.animationDuration = (Math.random()*2 + 2) + "s";

        document.body.appendChild(c);

        setTimeout(() => c.remove(), 4000);
    }
}

</script>

</body>
</html>
