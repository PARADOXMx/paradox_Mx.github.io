# paradox_Mx.github.io
pagina de precentacion 
[index.html](https://github.com/user-attachments/files/24362406/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, viewport-fit=cover">
    <meta name="theme-color" content="#8a2be2">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>Portafolio Personal</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script> <!-- Placeholder for FontAwesome -->
    <!-- Usaremos iconos SVG directos para evitar dependencias externas rotas -->
</head>
<body>
    <!-- Efecto de fondo interactivo -->
    <div class="cursor-glow"></div>

    <header>
        <nav>
            <div class="logo">Mi Portafolio<span class="dot">.</span></div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#habilidades">Habilidades</a></li>
                <li><a href="#proyectos">Proyectos</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <section id="inicio" class="hero">
        <div class="hero-content">
            <div class="profile-frame">
                <!-- Puedes cambiar esta URL por tu foto real -->
                <img src="251701120.jpg" alt="Foto de Perfil" class="profile-img">
            </div>
            <h1 class="fade-in">Hola, soy <span class="highlight">友ㅤPARADOXㅤMx</span></h1>
            <p class="fade-in delay-1">Desarrollador & Diseñador Creativo</p>
            <a href="#proyectos" class="btn fade-in delay-2">Ver Proyectos</a>
        </div>
    </section>

    <section id="habilidades" class="section">
        <h2 class="section-title">Mis Habilidades</h2>
        <div class="skills-container">
            <!-- Habilidades Técnicas -->
            <div class="skill-card tilt">
                <div class="icon">💻</div>
                <h3>Desarrollo Web</h3>
                <p>HTML, CSS, JavaScript, React</p>
            </div>
            <div class="skill-card tilt">
                <div class="icon">🎨</div>
                <h3>Diseño UI/UX</h3>
                <p>Figma, Adobe XD, Photoshop</p>
            </div>
            <div class="skill-card tilt">
                <div class="icon">⚙️</div>
                <h3>Backend</h3>
                <p>Node.js, Python, SQL</p>
            </div>
            <div class="skill-card tilt">
                <div class="icon">🚀</div>
                <h3>Otras</h3>
                <p>Git, Docker, SEO</p>
            </div>
        </div>
    </section>

    <section id="proyectos" class="section">
        <h2 class="section-title">Mis Proyectos</h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-img" style="background-image: url('IMG-20251222-WA0095.webp?text=Proyecto+2');"></div>
                <div class="project-info">
                    <h3>proyecto 1</h3>
                    <p>una herramienta ddos osea una herramienta que se usa para atacar a un servidor.</p>
                </div>
            </div>
            <div class="project-card">
                <div class="project-img" style="background-image: url('IMG-20251225-WA0070.webp?text=Proyecto+2');"></div>
                <div class="project-info">
                    <h3>Proyecto 2</h3>
                    <p>herramienta de hacking de rastreo de numero telefonico.</p>
                </div>
            </div>
            <div class="project-card">
                <div class="project-img" style="background-image: url('Screenshot_20251228_121347_com_discord_MainActivity_edit_166019431581433.webp?text=Proyecto+3');"></div>
                <div class="project-info">
                    <h3>Proyecto 3</h3>
                    <p>un rat un tipo virus q puede infectar tu dipositivo y obtener acceso a tu camara tanto como tu galeria .</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contacto" class="section">
        <h2 class="section-title">Redes Sociales</h2>
        <div class="social-links">
            <a href="#" class="social-btn">
                <span>Discord</span>
            </a>
            <a href="#" class="social-btn">
                <span>GitHub</span>
            </a>
    </section>

    <footer>
        <p>&copy; 2025 友ㅤPARADOXㅤMx. Todos los derechos reservados.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
[script.js](https://github.com/user-attachments/files/24362412/script.js)
// Mouse Glow Effect
const cursorGlow = document.querySelector('.cursor-glow');

document.addEventListener('mousemove', (e) => {
    // Mueve el div de brillo a la posición del mouse
    cursorGlow.style.left = e.clientX + 'px';
    cursorGlow.style.top = e.clientY + 'px';
});

// Tilt Effect for Skills Cards (3D movement on hover)
const cards = document.querySelectorAll('.skill-card');

cards.forEach(card => {
    card.addEventListener('mousemove', (e) => {
        const rect = card.getBoundingClientRect();
        const x = e.clientX - rect.left; // x position within the element.
        const y = e.clientY - rect.top;  // y position within the element.
        
        const centerX = rect.width / 2;
        const centerY = rect.height / 2;
        
        const rotateX = ((y - centerY) / centerY) * -10; // Max rotation 10deg
        const rotateY = ((x - centerX) / centerX) * 10;

        card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.05)`;
    });

    card.addEventListener('mouseleave', () => {
        card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale(1)';
    });
});

// Scroll Reveal Animation
const observerOptions = {
    threshold: 0.1
};

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.style.opacity = '1';
            entry.target.style.transform = 'translateY(0)';
            observer.unobserve(entry.target);
        }
    });
}, observerOptions);

document.querySelectorAll('.project-card, .section-title, .social-btn').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(30px)';
    el.style.transition = 'all 0.6s ease-out';
    observer.observe(el);
});
[styles.css](https://github.com/user-attachments/files/24362413/styles.css)
:root {
    --bg-color: #050505;
    --card-bg: #101010;
    --primary: #8a2be2; /* BlueViolet */
    --secondary: #9d4edd;
    --text-color: #ffffff;
    --text-muted: #b3b3b3;
    --gradient: linear-gradient(45deg, var(--primary), #4b0082);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
    scroll-behavior: smooth;
}

body {
    background-color: var(--bg-color);
    color: var(--text-color);
    overflow-x: hidden;
}

/* Cursor Glow Effect */
.cursor-glow {
    position: fixed;
    top: 0;
    left: 0;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(138, 43, 226, 0.15), transparent 70%);
    transform: translate(-50%, -50%);
    pointer-events: none;
    z-index: 9999;
    mix-blend-mode: screen;
}

/* Header */
header {
    position: fixed;
    top: 0;
    width: 100%;
    padding: 20px 50px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(5, 5, 5, 0.9);
    backdrop-filter: blur(10px);
    z-index: 1000;
    border-bottom: 1px solid rgba(138, 43, 226, 0.2);
}

.logo {
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.dot {
    color: var(--primary);
}

.nav-links {
    list-style: none;
    display: flex;
    gap: 30px;
}

.nav-links a {
    text-decoration: none;
    color: var(--text-color);
    font-weight: 500;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: var(--primary);
    text-shadow: 0 0 10px var(--primary);
}

/* Hero Section */
.hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: relative;
    padding-top: 60px;
}

.hero-content {
    z-index: 1;
}

.profile-frame {
    width: 180px;
    height: 180px;
    margin: 0 auto 20px;
    border-radius: 50%;
    padding: 5px;
    background: var(--gradient);
    box-shadow: 0 0 30px rgba(138, 43, 226, 0.5);
    transition: transform 0.5s;
}

.profile-frame:hover {
    transform: scale(1.05);
}

.profile-img {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid var(--bg-color);
}

h1 {
    font-size: 3.5rem;
    margin-bottom: 10px;
}

.highlight {
    color: var(--primary);
    text-shadow: 0 0 20px rgba(138, 43, 226, 0.6);
}

p {
    font-size: 1.2rem;
    color: var(--text-muted);
    margin-bottom: 30px;
}

.btn {
    display: inline-block;
    padding: 12px 30px;
    background: var(--gradient);
    color: white;
    text-decoration: none;
    border-radius: 30px;
    font-weight: 600;
    transition: transform 0.3s, box-shadow 0.3s;
}

.btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(138, 43, 226, 0.4);
}

/* Sections General */
.section {
    padding: 80px 10%;
    min-height: 80vh;
}

.section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 60px;
    position: relative;
    display: inline-block;
    left: 50%;
    transform: translateX(-50%);
}

.section-title::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 0;
    width: 100%;
    height: 3px;
    background: var(--gradient);
    border-radius: 2px;
}

/* Skills */
.skills-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
}

.skill-card {
    background: var(--card-bg);
    padding: 30px;
    border-radius: 15px;
    text-align: center;
    border: 1px solid rgba(255, 255, 255, 0.05);
    transition: all 0.3s;
    cursor: pointer;
}

.skill-card:hover {
    transform: translateY(-10px);
    border-color: var(--primary);
    box-shadow: 0 10px 30px rgba(138, 43, 226, 0.2);
}

.icon {
    font-size: 3rem;
    margin-bottom: 20px;
}

/* Projects */
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 40px;
}

.project-card {
    background: var(--card-bg);
    border-radius: 15px;
    overflow: hidden;
    transition: transform 0.3s;
}

.project-card:hover {
    transform: scale(1.03);
    box-shadow: 0 0 20px rgba(138, 43, 226, 0.15);
}

.project-img {
    height: 200px;
    background-size: cover;
    background-position: center;
    position: relative;
}

/* Overlay effect on hover */
.project-img::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(138, 43, 226, 0.2);
    opacity: 0;
    transition: opacity 0.3s;
}

.project-card:hover .project-img::before {
    opacity: 1;
}

.project-info {
    padding: 25px;
}

.project-info h3 {
    color: var(--primary);
    margin-bottom: 10px;
}

/* Socials */
.social-links {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.social-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 150px;
    height: 50px;
    border: 2px solid var(--primary);
    color: white;
    text-decoration: none;
    font-weight: 600;
    border-radius: 5px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
}

.social-btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: var(--primary);
    transition: left 0.3s;
    z-index: -1;
}

.social-btn:hover::before {
    left: 0;
}

.social-btn:hover {
    box-shadow: 0 0 15px var(--primary);
}

/* Footer */
footer {
    padding: 40px;
    text-align: center;
    background: #000;
    border-top: 1px solid #222;
    color: var(--text-muted);
}

/* Animations */
.fade-in {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 0.8s forwards;
}

.delay-1 { animation-delay: 0.2s; }
.delay-2 { animation-delay: 0.4s; }

@keyframes fadeInUp {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive */
@media (max-width: 768px) {
    h1 { font-size: 2.5rem; }
    .nav-links { display: none; } /* Mobile menu simplified for this demo */
    header { justify-content: center; }
}

