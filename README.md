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
    margin: 0;
    font-family: Arial, sans-serif;
    background: black;
    color: white;
    text-align: center;
}

section {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

p {
    max-width: 600px;
    font-size: 1.3em;
    line-height: 1.8;
}
/* backgrounds */
.one { background: linear-gradient(#1E90FF, #000); }
.two { background: #000; }
.three { background: #111; }
.four { background: #000; }
.five { background: #111; }

/* text */
h1 {
    font-size: 3em;
    margin-bottom: 20px;
}

p {
    max-width: 700px;
    line-height: 1.8;
    font-size: 1.2em;
}

/* button */
button {
    margin-top: 30px;
    padding: 15px 30px;
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

/* hidden final */
#final {
    opacity: 0;
    transition: 2s;
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
    .fade {
    opacity: 0;
    transform: translateY(40px);
    transition: 1.5s;
}

.show {
    opacity: 1;
    transform: translateY(0);
}
</style>

</head>

<body>

<section class="one">
    <h1 id="typing"></h1>
</section>

<section class="two">
    <p>
        I do not think I say this enough, but you changed my life in a way I never expected.
        Not loudly, not suddenly, but in small moments that slowly became everything.
    </p>
</section>

<section class="three">
    <p>
        You became the person I go to without thinking.
        The person I trust without explaining everything.
        The one who makes even normal days feel important.
    </p>
</section>

<section class="four">
    <p>
        It is not just the big memories.
        It is the random conversations, the silence, the stupid moments that somehow mean the most.
    </p>
</section>

<section class="five">
    <p>
        You are not just my best friend.
        You are someone who stayed, understood, and made life better just by being in it.
    </p>
</section>

<section class="two">
    <p>
        Happy Birthday.
        I hope this year gives you everything you deserve.
        And I hope you never forget how much you matter.
    </p>

    <button onclick="reveal()">Click when you are ready</button>

    <p id="final">
        Out of everyone in the world, I am really glad it was you.
        And I would choose you again without thinking.
    </p>
</section>

<audio autoplay loop>
<source src="https://www.bensound.com/bensound-music/bensound-slowmotion.mp3">
</audio>

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

function reveal() {
    document.getElementById("final").style.opacity = 1;
}

/* hearts */
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
