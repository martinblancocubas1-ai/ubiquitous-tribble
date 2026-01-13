# ubiquitous-tribble
Proyecto por adesense 
[index.html.html](https://github.com/user-attachments/files/24579321/index.html.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Premium Tech Blog - Tecnología & Innovación</title>
    <meta name="description" content="Descubre los últimos avances en tecnología, gaming, innovación y tendencias digitales.">
    <style>
        :root {
            --color-bg-primary: #0a0e27;
            --color-bg-secondary: #1a1f3a;
            --color-bg-tertiary: #242d4d;
            --color-accent: #00d4ff;
            --color-accent-light: #00f0ff;
            --color-text-primary: #e0e6ff;
            --color-text-secondary: #a0a9d0;
            --color-success: #00ff88;
            --color-warning: #ffa500;
            --gradient-primary: linear-gradient(135deg, #00d4ff 0%, #0099ff 100%);
            --gradient-secondary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--color-bg-primary);
            color: var(--color-text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* ===== HEADER & NAV ===== */
        header {
            background: linear-gradient(180deg, var(--color-bg-secondary) 0%, var(--color-bg-primary) 100%);
            border-bottom: 2px solid var(--color-accent);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 8px 32px rgba(0, 212, 255, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 3rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--color-text-secondary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--color-accent);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* ===== TOP AD SECTION ===== */
        .ad-leaderboard-top {
            background: var(--color-bg-secondary);
            padding: 1.5rem;
            text-align: center;
            border-bottom: 1px solid var(--color-accent);
            min-height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .ad-placeholder {
            width: 100%;
            max-width: 728px;
            height: 90px;
            background: linear-gradient(45deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 153, 255, 0.1) 100%);
            border: 2px dashed var(--color-accent);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--color-text-secondary);
            font-size: 0.9rem;
            font-weight: 500;
        }

        /* ===== HERO SECTION ===== */
        .hero {
            background: linear-gradient(135deg, var(--color-bg-secondary) 0%, var(--color-bg-tertiary) 100%);
            padding: 4rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 212, 255, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            top: -100px;
            right: -100px;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideDown 0.8s ease;
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--color-text-secondary);
            margin-bottom: 2rem;
            animation: slideUp 0.8s ease 0.2s backwards;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ===== CONTAINER ===== */
        .container {
            display: grid;
            grid-template-columns: 1fr 350px;
            gap: 2rem;
            max-width: 1400px;
            margin: 3rem auto;
            padding: 0 2rem;
        }

        /* ===== CONTENT SECTIONS ===== */
        .articles {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .article-card {
            background: var(--color-bg-secondary);
            border: 1px solid var(--color-bg-tertiary);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
        }

        .article-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.2), transparent);
            transition: left 0.6s ease;
            z-index: 1;
        }

        .article-card:hover::before {
            left: 100%;
        }

        .article-card:hover {
            transform: translateY(-10px);
            border-color: var(--color-accent);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.15);
        }

        .article-image {
            width: 100%;
            height: 180px;
            background: var(--gradient-secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            position: relative;
        }

        .article-content {
            padding: 1.5rem;
            position: relative;
            z-index: 2;
        }

        .article-tag {
            display: inline-block;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.2), rgba(0, 153, 255, 0.2));
            color: var(--color-accent);
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 0.8rem;
            border: 1px solid var(--color-accent);
        }

        .article-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.8rem;
            color: var(--color-accent-light);
        }

        .article-content p {
            color: var(--color-text-secondary);
            font-size: 0.95rem;
            margin-bottom: 1rem;
        }

        .read-more {
            color: var(--color-accent);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: gap 0.3s ease;
        }

        .read-more:hover {
            gap: 1rem;
        }

        /* ===== IN-CONTENT AD ===== */
        .ad-in-content {
            background: var(--color-bg-secondary);
            padding: 2rem;
            margin: 2rem 0;
            border-left: 4px solid var(--color-accent);
            border-radius: 8px;
            text-align: center;
        }

        .ad-in-content .ad-placeholder {
            max-width: 600px;
            height: 300px;
            margin: 0 auto;
        }

        /* ===== SIDEBAR ===== */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .sidebar-widget {
            background: var(--color-bg-secondary);
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid var(--color-bg-tertiary);
        }

        .sidebar-widget h4 {
            color: var(--color-accent);
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        /* ===== AD WIDGETS ===== */
        .ad-sidebar {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .ad-box-300 {
            width: 100%;
            height: 250px;
            background: linear-gradient(45deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 153, 255, 0.1) 100%);
            border: 2px dashed var(--color-accent);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--color-text-secondary);
            font-size: 0.85rem;
            font-weight: 500;
            text-align: center;
            padding: 1rem;
        }

        /* ===== TRENDING SECTION ===== */
        .trending-list {
            list-style: none;
        }

        .trending-item {
            padding: 1rem;
            border-bottom: 1px solid var(--color-bg-tertiary);
            display: flex;
            align-items: flex-start;
            gap: 1rem;
            transition: all 0.3s ease;
        }

        .trending-item:last-child {
            border-bottom: none;
        }

        .trending-item:hover {
            background: var(--color-bg-tertiary);
            padding-left: 1.5rem;
            border-radius: 8px;
            cursor: pointer;
        }

        .trend-number {
            color: var(--color-accent);
            font-weight: 700;
            font-size: 1.2rem;
            min-width: 25px;
        }

        .trend-content h5 {
            color: var(--color-accent-light);
            font-size: 0.95rem;
            margin-bottom: 0.3rem;
        }

        .trend-content p {
            color: var(--color-text-secondary);
            font-size: 0.85rem;
        }

        /* ===== NEWSLETTER ===== */
        .newsletter {
            background: var(--gradient-secondary);
            padding: 0;
            border-radius: 12px;
            overflow: hidden;
        }

        .newsletter-content {
            padding: 1.5rem;
        }

        .newsletter-content h4 {
            color: white;
            margin-bottom: 0.5rem;
        }

        .newsletter-content p {
            color: rgba(255, 255, 255, 0.9);
            font-size: 0.85rem;
            margin-bottom: 1rem;
        }

        .newsletter-form {
            display: flex;
            gap: 0.5rem;
        }

        .newsletter-form input {
            flex: 1;
            padding: 0.6rem;
            border: none;
            border-radius: 6px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 0.9rem;
        }

        .newsletter-form input::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        .newsletter-form button {
            padding: 0.6rem 1rem;
            background: var(--color-accent);
            border: none;
            border-radius: 6px;
            color: var(--color-bg-primary);
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .newsletter-form button:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
        }

        /* ===== FOOTER ===== */
        footer {
            background: var(--color-bg-secondary);
            border-top: 2px solid var(--color-accent);
            padding: 3rem 2rem 2rem;
            margin-top: 3rem;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h5 {
            color: var(--color-accent);
            margin-bottom: 1rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.6rem;
        }

        .footer-section a {
            color: var(--color-text-secondary);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--color-accent);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid var(--color-bg-tertiary);
            color: var(--color-text-secondary);
            font-size: 0.9rem;
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            nav {
                padding: 1rem 1.5rem;
            }

            .nav-links {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .hero h1 {
                font-size: 2.2rem;
            }

            .container {
                grid-template-columns: 1fr;
            }

            .sidebar {
                order: -1;
            }

            .articles {
                grid-template-columns: 1fr;
            }

            .ad-leaderboard-top {
                padding: 1rem;
            }

            .ad-placeholder {
                height: 60px;
                max-width: 100%;
            }
        }

        /* ===== SCROLL ANIMATIONS ===== */
        .fade-in {
            opacity: 0;
            animation: fadeIn 0.8s ease forwards;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }

        /* ===== ACCESSIBILITY ===== */
        a:focus,
        button:focus {
            outline: 2px solid var(--color-accent);
            outline-offset: 2px;
        }
    </style>
</head>
<body>
    <!-- Header y Navegación -->
    <header>
        <nav>
            <div class="logo">⚡ TECHPULSE</div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#articulos">Artículos</a></li>
                <li><a href="#tendencias">Tendencias</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- AD TOP (Leaderboard 728x90) -->
    <div class="ad-leaderboard-top">
        <div class="ad-placeholder">📺 Espacio Publicitario - Google AdSense (728x90)</div>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="hero-content">
            <h1>🚀 El Futuro de la Tecnología</h1>
            <p>Descubre las últimas tendencias, innovaciones y análisis profundos sobre tech, gaming e IA</p>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <!-- Articles Grid -->
        <div>
            <div class="articles" id="articulos">
                <!-- Article 1 -->
                <div class="article-card">
                    <div class="article-image">🤖</div>
                    <div class="article-content">
                        <span class="article-tag">IA</span>
                        <h3>Inteligencia Artificial 2026</h3>
                        <p>Descubre cómo la IA está revolucionando industrias y transformando nuestro futuro con modelos avanzados...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 2 -->
                <div class="article-card">
                    <div class="article-image">🎮</div>
                    <div class="article-content">
                        <span class="article-tag">GAMING</span>
                        <h3>Consolas Next-Gen</h3>
                        <p>Las mejores consolas gaming del mercado con especificaciones ultra potentes y juegos exclusivos...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 3 -->
                <div class="article-card">
                    <div class="article-image">📱</div>
                    <div class="article-content">
                        <span class="article-tag">MOBILE</span>
                        <h3>Smartphones 2026</h3>
                        <p>Los teléfonos más innovadores con cámaras holográficas y batería de 5 días de autonomía...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 4 -->
                <div class="article-card">
                    <div class="article-image">🌐</div>
                    <div class="article-content">
                        <span class="article-tag">WEB3</span>
                        <h3>Internet Descentralizado</h3>
                        <p>Web3 y blockchain: cómo funcionan y por qué son el futuro de Internet...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 5 -->
                <div class="article-card">
                    <div class="article-image">🔐</div>
                    <div class="article-content">
                        <span class="article-tag">SEGURIDAD</span>
                        <h3>Ciberseguridad Moderna</h3>
                        <p>Protege tus datos con las últimas tecnologías de encriptación y seguridad digital...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 6 -->
                <div class="article-card">
                    <div class="article-image">☁️</div>
                    <div class="article-content">
                        <span class="article-tag">CLOUD</span>
                        <h3>Computación en la Nube</h3>
                        <p>Cloud computing: cómo empresas migran a soluciones en la nube para optimizar recursos...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>
            </div>

            <!-- IN-CONTENT AD -->
            <div class="ad-in-content">
                <div class="ad-placeholder" style="height: 300px;">📺 Anuncio Publicitario - Google AdSense (300x250 / 600x300)</div>
            </div>

            <!-- More Articles -->
            <div class="articles" style="margin-top: 2rem;">
                <!-- Article 7 -->
                <div class="article-card">
                    <div class="article-image">🚗</div>
                    <div class="article-content">
                        <span class="article-tag">AUTOTECH</span>
                        <h3>Autos Autónomos</h3>
                        <p>Vehículos autónomos con IA avanzada que revolucionan el transporte y la seguridad vial...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 8 -->
                <div class="article-card">
                    <div class="article-image">🏥</div>
                    <div class="article-content">
                        <span class="article-tag">HEALTHTECH</span>
                        <h3>Tecnología Médica</h3>
                        <p>Innovaciones en medicina: dispositivos wearables y diagnósticos con IA en tiempo real...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>

                <!-- Article 9 -->
                <div class="article-card">
                    <div class="article-image">🌍</div>
                    <div class="article-content">
                        <span class="article-tag">SOSTENIBLE</span>
                        <h3>Tech Verde</h3>
                        <p>Energías renovables y tecnología sostenible para un planeta más limpio y saludable...</p>
                        <a href="#" class="read-more">Leer más →</a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Sidebar -->
        <aside class="sidebar">
            <!-- Trending Widget -->
            <div class="sidebar-widget">
                <h4>🔥 Tendencias</h4>
                <ul class="trending-list" id="tendencias">
                    <li class="trending-item">
                        <span class="trend-number">1</span>
                        <div class="trend-content">
                            <h5>ChatGPT 5 Lanzado</h5>
                            <p>Revoluciona el mercado con capacidades 10x mayores</p>
                        </div>
                    </li>
                    <li class="trending-item">
                        <span class="trend-number">2</span>
                        <div class="trend-content">
                            <h5>Apple Vision Pro 2</h5>
                            <p>Realidad aumentada de próxima generación</p>
                        </div>
                    </li>
                    <li class="trending-item">
                        <span class="trend-number">3</span>
                        <div class="trend-content">
                            <h5>Nvidia RTX 6090</h5>
                            <p>GPU más poderosa del mercado</p>
                        </div>
                    </li>
                    <li class="trending-item">
                        <span class="trend-number">4</span>
                        <div class="trend-content">
                            <h5>Quantum Computing</h5>
                            <p>Computación cuántica accesible al público</p>
                        </div>
                    </li>
                    <li class="trending-item">
                        <span class="trend-number">5</span>
                        <div class="trend-content">
                            <h5>6G Technology</h5>
                            <p>Primeros prototipos funcionando en Japón</p>
                        </div>
                    </li>
                </ul>
            </div>

            <!-- AD SIDEBAR 300x250 -->
            <div class="sidebar-widget" style="padding: 0;">
                <div class="ad-box-300">📺 Anuncio Publicitario (300x250)</div>
            </div>

            <!-- Newsletter Widget -->
            <div class="newsletter">
                <div class="newsletter-content">
                    <h4>📧 Newsletter</h4>
                    <p>Recibe actualizaciones semanales sobre tech</p>
                    <form class="newsletter-form" onsubmit="event.preventDefault(); alert('¡Suscripción registrada!');">
                        <input type="email" placeholder="tu@email.com" required>
                        <button type="submit">→</button>
                    </form>
                </div>
            </div>

            <!-- AD SIDEBAR 300x600 (Skyscraper) -->
            <div class="sidebar-widget" style="padding: 0; display: none;">
                <div style="width: 100%; height: 600px; background: linear-gradient(45deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 153, 255, 0.1) 100%); border: 2px dashed var(--color-accent); border-radius: 8px; display: flex; align-items: center; justify-content: center; color: var(--color-text-secondary); font-size: 0.85rem; text-align: center; padding: 1rem;">
                    📺 Anuncio Publicitario (300x600)
                </div>
            </div>

            <!-- Social Widget -->
            <div class="sidebar-widget">
                <h4>🌐 Síguenos</h4>
                <div style="display: flex; gap: 1rem; flex-wrap: wrap;">
                    <a href="#" style="color: var(--color-accent); text-decoration: none; font-weight: 600;">Twitter</a>
                    <a href="#" style="color: var(--color-accent); text-decoration: none; font-weight: 600;">YouTube</a>
                    <a href="#" style="color: var(--color-accent); text-decoration: none; font-weight: 600;">Discord</a>
                </div>
            </div>
        </aside>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h5>Sobre Nosotros</h5>
                <p style="color: var(--color-text-secondary); font-size: 0.9rem;">TechPulse es la plataforma líder en cobertura de tecnología, IA y gaming. Nuestro objetivo es mantener a la comunidad informada sobre los avances más importantes del sector.</p>
            </div>
            <div class="footer-section">
                <h5>Categorías</h5>
                <ul>
                    <li><a href="#">Inteligencia Artificial</a></li>
                    <li><a href="#">Gaming</a></li>
                    <li><a href="#">Smartphones</a></li>
                    <li><a href="#">Web3</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h5>Legal</h5>
                <ul>
                    <li><a href="#">Privacidad</a></li>
                    <li><a href="#">Términos de Uso</a></li>
                    <li><a href="#">Política de Cookies</a></li>
                    <li><a href="#">Contacto</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h5>Soporte</h5>
                <ul>
                    <li><a href="#">Centro de Ayuda</a></li>
                    <li><a href="#">Reportar Problema</a></li>
                    <li><a href="#">Sugerencias</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 TechPulse. Todos los derechos reservados. | Diseño Futurista para Máximas Ganancias AdSense</p>
        </div>
    </footer>

    <script>
        // Animaciones suaves al scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.article-card').forEach(card => {
            observer.observe(card);
        });

        // Scroll animation para trending items
        const trendingItems = document.querySelectorAll('.trending-item');
        trendingItems.forEach((item, index) => {
            item.style.animationDelay = `${index * 0.1}s`;
        });

        // Interactividad
        document.querySelectorAll('.article-card').forEach(card => {
            card.addEventListener('click', function() {
                alert('En una versión real, esto te llevaría al artículo completo. ¡Los anuncios se mostrarían en el navegador!');
            });
        });

        document.querySelectorAll('.trending-item').forEach(item => {
            item.addEventListener('click', function() {
                alert('Trending item clickeado - ¡Lugar perfecto para ads de alta relevancia!');
            });
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
    </script>
</body>
</html>
