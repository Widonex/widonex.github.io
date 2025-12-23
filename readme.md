<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Widonex Studio - Начинающие проекты</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #0fce7c;
            --accent-dark: #0bb369;
            --text: #f1f1f1;
            --text-light: #b0b0b0;
            --card-bg: rgba(255, 255, 255, 0.05);
        }

        body {
            background-color: var(--primary);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background-color: var(--secondary);
            padding: 20px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-icon {
            color: var(--accent);
            font-size: 28px;
        }

        .logo-text {
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(to right, var(--accent), #2af3b6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text);
            font-size: 24px;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            text-align: center;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero h1 span {
            color: var(--accent);
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-light);
            max-width: 700px;
            margin: 0 auto 40px;
        }

        .cta-button {
            display: inline-block;
            background-color: var(--accent);
            color: var(--primary);
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s;
            border: 2px solid var(--accent);
        }

        .cta-button:hover {
            background-color: transparent;
            color: var(--accent);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(15, 206, 124, 0.2);
        }

        /* Projects Section */
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--accent);
            border-radius: 2px;
        }

        .projects {
            padding: 100px 0;
            background-color: var(--primary);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border-color: rgba(15, 206, 124, 0.3);
        }

        .project-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: var(--accent);
            color: var(--primary);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 700;
            z-index: 2;
        }

        .project-img {
            height: 200px;
            width: 100%;
            background-color: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: var(--accent);
        }

        .project-content {
            padding: 25px;
        }

        .project-title {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--accent);
        }

        .project-description {
            color: var(--text-light);
            margin-bottom: 20px;
        }

        .project-features {
            list-style-type: none;
            margin-bottom: 25px;
        }

        .project-features li {
            padding: 5px 0;
            padding-left: 25px;
            position: relative;
        }

        .project-features li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: bold;
        }

        .project-link {
            display: inline-block;
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
        }

        .project-link:hover {
            color: #2af3b6;
            text-decoration: underline;
        }

        /* About Section */
        .about {
            padding: 100px 0;
            background-color: var(--secondary);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-text {
            flex: 1;
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .about-text p {
            color: var(--text-light);
            margin-bottom: 20px;
        }

        .about-stats {
            display: flex;
            justify-content: space-between;
            margin-top: 40px;
        }

        .stat {
            text-align: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--accent);
            display: block;
        }

        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .about-visual {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .studio-logo {
            font-size: 200px;
            color: var(--accent);
            opacity: 0.7;
        }

        /* Roadmap Section */
        .roadmap {
            padding: 100px 0;
            background-color: var(--primary);
        }

        .roadmap-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .roadmap-item {
            display: flex;
            margin-bottom: 50px;
            position: relative;
        }

        .roadmap-item:last-child {
            margin-bottom: 0;
        }

        .roadmap-date {
            min-width: 120px;
            font-weight: 700;
            color: var(--accent);
            position: relative;
            padding-top: 5px;
        }

        .roadmap-date::after {
            content: '';
            position: absolute;
            top: 10px;
            right: -20px;
            width: 20px;
            height: 20px;
            background-color: var(--accent);
            border-radius: 50%;
            z-index: 2;
        }

        .roadmap-content {
            flex: 1;
            padding-left: 50px;
            border-left: 2px solid rgba(255, 255, 255, 0.1);
            position: relative;
        }

        .roadmap-content::before {
            content: '';
            position: absolute;
            top: 10px;
            left: -8px;
            width: 14px;
            height: 14px;
            background-color: var(--primary);
            border: 2px solid var(--accent);
            border-radius: 50%;
        }

        .roadmap-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--accent);
        }

        .roadmap-description {
            color: var(--text-light);
        }

        /* Footer */
        footer {
            background-color: #0d0d1a;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column {
            flex: 1;
            min-width: 250px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--accent);
        }

        .footer-links {
            list-style-type: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: var(--text-light);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--accent);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--text);
            font-size: 18px;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background-color: var(--accent);
            color: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text-light);
            font-size: 0.9rem;
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .about-content {
                flex-direction: column;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--secondary);
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 10px 15px rgba(0, 0, 0, 0.2);
                z-index: 100;
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .about-stats {
                flex-wrap: wrap;
                gap: 30px;
            }
            
            .roadmap-item {
                flex-direction: column;
            }
            
            .roadmap-content {
                padding-left: 0;
                border-left: none;
                padding-top: 20px;
            }
            
            .roadmap-content::before {
                display: none;
            }
            
            .roadmap-date::after {
                display: none;
            }
        }

        @media (max-width: 480px) {
            .hero {
                padding: 70px 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .studio-logo {
                font-size: 150px;
            }
        }

        /* Animation */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animate-fade-in-up {
            animation: fadeInUp 0.8s ease-out forwards;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-cube"></i>
                    </div>
                    <div class="logo-text">Widonex Studio</div>
                </div>
                
                <nav>
                    <button class="mobile-menu-btn" id="mobileMenuBtn">
                        <i class="fas fa-bars"></i>
                    </button>
                    <div class="nav-links" id="navLinks">
                        <a href="#home">Главная</a>
                        <a href="#projects">Проекты</a>
                        <a href="#roadmap">Развитие</a>
                        <a href="#about">О студии</a>
                        <a href="#contact">Контакты</a>
                    </div>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1 class="animate-fade-in-up">Начинающие проекты от <span>Widonex Studio</span></h1>
            <p class="animate-fade-in-up">Молодая студия, которая создает простые и полезные приложения для Android. Наши проекты только начинают свой путь, но уже сейчас они предлагают уникальные возможности для пользователей.</p>
            <a href="#projects" class="cta-button animate-fade-in-up">Узнать о проектах</a>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects" id="projects">
        <div class="container">
            <h2 class="section-title">Наши проекты</h2>
            <div class="projects-grid">
                <!-- TSRI STORE -->
                <div class="project-card animate-fade-in-up">
                    <div class="project-badge">Начинающий</div>
                    <div class="project-img">
                        <i class="fas fa-store"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">TSRI STORE</h3>
                        <p class="project-description">Начинающий магазин приложений для Android с простым интерфейсом и базовым набором функций. Наш первый шаг в создании собственной экосистемы приложений.</p>
                        <ul class="project-features">
                            <li>Каталог приложений для Android</li>
                            <li>Простой и понятный интерфейс</li>
                            <li>Базовая система категорий</li>
                            <li>Возможность загрузки приложений</li>
                            <li>Поиск по названию приложений</li>
                        </ul>
                        <a href="#" class="project-link">Скачать в разработке <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- TSRI BROWSER -->
                <div class="project-card animate-fade-in-up">
                    <div class="project-badge">Начинающий</div>
                    <div class="project-img">
                        <i class="fas fa-globe"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">TSRI BROWSER</h3>
                        <p class="project-description">Легкий и быстрый браузер для Android с минималистичным дизайном. Без лишних функций и сложных настроек - только основа для комфортного серфинга.</p>
                        <ul class="project-features">
                            <li>Быстрая загрузка страниц</li>
                            <li>Минималистичный интерфейс</li>
                            <li>Вкладки и история просмотров</li>
                            <li>Поисковая строка</li>
                            <li>Закладки</li>
                        </ul>
                        <a href="#" class="project-link">Скачать в разработке <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- TSRICHAT -->
                <div class="project-card animate-fade-in-up">
                    <div class="project-badge">Начинающий</div>
                    <div class="project-img">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">TSRICHAT</h3>
                        <p class="project-description">Начинающий ИИ-помощник для Android, который умеет отвечать на вопросы и помогать с базовыми задачами. Постоянно учится и улучшает свои ответы.</p>
                        <ul class="project-features">
                            <li>Ответы на вопросы</li>
                            <li>Поддержка русского языка</li>
                            <li>Обучение на основе диалогов</li>
                            <li>Простой чат-интерфейс</li>
                            <li>Базовые знания по разным темам</li>
                        </ul>
                        <a href="#" class="project-link">Скачать в разработке <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Roadmap Section -->
    <section class="roadmap" id="roadmap">
        <div class="container">
            <h2 class="section-title">Планы развития</h2>
            <div class="roadmap-container">
                <div class="roadmap-item animate-fade-in-up">
                    <div class="roadmap-date">2024 Q1</div>
                    <div class="roadmap-content">
                        <h3 class="roadmap-title">Запуск первых версий</h3>
                        <p class="roadmap-description">Выпуск базовых версий TSRI STORE, TSRI BROWSER и TSRICHAT с минимальным набором функций для тестирования.</p>
                    </div>
                </div>
                
                <div class="roadmap-item animate-fade-in-up">
                    <div class="roadmap-date">2024 Q2</div>
                    <div class="roadmap-content">
                        <h3 class="roadmap-title">Добавление функций</h3>
                        <p class="roadmap-description">Расширение возможностей приложений на основе отзывов первых пользователей.</p>
                    </div>
                </div>
                
                <div class="roadmap-item animate-fade-in-up">
                    <div class="roadmap-date">2024 Q3</div>
                    <div class="roadmap-content">
                        <h3 class="roadmap-title">Интеграция между проектами</h3>
                        <p class="roadmap-description">Создание единой экосистемы, где приложения будут работать вместе и обмениваться данными.</p>
                    </div>
                </div>
                
                <div class="roadmap-item animate-fade-in-up">
                    <div class="roadmap-date">2024 Q4</div>
                    <div class="roadmap-content">
                        <h3 class="roadmap-title">Публичный релиз</h3>
                        <p class="roadmap-description">Официальный запуск всех проектов в Google Play Store и других платформах.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <h2 class="section-title">О студии</h2>
            <div class="about-content">
                <div class="about-text">
                    <h2>Widonex Studio</h2>
                    <p>Мы - небольшая команда энтузиастов, которые верят, что даже начинающие проекты могут быть полезными. Наша студия создает простые и понятные приложения для Android, которые решают конкретные задачи пользователей.</p>
                    <p>Основанная в 2023 году, Widonex Studio фокусируется на трех основных проектах: магазин приложений, браузер и ИИ-помощник. Мы начинаем с малого, но планируем постоянно развивать и улучшать наши продукты.</p>
                    
                    <div class="about-stats">
                        <div class="stat">
                            <span class="stat-number">3</span>
                            <span class="stat-label">Активных проекта</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">0</span>
                            <span class="stat-label">Пока нет релиза</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">4</span>
                            <span class="stat-label">Члена команды</span>
                        </div>
                        <div class="stat">
                            <span class="stat-number">2023</span>
                            <span class="stat-label">Год основания</span>
                        </div>
                    </div>
                </div>
                
                <div class="about-visual">
                    <div class="studio-logo">
                        <i class="fas fa-seedling"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Widonex Studio</h3>
                    <p>Молодая студия, создающая начинающие проекты для Android. Мы верим в простые и полезные решения.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-vk"></i></a>
                        <a href="#"><i class="fab fa-google-play"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Наши проекты</h3>
                    <ul class="footer-links">
                        <li><a href="#projects">TSRI STORE</a></li>
                        <li><a href="#projects">TSRI BROWSER</a></li>
                        <li><a href="#projects">TSRICHAT</a></li>
                        <li><a href="#roadmap">Планы развития</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Контакты</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-envelope"></i> contact@widonex.studio</li>
                        <li><i class="fas fa-map-marker-alt"></i> Россия</li>
                        <li><i class="fas fa-mobile-alt"></i> Только Android проекты</li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Поддержать проекты</h3>
                    <p>Наши проекты находятся в начале пути. Если вам интересна наша работа, подпишитесь на обновления.</p>
                    <form id="subscribeForm">
                        <input type="email" placeholder="Ваш email" style="width: 100%; padding: 10px; margin-bottom: 10px; border-radius: 5px; border: 1px solid #444; background: rgba(255,255,255,0.1); color: white;">
                        <button type="submit" class="cta-button" style="padding: 10px 20px; font-size: 0.9rem;">Подписаться</button>
                    </form>
                </div>
            </div>
            
            <div class="copyright">
                &copy; 2023 Widonex Studio. Начинающие проекты в разработке.
            </div>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.getElementById('navLinks');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            mobileMenuBtn.innerHTML = navLinks.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    entry.target.classList.add('animate-fade-in-up');
                }
            });
        }, observerOptions);
        
        // Observe elements to animate
        document.querySelectorAll('.project-card, .roadmap-item, .about-content, .footer-content').forEach(el => {
            observer.observe(el);
        });
        
        // Form submission
        const subscribeForm = document.getElementById('subscribeForm');
        subscribeForm.addEventListener('submit', function(e) {
            e.preventDefault();
            const email = this.querySelector('input[type="email"]').value;
            if(email) {
                alert(`Спасибо за интерес к нашим проектам, ${email}! Вы будете получать новости о наших приложениях.`);
                this.reset();
            }
        });
        
        // Add "В разработке" notification for project links
        document.querySelectorAll('.project-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                alert('Этот проект находится в разработке. Скоро будет доступен для скачивания!');
            });
        });
    </script>
</body>
</html>
