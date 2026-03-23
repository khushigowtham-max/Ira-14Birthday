<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Ira</title>

<style>
<section class="fade">
    
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
    
.photo {
    width: 250px;
    border-radius: 15px;
    margin-top: 20px;
    transition: 0.4s;
}

.photo:hover {
    transform: scale(1.05);
}
p {
    max-width: 600px;
    font-size: 1.3em;
    line-height: 1.8;
}
/* backgrounds */
.one {background: url("bg2.jpg") center/cover no-repeat;}
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
        const faders = document.querySelectorAll('.fade');

window.addEventListener('scroll', () => {
    faders.forEach(el => {
        const top = el.getBoundingClientRect().top;
        if (top < window.innerHeight - 100) {
            el.classList.add('show');
        }
    });
});
}

.show {
    opacity: 1;
    transform: translateY(0);
}
    <script>
function next(id) {
    document.querySelectorAll("section").forEach(s => s.style.display = "none");
    document.getElementById(id).style.display = "flex";
}
</script>
</style>

</head>

<body>

<section id="s1">
    <h1 id="typing"></h1>
    <button onclick="next('s2')">Continue</button>
</section>

<section id="s2" style="display:none;">
    <p>
        I do not think I say this enough, but you changed my life in a way I never expected.
    </p>
    <button onclick="next('s3')">Continue</button>
</section>

<section id="s3" style="display:none;">
    <p>
        You became the person I go to without thinking.
        The person I trust without explaining everything.
    </p>
    <button onclick="next('s4')">Continue</button>
</section>

<section id="s4" style="display:none;">
    <p>
        It is not just the big memories.
        It is the random conversations that somehow mean the most.
    </p>
    <button onclick="next('s5')">Continue</button>
</section>

<section id="s5" style="display:none;">
    <p>
        You are not just my best friend.
        You are someone who stayed, understood, and made life better.
    </p>
    <button onclick="next('s6')">Continue</button>
</section>

<section id="s6" style="display:none;">
    <p>
        Happy Birthday.
        I hope this year gives you everything you deserve.
    </p>
    <button onclick="next('end')">Last</button>
</section>

<section id="end" style="display:none;">
    <p>
        If I had to choose again, I will still choose you.
    </p>
</section>
<audio autoplay loop>
<source "Queen London Thumakda Full Song (audio)  Amit Trivedi  Kangana Ranaut, Raj Kumar Rao">
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
