<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #89CFF0, #1E90FF);
    color: white;
    text-align: center;
    overflow-x: hidden;
}

.section {
    padding: 60px 20px;
}

h1 {
    font-size: 3em;
}

h2 {
    margin-top: 40px;
    font-size: 2em;
}

p {
    width: 70%;
    margin: auto;
    margin-top: 15px;
    font-size: 1.1em;
    line-height: 1.6;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    margin: 10px 0;
}

button {
    margin-top: 30px;
    padding: 15px 30px;
    font-size: 1em;
    border: none;
    border-radius: 25px;
    background-color: white;
    color: #1E90FF;
    cursor: pointer;
    transition: 0.3s;
    box-shadow: 0 0 10px white, 0 0 20px #1E90FF;
}

button:hover {
    transform: scale(1.1);
    background-color: #ddd;
}

.hidden {
    display: none;
    margin-top: 20px;
    font-size: 1.4em;
}

img {
    width: 200px;
    margin: 10px;
    border-radius: 15px;
}

.heart {
    position: absolute;
    color: pink;
    animation: floatUp 5s linear infinite;
}

@keyframes floatUp {
    0% {
        transform: translateY(100vh);
        opacity: 1;
    }
    100% {
        transform: translateY(-10vh);
        opacity: 0;
    }
}
</style>

</head>

<body>

<div class="section">
    <h1 id="typing"></h1>
    <p>
        From random laughs to deep talks you have always been someone I can count on.
        Life feels lighter and better with you in it.
    </p>
</div>

<div class="section">
    <h2>Our Story</h2>
    <p>
        It started with a simple moment and turned into something I will always value.
        We created memories that are impossible to replace.
        The way we understand each other without explaining everything makes this friendship special.
    </p>
</div>

<div class="section">
    <h2>Things Only We Understand</h2>
    <ul>
        <li>Those random conversations that make no sense to anyone else</li>
        <li>The times we could not stop laughing</li>
        <li>The way one word is enough for us to understand everything</li>
    </ul>
</div>

<div class="section">
    <h2>Why You Matter</h2>
    <p>
        You are someone who listens, cares, and stays.
        That is rare and it means more than I can explain.
        Having you in my life is something I will always be grateful for.
    </p>
</div>

<div class="section">
    <h2>Birthday Message</h2>
    <p>
        I hope this year brings you happiness, success, and everything you have been wishing for.
        You deserve good things and more.
        No matter what happens I will always be here.
    </p>
</div>

<div class="section">
    <h2>Memories</h2>
    <img src="photo1.jpg">
    <img src="photo2.jpg">
    <img src="photo3.jpg">
</div>

<div class="section">
    <h2>Timeline</h2>
    <ul>
        <li>When we first met</li>
        <li>Our first real conversation</li>
        <li>Moments that made this friendship strong</li>
    </ul>
</div>

<div class="section">
    <button onclick="showMessage()">Click for a final message</button>
    <p id="finalMessage" class="hidden">
        No matter how much time passes you will always be important to me.
    </p>
</div>

<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-sunny.mp3" type="audio/mp3">
</audio>

<script>
const text = "Hey Ira";
let i = 0;

function typeEffect() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeEffect, 70);
    }
}
typeEffect();

function showMessage() {
    document.getElementById("finalMessage").style.display = "block";
}

function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "♥";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 5000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
