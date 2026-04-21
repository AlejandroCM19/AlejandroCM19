<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Perfil Tech | Dev & Security</title>
    <!-- Importar fuente Inter y JetBrains Mono para el estilo código -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    <!-- Iconos FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- VARIABLES CSS --- */
        :root {
            --bg-body: #0d1117; /* GitHub Dark Background */
            --bg-card: #161b22;
            --text-main: #c9d1d9;
            --text-muted: #8b949e;
            --border-color: #30363d;
            
            /* Colores por especialidad */
            --color-web: #a855f7;   /* Púrpura para Diseño */
            --color-qa: #0ea5e9;    /* Azul para QA */
            --color-code: #22c55e;  /* Verde para Programación */
            --color-sec: #ef4444;   /* Rojo para Ciberseguridad */
            
            --accent: #58a6ff;      /* Azul GitHub clásico */
            --glow: 0 0 10px rgba(88, 166, 255, 0.2);
        }

        /* --- RESET & BASE --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-body);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a { text-decoration: none; color: inherit; transition: 0.3s; }
        ul { list-style: none; }

        /* --- UTILIDADES --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: var(--accent);
            margin: 10px auto 0;
            border-radius: 2px;
        }

        .mono { font-family: 'JetBrains Mono', monospace; }

        .btn {
            display: inline-block;
            padding: 10px 24px;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            border: 1px solid var(--border-color);
            background: var(--bg-card);
            color: var(--accent);
        }

        .btn:hover {
            background: var(--accent);
            color: #fff;
            box-shadow: var(--glow);
        }

        /* --- HEADER --- */
        header {
            background: rgba(13, 17, 23, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-main);
        }
        .logo span { color: var(--accent); }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        /* --- HERO SECTION --- */
        .hero {
            padding: 6rem 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .hero-content {
            flex: 1;
            min-width: 300px;
        }

        .hero-tag {
            color: var(--accent);
            font-weight: 600;
            margin-bottom: 1rem;
            display: block;
        }

        .hero h1 {
            font-size: 3.5rem;
            line-height: 1.2;
            margin-bottom: 1.5rem;
            background: linear-gradient(90deg, #fff, #8b949e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            max-width: 500px;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
            min-width: 300px;
        }

        .avatar-container {
            position: relative;
            width: 300px;
            height: 300px;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--bg-card);
            box-shadow: 0 0 30px rgba(0,0,0,0.5);
        }

        .status-badge {
            position: absolute;
            bottom: 20px;
            right: 20px;
            background: #238636;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            border: 1px solid rgba(255,255,255,0.1);
        }

        /* --- PILARS (LOS 4 ENFOQUES) --- */
        .pillars {
            padding: 4rem 0;
        }

        .grid-4 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 2rem;
            transition: transform 0.3s, border-color 0.3s;
            position: relative;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card-icon {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
        }

        .card h3 {
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tag {
            font-size: 0.75rem;
            padding: 4px 8px;
            border-radius: 4px;
            background: rgba(255,255,255,0.05);
            font-family: 'JetBrains Mono', monospace;
        }

        /* Estilos específicos para cada carta */
        .card-web:hover { border-color: var(--color-web); box-shadow: 0 4px 20px rgba(168, 85, 247, 0.15); }
        .card-web .card-icon { color: var(--color-web); }
        .card-web .tag { color: var(--color-web); border: 1px solid rgba(168, 85, 247, 0.2); }

        .card-qa:hover { border-color: var(--color-qa); box-shadow: 0 4px 20px rgba(14, 165, 233, 0.15); }
        .card-qa .card-icon { color: var(--color-qa); }
        .card-qa .tag { color: var(--color-qa); border: 1px solid rgba(14, 165, 233, 0.2); }

        .card-code:hover { border-color: var(--color-code); box-shadow: 0 4px 20px rgba(34, 197, 94, 0.15); }
        .card-code .card-icon { color: var(--color-code); }
        .card-code .tag { color: var(--color-code); border: 1px solid rgba(34, 197, 94, 0.2); }

        .card-sec:hover { border-color: var(--color-sec); box-shadow: 0 4px 20px rgba(239, 68, 68, 0.15); }
        .card-sec .card-icon { color: var(--color-sec); }
        .card-sec .tag { color: var(--color-sec); border: 1px solid rgba(239, 68, 68, 0.2); }

        /* --- PROJECTS --- */
        .projects {
            padding: 4rem 0;
            background: rgba(22, 27, 34, 0.5);
        }

        .project-card {
            background: var(--bg-body);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }
        
        .project-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-bottom: 1px solid var(--border-color);
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        .project-title {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--text-main);
        }

        .project-desc {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 1.5rem;
        }

        /* --- GITHUB STATS (SIMULATED) --- */
        .stats-section {
            padding: 4rem 0;
            text-align: center;
        }

        .contribution-graph {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 4px;
            margin-top: 2rem;
            justify-items: center;
        }

        .day {
            width: 12px;
            height: 12px;
            background-color: #161b22;
            border-radius: 2px;
        }
        /* Simulación de niveles de actividad */
        .l1 { background-color: #0e4429; }
        .l2 { background-color: #006d32; }
        .l3 { background-color: #26a641; }
        .l4 { background-color: #39d353; }

        .stats-summary {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .stat-item h4 {
            font-size: 1.8rem;
            color: var(--text-main);
        }
        .stat-item p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* --- FOOTER --- */
        footer {
            padding: 3rem 0;
            border-top: 1px solid var(--border-color);
            text-align: center;
        }

        .social-icons {
            margin-bottom: 1.5rem;
        }

        .social-icons a {
            font-size: 1.5rem;
            margin: 0 10px;
            color: var(--text-muted);
        }

        .social-icons a:hover {
            color: var(--accent);
        }

        .copyright {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .hero { text-align: center; flex-direction: column-reverse; }
            .hero h1 { font-size: 2.5rem; }
            .hero p { margin: 0 auto 2rem; }
            .nav-links { display: none; } /* En un diseño real añadiríamos menú hamburguesa */
            .logo { flex-grow: 1; text-align: center; }
            .section-title { font-size: 1.8rem; }
        }
    </style>
</head>
<body>

    <!-- NAV -->
    <header>
        <div class="container">
            <nav>
                <div class="logo mono">&lt;Dev<span class="color-accent">Profile</span>/&gt;</div>
                <ul class="nav-links">
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#especialidades">Especialidades</a></li>
                    <li><a href="#proyectos">Proyectos</a></li>
                    <li><a href="#github">Github</a></li>
                </ul>
                <a href="#contacto" class="btn mono">Contratar</a>
            </nav>
        </div>
    </header>

    <!-- HERO -->
    <section id="inicio" class="hero container">
        <div class="hero-content">
            <span class="hero-tag mono">Full Stack & Security Specialist</span>
            <h1>Construyo, Diseño y Aseguro el Futuro Digital</h1>
            <p>Ingeniero multidisciplinario apasionado por crear experiencias web visuales, asegurando la calidad del código y protegiendo sistemas contra amenazas cibernéticas.</p>
            <div style="display: flex; gap: 1rem; flex-wrap: wrap; justify-content: center; @media(min-width:768px){justify-content: flex-start;}">
                <a href="#proyectos" class="btn">Ver Portafolio</a>
                <a href="https://github.com" target="_blank" class="btn" style="background: transparent; color: var(--text-muted);"><i class="fab fa-github"></i> GitHub</a>
            </div>
        </div>
        <div class="hero-image">
            <div class="avatar-container">
                <!-- Foto de placeholder genérica de perfil -->
                <img src="https://picsum.photos/seed/devsec/300/300" alt="Foto de Perfil" class="avatar">
                <div class="status-badge mono"><i class="fas fa-circle" style="font-size: 8px; vertical-align: middle;"></i> Open to work</div>
            </div>
        </div>
    </section>

    <!-- ESPECIALIDADES (4 PILLARS) -->
    <section id="especialidades" class="pillars">
        <div class="container">
            <h2 class="section-title">Mis Pilares de Expertise</h2>
            <div class="grid-4">
                
                <!-- Diseño Web -->
                <article class="card card-web">
                    <i class="fas fa-palette card-icon"></i>
                    <h3>Diseño Web</h3>
                    <p>Creación de interfaces atractivas y funcionales centradas en el usuario (UI/UX). Experiencias visuales que cautivan.</p>
                    <div class="tech-tags">
                        <span class="tag">Figma</span>
                        <span class="tag">CSS3</span>
                        <span class="tag">Responsive</span>
                        <span class="tag">Adobe XD</span>
                    </div>
                </article>

                <!-- QA -->
                <article class="card card-qa">
                    <i class="fas fa-check-double card-icon"></i>
                    <h3>Quality Assurance</h3>
                    <p>Garantía de calidad mediante pruebas exhaustivas. Automatización de flujos para asegurar entregas sin errores.</p>
                    <div class="tech-tags">
                        <span class="tag">Selenium</span>
                        <span class="tag">Cypress</span>
                        <span class="tag">JIRA</span>
                        <span class="tag">Unit Testing</span>
                    </div>
                </article>

                <!-- Programación -->
                <article class="card card-code">
                    <i class="fas fa-code card-icon"></i>
                    <h3>Programación</h3>
                    <p>Desarrollo de software robusto y escalable. Arquitectura limpia y optimización de recursos.</p>
                    <div class="tech-tags">
                        <span class="tag">JavaScript</span>
                        <span class="tag">Python</span>
                        <span class="tag">Java</span>
                        <span class="tag">SQL</span>
                    </div>
                </article>

                <!-- Ciberseguridad -->
                <article class="card card-sec">
                    <i class="fas fa-shield-alt card-icon"></i>
                    <h3>Ciberseguridad</h3>
                    <p>Auditoría de sistemas, análisis de vulnerabilidades e implementación de protocolos de defensa.</p>
                    <div class="tech-tags">
                        <span class="tag">Pentesting</span>
                        <span class="tag">Kali Linux</span>
                        <span class="tag">OWASP</span>
                        <span class="tag">Network Sec</span>
                    </div>
                </article>

            </div>
        </div>
    </section>

    <!-- PROYECTOS -->
    <section id="proyectos" class="projects">
        <div class="container">
            <h2 class="section-title">Proyectos Destacados</h2>
            <div class="grid-4">
                
                <!-- Proyecto 1 -->
                <article class="project-card">
                    <img src="https://picsum.photos/seed/webdesign/400/200" alt="Proyecto Web" class="project-img">
                    <div class="project-content">
                        <div class="project-meta mono">
                            <span><i class="fas fa-code-branch"></i> 4</span>
                            <span style="color: var(--color-web)">Diseño Web</span>
                        </div>
                        <h3 class="project-title">Dashboard UI Moderno</h3>
                        <p class="project-desc">Interfaz administrativa con tema oscuro, gráficos interactivos y diseño totalmente responsivo.</p>
                        <a href="#" class="btn" style="padding: 5px 15px; font-size: 0.8rem;">Ver Demo</a>
                    </div>
                </article>

                <!-- Proyecto 2 -->
                <article class="project-card">
                    <img src="https://picsum.photos/seed/security/400/200" alt="Proyecto Sec" class="project-img">
                    <div class="project-content">
                        <div class="project-meta mono">
                            <span><i class="fas fa-code-branch"></i> 12</span>
                            <span style="color: var(--color-sec)">Ciberseguridad</span>
                        </div>
                        <h3 class="project-title">Network Scanner</h3>
                        <p class="project-desc">Script en Python para detectar dispositivos activos en una red local y puertos abiertos vulnerables.</p>
                        <a href="#" class="btn" style="padding: 5px 15px; font-size: 0.8rem;">Ver Repo</a>
                    </div>
                </article>

                <!-- Proyecto 3 -->
                <article class="project-card">
                    <img src="https://picsum.photos/seed/qa/400/200" alt="Proyecto QA" class="project-img">
                    <div class="project-content">
                        <div class="project-meta mono">
                            <span><i class="fas fa-code-branch"></i> 8</span>
                            <span style="color: var(--color-qa)">QA & Testing</span>
                        </div>
                        <h3 class="project-title">AutoTest E-commerce</h3>
                        <p class="project-desc">Suite de pruebas automatizadas con Selenium para validar el flujo de compra y pagos.</p>
                        <a href="#" class="btn" style="padding: 5px 15px; font-size: 0.8rem;">Ver Docs</a>
                    </div>
                </article>

                <!-- Proyecto 4 -->
                <article class="project-card">
                    <img src="https://picsum.photos/seed/code/400/200" alt="Proyecto Code" class="project-img">
                    <div class="project-content">
                        <div class="project-meta mono">
                            <span><i class="fas fa-code-branch"></i> 23</span>
                            <span style="color: var(--color-code)">Programación</span>
                        </div>
                        <h3 class="project-title">API REST Generator</h3>
                        <p class="project-desc">Generador de backend Node.js/Express con autenticación JWT y documentación Swagger incluida.</p>
                        <a href="#" class="btn" style="padding: 5px 15px; font-size: 0.8rem;">Ver Repo</a>
                    </div>
                </article>

            </div>
        </div>
    </section>

    <!-- GITHUB STATS VISUALIZATION -->
    <section id="github" class="stats-section container">
        <h2 class="section-title">Actividad en GitHub</h2>
        <p style="color: var(--text-muted);">Contribuciones y datos públicos del último año</p>
        
        <!-- Gráfica simulada con CSS -->
        <div class="contribution-graph">
            <!-- Generación aleatoria de cuadros para simular el gráfico de contribuciones de GitHub -->
            <script>
                // Pequeño script para generar los cuadritos visualmente
                // Esto es solo visual para el showcase, no conecta a la API real de GitHub
                document.addEventListener("DOMContentLoaded", () => {
                    const graph = document.querySelector('.contribution-graph');
                    const levels = ['', 'l1', 'l2', 'l3', 'l4'];
                    
                    for (let i = 0; i < 364; i++) {
                        const day = document.createElement('div');
                        day.className = 'day';
                        // Simulación aleatoria de actividad
                        const randomLevel = levels[Math.floor(Math.random() * levels.length)];
                        if (randomLevel) day.classList.add(randomLevel);
                        graph.appendChild(day);
                    }
                });
            </script>
        </div>

        <div class="stats-summary">
            <div class="stat-item">
                <h4 class="mono">1,240+</h4>
                <p>Commits</p>
            </div>
            <div class="stat-item">
                <h4 class="mono">45</h4>
                <p>Repositorios</p>
            </div>
            <div class="stat-item">
                <h4 class="mono">12</h4>
                <p>Pull Requests Merged</p>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer id="contacto">
        <div class="container">
            <div class="social-icons">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fas fa-envelope"></i></a>
            </div>
            <p class="copyright mono">&copy; 2023 DevProfile. Diseñado con <i class="fas fa-heart" style="color: var(--color-sec)"></i> y Código.</p>
        </div>
    </footer>

</body>
</html>
