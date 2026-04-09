<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lalit | Portfolio</title>

<style>

/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Smooth Scroll */
html {
    scroll-behavior: smooth;
}

/* Body */
body {
    font-family: 'Segoe UI', sans-serif;
    background: #0f172a;
    color: #fff;
}

/* Navbar */
nav {
    display: flex;
    justify-content: space-between;
    padding: 20px 50px;
    background: #020617;
    position: sticky;
    top: 0;
    z-index: 1000;
}

.logo {
    color: #38bdf8;
    font-size: 22px;
}

nav ul {
    display: flex;
    list-style: none;
}

nav ul li {
    margin-left: 20px;
}

nav a {
    color: white;
    text-decoration: none;
    transition: 0.3s;
}

nav a:hover {
    color: #38bdf8;
}

/* Hero */
.hero {
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    background: linear-gradient(135deg, #0f172a, #1e293b);
}

.hero h1 {
    font-size: 50px;
}

.hero span {
    color: #38bdf8;
}

.hero p {
    margin-top: 10px;
}

.hero button {
    margin-top: 20px;
    padding: 10px 20px;
    border: none;
    background: #38bdf8;
    color: black;
    cursor: pointer;
    transition: 0.3s;
}

.hero button:hover {
    transform: scale(1.1);
}

/* Sections */
section {
    padding: 60px 20px;
    max-width: 900px;
    margin: auto;
}

h2 {
    margin-bottom: 20px;
    color: #38bdf8;
}

/* Skills */
.skill-box {
    display: flex;
    flex-wrap: wrap;
}

.skill {
    background: #1e293b;
    margin: 10px;
    padding: 10px 20px;
    border-radius: 20px;
    transition: 0.3s;
}

.skill:hover {
    background: #38bdf8;
    color: black;
}

/* Projects */
.project-card {
    background: #1e293b;
    margin: 15px 0;
    padding: 20px;
    border-radius: 10px;
    transition: 0.3s;
}

.project-card:hover {
    transform: translateY(-10px);
    background: #334155;
}

/* Contact */
#contact p {
    margin: 10px 0;
}

/* Footer */
footer {
    text-align: center;
    padding: 20px;
    background: #020617;
}

/* Fade Animation */
.fade {
    opacity: 0;
    transform: translateY(30px);
    transition: 1s;
}

.fade.show {
    opacity: 1;
    transform: translateY(0);
}

/* Typing Effect */
.typing {
    border-right: 3px solid #38bdf8;
    white-space: nowrap;
    overflow: hidden;
}

/* Responsive */
@media(max-width: 768px) {
    nav {
        flex-direction: column;
        align-items: center;
    }

    nav ul {
        margin-top: 10px;
    }

    .hero h1 {
        font-size: 35px;
    }
}

</style>
</head>

<body>

<!-- Navbar -->
<nav>
    <h2 class="logo">Lalit</h2>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>

<!-- Hero -->
<section id="home" class="hero">
    <div>
        <h1>Hello, I'm <span>Lalit</span></h1>
        <p class="typing" id="typing"></p>
        <button>Hire Me</button>
    </div>
</section>

<!-- About -->
<section id="about" class="fade">
    <h2>About Me</h2>
    <p>
        I'm Lalit, a creative frontend developer who builds modern, responsive websites.
        I love animations, UI design, and solving real-world problems with code.
    </p>
</section>

<!-- Skills -->
<section id="skills" class="fade">
    <h2>Skills</h2>
    <div class="skill-box">
        <div class="skill">HTML</div>
        <div class="skill">CSS</div>
        <div class="skill">JavaScript</div>
        <div class="skill">React</div>
        <div class="skill">UI/UX</div>
    </div>
</section>

<!-- Projects -->
<section id="projects" class="fade">
    <h2>Projects</h2>

    <div class="project-card">
        <h3>Portfolio Website</h3>
        <p>Modern animated portfolio.</p>
    </div>

    <div class="project-card">
        <h3>Weather App</h3>
        <p>API-based weather app.</p>
    </div>

    <div class="project-card">
        <h3>Todo App</h3>
        <p>Task manager with clean UI.</p>
    </div>

</section>

<!-- Contact -->
<section id="contact" class="fade">
    <h2>Contact</h2>
    <p>Email: lalit.dev@example.com</p>
    <p>Phone: +91 98765 43210</p>
</section>

<footer>
    <p>© 2026 Lalit | All Rights Reserved</p>
</footer>

<!-- JavaScript -->
<script>

// Typing Effect
const text = ["Frontend Developer", "UI Designer", "Freelancer"];
let count = 0;
let index = 0;
let currentText = "";
let letter = "";

(function type() {
    if (count === text.length) {
        count = 0;
    }
    currentText = text[count];
    letter = currentText.slice(0, ++index);

    document.getElementById("typing").textContent = letter;
    if (letter.length === currentText.length) {
        count++;
        index = 0;
        setTimeout(type, 1000);
    } else {
        setTimeout(type, 100);
    }
})();

// Scroll Animation
const faders = document.querySelectorAll(".fade");

window.addEventListener("scroll", () => {
    const trigger = window.innerHeight / 1.2;

    faders.forEach(el => {
        const top = el.getBoundingClientRect().top;

        if (top < trigger) {
            el.classList.add("show");
        }
    });
});

</script>

</body>
</html>
