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
    font-size:
