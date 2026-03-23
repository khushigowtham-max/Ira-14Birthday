<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: black;
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

h1 {
    font-size: 3em;
    margin-bottom: 20px;
}

p {
    max-width: 600px;
    font-size: 1.3em;
    line-height: 1.8;
}

/* button */
button {
    margin-top: 25px;
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

/* hearts */
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
    <h1>Enter something only we know</h1>
    <input type="password" id="pass">
    <p style="margin-top:10px; opacity:0.7;">
        Hint: Who is better for Akanksha over Yogesh????
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
    <p>
        I do not think I say this enough, but you changed my life in a way I never expected.
    </p>

    <button onclick="reveal('m1')">Tap to reveal memory</button>
    <img src="Ira3.jpg" id="m1" class="photo">

    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3">
    <p>
        You became the person I go to without thinking.
        The person I trust without explaining everything.
    </p>

    <button onclick="reveal('m2')">Tap to reveal memory</button>
    <img src="Ira1.jpg" id="m2" class="photo">

    <button onclick="next('s4')">Continue</button>
</section>

<section id="s4">
    <p>
        These moments meant more than I ever said.
    </p>

    <video controls>
        <source src="Ira Video.mp4" type="video/mp4">
    </video>

    <button onclick="next('s5')">Continue</button>
</section>

<section id="s5">
    <p>
        It is not just the big memories.
        It is the random moments that somehow became everything.
    </p>

    <button onclick="reveal('m3')">Tap to reveal memory</button>
    <img src="Ira2.jpg" id="m3" class="photo">

    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6">
    <p>
        You are not just my best friend.
        You are someone who stayed and made life better.
    </p>
      <button onclick="reveal('m2')">Tap to reveal</button>
    <img src="Ira5.jpg" id="m2" class="photo">
    <button onclick="next('end')">Last</button>
</section>

<section id="end">
    <p>
        If I had to choose again, I would still choose you.
         <button onclick="reveal('m3')">Tap to reveal </button>
    <img src="Ira2.jpg" id="m3" class="photo">

    </p>
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
}

/* TYPE EFFECT */
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
