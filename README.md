<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Мой сайт · GitHub Pages</title>
    <!-- Стили -->
    <style>
        /* Общие сбросы и шрифты */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            background: #f9fafb;
            color: #1e293b;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* Контейнер */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }

        /* Шапка */
        header {
            background: #ffffff;
            border-bottom: 1px solid #e9edf4;
            padding: 1.2rem 0;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.02);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 600;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #2563eb, #7c3aed);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            align-items: center;
            flex-wrap: wrap;
        }

        .nav-links a {
            text-decoration: none;
            color: #334155;
            font-weight: 500;
            font-size: 1rem;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: #2563eb;
        }

        .btn-outline {
            border: 1.5px solid #2563eb;
            padding: 0.4rem 1.2rem;
            border-radius: 30px;
            color: #2563eb !important;
            font-weight: 600;
            transition: all 0.2s;
        }

        .btn-outline:hover {
            background: #2563eb;
            color: #fff !important;
        }

        /* Герой */
        .hero {
            padding: 4rem 0 3rem;
            text-align: center;
        }

        .hero h1 {
            font-size: 3.2rem;
            font-weight: 700;
            letter-spacing: -1px;
            line-height: 1.2;
            margin-bottom: 1rem;
        }

        .hero h1 span {
            background: linear-gradient(135deg, #2563eb, #7c3aed);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.25rem;
            color: #475569;
            max-width: 600px;
            margin: 0 auto 2rem;
        }

        .btn-primary {
            display: inline-block;
            background: #2563eb;
            color: #fff;
            padding: 0.75rem 2.2rem;
            border-radius: 40px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: 0 4px 12px rgba(37, 99, 235, 0.25);
            transition: background 0.2s, transform 0.1s;
            border: none;
            cursor: pointer;
        }

        .btn-primary:hover {
            background: #1d4ed8;
            transform: scale(1.02);
        }

        .badge-github {
            margin-top: 2rem;
            display: inline-block;
            background: #eef2f6;
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            font-size: 0.9rem;
            color: #1e293b;
        }

        .badge-github i {
            font-style: normal;
            background: #1e293b;
            color: #fff;
            padding: 0.1rem 0.6rem;
            border-radius: 20px;
            margin-right: 0.4rem;
            font-weight: 600;
        }

        /* Секция возможностей */
        .features {
            padding: 3rem 0 4rem;
        }

        .features h2 {
            font-size: 2.2rem;
            font-weight: 600;
            text-align: center;
            margin-bottom: 2.5rem;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
            gap: 2rem;
        }

        .card {
            background: #ffffff;
            padding: 2rem 1.5rem;
            border-radius: 24px;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.04);
            transition: transform 0.2s, box-shadow 0.2s;
            border: 1px solid #f1f5f9;
            text-align: center;
        }

        .card:hover {
            transform: translateY(-6px);
            box-shadow: 0 16px 40px rgba(0, 0, 0, 0.06);
        }

        .card-icon {
            font-size: 2.8rem;
            margin-bottom: 0.6rem;
        }

        .card h3 {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .card p {
            color: #64748b;
            font-size: 0.95rem;
        }

        /* Секция "О проекте" */
        .about {
            background: #ffffff;
            padding: 3.5rem 0;
            border-radius: 40px 40px 0 0;
            margin-top: 1rem;
            box-shadow: 0 -4px 20px rgba(0, 0, 0, 0.02);
        }

        .about-content {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            max-width: 700px;
            margin: 0 auto;
            text-align: center;
        }

        .about-content h2 {
            font-size: 2rem;
            font-weight: 600;
        }

        .about-content p {
            color: #475569;
            font-size: 1.05rem;
        }

        .about-content code {
            background: #f1f5f9;
            padding: 0.2rem 0.8rem;
            border-radius: 30px;
            font-size: 0.9rem;
            color: #0f172a;
        }

        /* Футер */
        footer {
            margin-top: auto;
            background: #ffffff;
            border-top: 1px solid #e9edf4;
            padding: 1.8rem 0;
            text-align: center;
            color: #64748b;
            font-size: 0.95rem;
        }

        footer .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .footer-links a {
            color: #334155;
            text-decoration: none;
            margin: 0 0.8rem;
            transition: color 0.2s;
        }

        .footer-links a:hover {
            color: #2563eb;
        }

        /* Адаптив */
        @media (max-width: 650px) {
            .header-content {
                flex-direction: column;
                align-items: flex-start;
            }

            .hero h1 {
                font-size: 2.4rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            footer .container {
                flex-direction: column;
                gap: 0.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- ШАПКА -->
    <header>
        <div class="container header-content">
            <div class="logo">✦ mypage</div>
            <nav class="nav-links">
                <a href="#">Главная</a>
                <a href="#features">Возможности</a>
                <a href="#about">О проекте</a>
                <a href="#" class="btn-outline">GitHub</a>
            </nav>
        </div>
    </header>

    <!-- ГЛАВНЫЙ БЛОК -->
    <main>
        <div class="container hero">
            <h1>Сайт на <span>GitHub Pages</span></h1>
            <p>
                Быстрый старт для вашего проекта. 
                Простота, стиль и готовность к публикации.
            </p>
            <a href="#" class="btn-primary">Начать →</a>
            <div class="badge-github">
                <i>⌨</i> готов к деплою · репозиторий
            </div>
        </div>

        <!-- СЕКЦИЯ ВОЗМОЖНОСТЕЙ -->
        <section class="features" id="features">
            <div class="container">
                <h2>Почему этот шаблон</h2>
                <div class="grid">
                    <div class="card">
                        <div class="card-icon">⚡</div>
                        <h3>Мгновенный деплой</h3>
                        <p>Загрузите на GitHub — и сайт уже работает. Без серверов и настроек.</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">🎨</div>
                        <h3>Современный дизайн</h3>
                        <p>Минимализм, градиенты, адаптивность — всё готово для вашего контента.</p>
                    </div>
                    <div class="card">
                        <div class="card-icon">🔧</div>
                        <h3>Легко править</h3>
                        <p>Один HTML-файл. Меняйте текст, цвета, блоки — без лишних сложностей.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- СЕКЦИЯ О ПРОЕКТЕ -->
        <section class="about" id="about">
            <div class="container about-content">
                <h2>О проекте</h2>
                <p>
                    Этот сайт создан как стартовая точка для вашего присутствия на 
                    <strong>GitHub Pages</strong>. 
                    Весь код в одном файле — просто скачайте, измените под себя и 
                    загрузите в репозиторий.
                </p>
                <p>
                    <code>index.html</code> — всё, что нужно. 
                    Подходит для личной страницы, портфолио или демо-проекта.
                </p>
            </div>
        </section>
    </main>

    <!-- ФУТЕР -->
    <footer>
        <div class="container">
            <span>© 2026 · Сделано для GitHub Pages</span>
            <div class="footer-links">
                <a href="#">Документация</a>
                <a href="#">Репозиторий</a>
                <a href="#">Контакты</a>
            </div>
        </div>
    </footer>

    <!-- Небольшой скрипт для интерактива (пример) -->
    <script>
        // Приветствие в консоли (можно убрать)
        console.log('🚀 Сайт готов для GitHub Pages!');

        // Простое поведение для кнопки "Начать" (демо)
        const startBtn = document.querySelector('.btn-primary');
        if (startBtn) {
            startBtn.addEventListener('click', (e) => {
                e.preventDefault();
                alert('✨ Отлично! Теперь настройте контент под себя и деплойте на GitHub.');
            });
        }
    </script>
</body>
</html>
