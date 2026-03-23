<html lang="en">
<head>
<meta charset="UTF-8">
<title>For My Best Friend </title>
<style>
    body {
        margin: 0;
        font-family: 'Arial', sans-serif;
        background: linear-gradient(135deg, #89CFF0, #1E90FF);
        color: white;
        text-align: center;
        overflow: hidden;
    }

    .container {
        margin-top: 100px;
    }

    h1 {
        font-size: 3em;
        animation: fadeIn 2s ease-in-out;
    }

    p {
        font-size: 1.2em;
        width: 60%;
        margin: auto;
        margin-top: 20px;
        animation: fadeIn 3s ease-in-out;
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
    }

    button:hover {
        background-color: #ddd;
        transform: scale(1.1);
    }

    .hidden-message {
        margin-top: 30px;
        font-size: 1.5em;
        display: none;
        animation: fadeIn 1s ease-in-out;
    }

    @keyframes fadeIn {
        from {opacity: 0;}
        to {opacity: 1;}
    }

    /* floating hearts */
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

<div class="container">
    <h1>Hey Bestie 💙</h1>
    <p>
        You are literally one of the best things in my life.  
        Thank you for always being there, for the laughs, the chaos,  
        and all the unforgettable memories we’ve made together.
    </p>

    <button onclick="showMessage()">Click Me 👀</button>

    <div class="hidden-message" id="message">
        I love you so much bestie 💙✨ Never change!!
    </div>
</div>

<script>
function showMessage() {
    document.getElementById("message").style.display = "block";
}

// floating hearts generator
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerText = "💖";
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
