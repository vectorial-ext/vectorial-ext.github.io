# vectorial-ext.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vectorial - Premium Roblox Software</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Poppins:wght@600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #04040a; 
            --bg-secondary: #0c0c16;
            --bg-card: #12121e;
            --text-primary: #ffffff;
            --text-secondary: #a0a0b0; 
            --accent-1: #00d4aa; 
            --accent-2: #0099ff; 
            --accent-3: #7c3aed; 
            --gradient-1: linear-gradient(135deg, #00d4aa 0%, #0099ff 100%);
            --gradient-2: linear-gradient(135deg, #7c3aed 0%, #00d4aa 100%);
            --gradient-3: linear-gradient(135deg, #0099ff 0%, #7c3aed 100%);
            --glow-color: rgba(0, 212, 170, 0.5);
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-primary);
            color: var(--text-primary);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
        }

        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: 
                radial-gradient(ellipse at 15% 15%, rgba(0, 212, 170, 0.12) 0%, transparent 40%),
                radial-gradient(ellipse at 85% 85%, rgba(0, 153, 255, 0.12) 0%, transparent 40%),
                radial-gradient(ellipse at 50% 50%, rgba(124, 58, 237, 0.08) 0%, transparent 60%),
                var(--bg-primary);
            filter: blur(5px);
            animation: backgroundShift 30s infinite alternate ease-in-out;
        }
        
        .decorative-lines {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.2; 
            background: repeating-linear-gradient(
                -45deg,
                rgba(0, 212, 170, 0.1),
                rgba(0, 212, 170, 0.1) 1px,
                transparent 1px,
                transparent 150px 
            ),
            repeating-linear-gradient(
                45deg,
                rgba(0, 153, 255, 0.1),
                rgba(0, 153, 255, 0.1) 1px,
                transparent 1px,
                transparent 150px
            );
            background-size: 300% 300%;
            animation: moveLines 60s linear infinite; 
        }
        
        @keyframes moveLines {
            0% { background-position: 0 0; }
            100% { background-position: 300px 300px; } 
        }

        @keyframes backgroundShift {
            0% { background-position: 0% 0%, 100% 100%, 50% 50%; }
            100% { background-position: 20% 80%, 80% 20%, 50% 50%; }
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 80px; 
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            backdrop-filter: blur(25px); 
            background: rgba(4, 4, 10, 0.9);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
        }

        .logo {
            font-family: 'Poppins', sans-serif;
            font-size: 28px;
            font-weight: 800;
            letter-spacing: -1px;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 50px; 
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-1);
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--text-primary);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 180px 20px 80px; 
        }

        .hero h1 {
            font-family: 'Poppins', sans-serif;
            font-size: clamp(60px, 10vw, 100px); 
            font-weight: 800;
            margin-bottom: 25px;
            letter-spacing: -2px;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 20px var(--glow-color); 
        }

        .hero p {
            font-size: 22px;
            color: var(--text-secondary);
            max-width: 700px;
            margin-bottom: 50px;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 18px 45px;
            border-radius: 14px; 
            font-size: 18px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            border: none;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .btn-primary {
            background: var(--gradient-1);
            background-size: 300% 300%;
            color: var(--bg-primary);
            box-shadow: 0 15px 45px rgba(0, 212, 170, 0.4);
            animation: gradientIdle 4s ease infinite;
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-2);
            opacity: 0;
            transition: opacity 0.5s ease;
            z-index: -1;
            border-radius: 14px;
        }

        .btn-primary:hover::before {
            opacity: 1;
        }

        .btn-primary:hover {
            transform: translateY(-8px) scale(1.04);
            box-shadow: 0 30px 70px rgba(124, 58, 237, 0.5);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.08); 
            color: var(--text-primary);
            border: 2px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
        }

        .btn-secondary::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(124, 58, 237, 0.3) 0%, rgba(0, 212, 170, 0.3) 100%);
            opacity: 0;
            transition: opacity 0.4s ease;
            z-index: -1;
            border-radius: 12px;
        }

        .btn-secondary:hover::before {
            opacity: 1;
        }

        .btn-secondary:hover {
            border-color: var(--accent-1);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 212, 170, 0.2);
        }

        @keyframes gradientIdle {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .pricing {
            padding: 120px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-title h2 {
            font-family: 'Poppins', sans-serif;
            font-size: 56px;
            font-weight: 700;
            margin-bottom: 20px;
            letter-spacing: -1px;
            background: var(--gradient-2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-title p {
            color: var(--text-secondary);
            font-size: 20px;
        }

        .pricing-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .pricing-card {
            background: var(--bg-card);
            border-radius: 30px; 
            padding: 50px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            
            display: flex;
            flex-direction: column;
        }

        .pricing-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: var(--gradient-1);
            opacity: 0;
            transition: opacity 0.4s ease;
        }
        
        .pricing-card::after {
            content: '';
            position: absolute;
            bottom: -50%;
            left: 50%;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(0, 212, 170, 0.1) 0%, transparent 70%);
            transform: translateX(-50%);
            transition: all 0.5s ease;
            z-index: 0;
        }

        .pricing-card:hover {
            transform: translateY(-15px) scale(1.03);
            border-color: rgba(0, 212, 170, 0.5);
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.4);
        }

        .pricing-card:hover::before {
            opacity: 1;
        }
        
        .pricing-card:hover::after {
            bottom: -20%;
            width: 150%;
            height: 150%;
        }

        .pricing-card.featured {
            border-color: var(--accent-1);
            background: linear-gradient(180deg, rgba(0, 212, 170, 0.08) 0%, var(--bg-card) 100%);
            box-shadow: 0 10px 40px rgba(0, 212, 170, 0.3);
        }

        .pricing-card.featured::before {
            opacity: 1;
            background: var(--gradient-2);
        }

        .card-badge {
            position: absolute;
            top: 30px;
            right: 30px;
            background: var(--gradient-2);
            padding: 8px 18px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 700;
            color: white;
            box-shadow: 0 5px 15px rgba(124, 58, 237, 0.5);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .card-title {
            font-family: 'Poppins', sans-serif;
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 15px;
            letter-spacing: 0.5px;
        }

        .card-price {
            font-size: 64px;
            font-weight: 800;
            margin-bottom: 5px;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 10px rgba(0, 212, 170, 0.2);
        }

        .card-period {
            color: var(--text-secondary);
            font-size: 16px;
            margin-bottom: 40px;
            font-weight: 500;
            text-transform: uppercase;
        }

        .features-list {
            list-style: none;
            margin-bottom: 40px;
            position: relative;
            z-index: 1;
        }

        .features-list li {
            padding: 14px 0;
            display: flex;
            align-items: center;
            gap: 15px;
            color: var(--text-secondary);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            font-weight: 400;
            transition: color 0.3s ease;
        }
        
        .features-list li:hover {
            color: var(--text-primary);
        }

        .features-list li:last-child {
            border-bottom: none;
        }

        .features-list li::before {
            content: '✓';
            color: var(--accent-1);
            font-weight: 700;
            font-size: 16px;
        }

        .features-list li.disabled {
            opacity: 0.5;
            text-decoration: line-through;
        }

        .features-list li.disabled::before {
            content: '✕';
            color: #ff4757;
        }

        .card-btn {
            width: 100%;
            padding: 18px;
            border-radius: 14px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            border: none;
            background: var(--gradient-1);
            color: var(--bg-primary);
            position: relative;
            overflow: hidden;
            z-index: 1;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 10px 30px rgba(0, 212, 170, 0.3);
            text-align: center; 
            display: block; 
            text-decoration: none; 
            
            margin-top: auto; 
        }

        .card-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--gradient-3);
            opacity: 0;
            transition: opacity 0.5s ease;
            z-index: -1;
            border-radius: 14px;
        }

        .card-btn:hover::before {
            opacity: 1;
        }

        .card-btn:hover {
            transform: scale(1.03) translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 153, 255, 0.4);
        }

        .pricing-card.featured .card-btn {
            background: var(--gradient-2);
            box-shadow: 0 10px 30px rgba(124, 58, 237, 0.4);
        }

        .pricing-card.featured .card-btn::before {
            background: var(--gradient-1);
        }

        .features {
            padding: 120px 20px;
            background: var(--bg-secondary);
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .features .section-title h2 {
            background: var(--gradient-3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-card {
            background: var(--bg-card);
            padding: 40px;
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 60px;
            height: 60px;
            background: var(--accent-1);
            border-radius: 50%;
            filter: blur(40px);
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .feature-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent-1);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }
        
        .feature-card:hover::before {
            opacity: 0.3;
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            border-radius: 16px;
            background: var(--gradient-1);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            margin-bottom: 25px;
            box-shadow: 0 8px 20px rgba(0, 212, 170, 0.3);
        }

        .feature-card h3 {
            font-family: 'Poppins', sans-serif;
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .feature-card p {
            color: var(--text-secondary);
            font-weight: 300;
        }

        footer {
            padding: 80px 20px;
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.08);
            background: var(--bg-secondary);
        }

        footer p {
            color: var(--text-secondary);
            font-size: 16px;
        }

        .discord-link {
            color: var(--accent-1);
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s ease;
        }

        .discord-link:hover {
            color: var(--accent-2);
            text-decoration: underline;
        }

        @media (max-width: 992px) {
            nav {
                padding: 15px 40px;
            }
            .pricing-cards {
                grid-template-columns: 1fr;
            }
            .hero h1 {
                font-size: clamp(48px, 12vw, 80px);
            }
            .section-title h2 {
                font-size: 40px;
            }
        }
        
        @media (max-width: 768px) {
            nav {
                padding: 15px 20px;
            }
            .nav-links {
                display: none;
            }
            .hero {
                padding-top: 120px;
            }
            .hero p {
                font-size: 18px;
            }
            .pricing-card {
                padding: 35px;
            }
            .card-price {
                font-size: 52px;
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeIn 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .delay-1 { animation-delay: 0.15s; }
        .delay-2 { animation-delay: 0.3s; }
        .delay-3 { animation-delay: 0.45s; }
        .delay-4 { animation-delay: 0.6s; }
        .delay-5 { animation-delay: 0.75s; }
    </style>
</head>
<body>
    <div class="bg-animation">
        <div class="decorative-lines"></div>
    </div>

    <nav>
        <div class="logo">vectorial</div>
        <div class="nav-links">
            <a href="#pricing">Цены</a>
            <a href="#features">Функции</a>
            <a href="https://discord.gg/Uw7Y3gHuHZ">Discord</a>
        </div>
    </nav>

    <section class="hero">
        <h1 class="fade-in">VECTORIAL.WIN</h1>
        <p class="fade-in delay-1">Премиум софт для **Roblox** с передовыми функциями. Безопасность, производительность и стиль в одном решении, разработанном для превосходства.</p>
        <div class="hero-buttons fade-in delay-2">
            <a href="#pricing" class="btn btn-primary">⚡ Купить сейчас</a>
            <a href="https://discord.gg/Uw7Y3gHuHZ" class="btn btn-secondary" target="_blank">💬 Discord сервер</a>
        </div>
    </section>

    <section class="pricing" id="pricing">
        <div class="section-title fade-in">
            <h2>Выберите план</h2>
            <p>Доступные цены для каждого с мгновенным доступом</p>
        </div>

        <div class="pricing-cards">
            <div class="pricing-card fade-in delay-1">
                <div class="card-title">Default</div>
                <div class="card-price">50₽</div>
                <div class="card-period">разовая покупка</div>
                <ul class="features-list">
                    <li>Aimbot (Camera Lock)</li>
                    <li>ESP (Boxes, Names, Health)</li>
                    <li>Triggerbot</li>
                    <li>Speed Hack</li>
                    <li>Flight</li>
                    <li class="disabled">Silent Aim</li>
                    <li class="disabled">Anti-Aim</li>
                    <li class="disabled">Orbit</li>
                    <li class="disabled">Spinbot</li>
                    <li class="disabled">Chams & Glow ESP</li>
                    <li class="disabled">Radar</li>
                    <li class="disabled">Автообновление</li>
                </ul>
                <a href="https://discord.gg/Uw7Y3gHuHZ" target="_blank" class="card-btn">Выбрать Default</a>
            </div>

            <div class="pricing-card featured fade-in delay-2">
                <div class="card-badge">⭐ Популярный</div>
                <div class="card-title">Alpha</div>
                <div class="card-price">150₽</div>
                <div class="card-period">разовая покупка</div>
                <ul class="features-list">
                    <li>Всё из Default</li>
                    <li>Silent Aim</li>
                    <li>Anti-Aim</li>
                    <li>Orbit</li>
                    <li>Spinbot</li>
                    <li>Chams & Glow ESP</li>
                    <li>Radar</li>
                    <li>Автообновление</li>
                </ul>
                <a href="https://discord.gg/Uw7Y3gHuHZ" target="_blank" class="card-btn">Выбрать Alpha</a>
            </div>
        </div>
    </section>

    <section class="features" id="features">
        <div class="section-title fade-in">
            <h2>Почему Vectorial?</h2>
            <p>Преимущества, которые выводят ваш игровой опыт на новый уровень</p>
        </div>

        <div class="features-grid">
            <div class="feature-card fade-in delay-1">
                <div class="feature-icon">🎯</div>
                <h3>Точный Aimbot</h3>
                <p>Продвинутый аимбот с настройкой smoothing, predictions, выбором частей тела и максимальной легитностью.</p>
            </div>

            <div class="feature-card fade-in delay-2">
                <div class="feature-icon">👁️</div>
                <h3>Полный ESP</h3>
                <p>Boxes, скелеты, здоровье, дистанция, имена, линии взгляда и многое другое для полного видения поля боя.</p>
            </div>

            <div class="feature-card fade-in delay-3">
                <div class="feature-icon">⚡</div>
                <h3>Непревзойденная Производительность</h3>
                <p>Оптимизированный внешний код гарантирует максимальный FPS и отсутствие лагов, даже на слабых ПК.</p>
            </div>

            <div class="feature-card fade-in delay-4">
                <div class="feature-icon">🔄</div>
                <h3>Автоматическое Обновление</h3>
                <p>Автоматические обновления оффсетов и функций через KeyAuth без необходимости ручной загрузки.</p>
            </div>

            <div class="feature-card fade-in delay-5">
                <div class="feature-icon">🛡️</div>
                <h3>Максимальная Безопасность</h3>
                <p>Внешний чит (External) без прямого инжекта в процесс - минимальный риск бана и обнаружения анти-читами.</p>
            </div>

            <div class="feature-card fade-in delay-1">
                <div class="feature-icon">💬</div>
                <h3>Поддержка 24/7</h3>
                <p>Активное сообщество в Discord, детальные гайды и быстрая техническая помощь от разработчиков.</p>
            </div>
        </div>
    </section>

    <footer>
        <p>© 2025 vectorial.win. Все права защищены. — <a href="https://discord.gg/Uw7Y3gHuHZ" class="discord-link">Discord Сообщество</a></p>
    </footer>

    <script>
        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                if (anchor.target !== '_blank') {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Intersection Observer for animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationPlayState = 'running';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.fade-in').forEach(el => {
            el.style.animationPlayState = 'paused';
            observer.observe(el);
        });
    </script>
</body>
</html>
