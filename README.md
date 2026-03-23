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
    padding: 70px 20px;
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
    font-size: 1.15em;
    line-height: 1.8;
}

button {
    margin-top: 40px;
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
    margin-top: 30px;
    font-size: 1.5em;
}

.fade {
    opacity: 0;
    animation: fadeIn 3s forwards;
}

@keyframes fadeIn {
    to { opacity: 1; }
}

.heart {
    position: absolute;
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

<div class="section">
    <h1 id="typing"></h1>
    <p class="fade">
        I do not think I say this enough, but you changed my life in a way I never expected.
        Not in a loud dramatic way, but in quiet moments that slowly became everything.
    </p>
</div>

<div class="section">
    <h2 class="fade">There is something about you</h2>
    <p class="fade">
        You walked into my life like it was nothing, and somehow stayed in a way that means everything.
        You became the person I go to without thinking, the person I trust without doubt,
        and the person who makes even the worst days feel lighter.
    </p>
</div>

<div class="section">
    <h2 class="fade">The little things</h2>
    <p class="fade">
        It is not just the big memories.
        It is the random conversations, the moments where nothing important is happening,
        and yet I would not trade them for anything.
        Those are the moments that made this friendship real.
    </p>
</div>

<div class="section">
    <h2 class="fade">What you mean to me</h2>
    <p class="fade">
        You are not just my best friend.
        You are someone who understands me in a way that is hard to explain.
        Someone who stayed when it mattered.
        Someone who made me feel like I am not alone.
    </p>
</div>

<div class="section">
    <h2 class="fade">I want you to know this</h2>
    <p class="fade">
        No matter where life goes, no matter how much changes,
        you will always be important to me.
        Not just for what we have now, but for everything we have already been through.
    </p>
</div>

<div class="section">
    <h2 class="fade">Happy Birthday</h2>
    <p class="fade">
        I hope this year gives you the happiness you give to everyone else.
        I hope you find everything you are looking for.
        And I hope you never forget how much you matter.
    </p>
</div>

<div class="section">
    <button onclick="showFinal()">Click this when you are ready</button>
    <p id="finalMessage" class="hidden">
        Out of all the people in the world, I am really glad it was you.
    </p>
</div>

<script>
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

function showFinal() {
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
    }, 6000);
}

setInterval(createHeart, 400);
</script>

</body>
</html>
