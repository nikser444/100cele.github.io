<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>100 Целей - Путь к Лучшему Будущему</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        header {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 100px 20px 60px;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            animation: slideDown 1s ease-out;
            text-shadow: 2px 2px 20px rgba(0, 0, 0, 0.3);
        }

        .subtitle {
            font-size: 1.5rem;
            opacity: 0.9;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 0.9; }
        }

        .container {
            position: relative;
            z-index: 10;
            max-width: 1400px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .filter-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 50px;
        }

        .filter-btn {
            padding: 12px 30px;
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            color: #fff;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            backdrop-filter: blur(10px);
        }

        .filter-btn:hover, .filter-btn.active {
            background: rgba(255, 255, 255, 0.9);
            color: #667eea;
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .goals-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .goal-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.4s ease;
            cursor: pointer;
            animation: fadeInUp 0.6s ease-out;
            animation-fill-mode: both;
        }

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

        .goal-card:hover {
            transform: translateY(-10px) scale(1.02);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
        }

        .goal-number {
            display: inline-block;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: #fff;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
            margin-bottom: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .goal-title {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 10px;
        }

        .goal-category {
            display: inline-block;
            padding: 5px 15px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            font-size: 0.85rem;
            margin-top: 10px;
        }

        .progress-section {
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-top: 60px;
            text-align: center;
        }

        .progress-bar {
            width: 100%;
            height: 30px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            overflow: hidden;
            margin: 20px 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #4facfe 0%, #00f2fe 100%);
            width: 0%;
            transition: width 2s ease-out;
            animation: progressAnimation 2s ease-out forwards;
        }

        @keyframes progressAnimation {
            to { width: 12%; }
        }

        footer {
            text-align: center;
            padding: 40px 20px;
            background: rgba(0, 0, 0, 0.3);
            margin-top: 60px;
        }

        .hidden {
            display: none;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            .subtitle {
                font-size: 1.2rem;
            }
            .goals-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <header>
        <h1>🌟 100 Целей</h1>
        <p class="subtitle">Путь к лучшему будущему начинается здесь</p>
    </header>

    <div class="container">
        <div class="filter-buttons">
            <button class="filter-btn active" data-category="all">Все цели</button>
            <button class="filter-btn" data-category="ecology">Экология</button>
            <button class="filter-btn" data-category="business">Бизнес</button>
            <button class="filter-btn" data-category="education">Образование</button>
            <button class="filter-btn" data-category="health">Здоровье</button>
            <button class="filter-btn" data-category="creativity">Творчество</button>
            <button class="filter-btn" data-category="social">Социум</button>
            <button class="filter-btn" data-category="tech">Технологии</button>
            <button class="filter-btn" data-category="travel">Путешествия</button>
            <button class="filter-btn" data-category="personal">Личность</button>
        </div>

        <div class="goals-grid" id="goalsGrid"></div>

        <div class="progress-section">
            <h2>Прогресс достижения целей</h2>
            <div class="progress-bar">
                <div class="progress-fill"></div>
            </div>
            <p>12 из 100 целей определены</p>
        </div>
    </div>

    <footer>
        <p>© 2025 100 Целей. Создавая лучшее будущее вместе 🌍</p>
    </footer>

    <script>
        const goals = [
            { num: 1, text: "Запретить автомобили на любом вредном топливе (дизель, бензин) — только электричество", cat: "ecology" },
            { num: 2, text: "Помогать тем, кто нуждается и не может себе помочь", cat: "social" },
            { num: 3, text: "Заработать капитал 1 000 000 и доходные объекты недвижимости", cat: "business" },
            { num: 4, text: "Открыть собственную ферму с производством товаров с чистым составом", cat: "business" },
            { num: 5, text: "Найти свой стиль в музыке, делать качественно и стать популярным", cat: "creativity" },
            { num: 6, text: "Развивать свой личный бренд", cat: "business" },
            { num: 7, text: "Научиться прибыльному трейдингу", cat: "business" },
            { num: 8, text: "Поделиться опытом с другими", cat: "social" },
            { num: 9, text: "Запустить свой подкаст", cat: "creativity" },
            { num: 10, text: "Запретить курение, алкоголь и их продажу", cat: "health" },
            { num: 11, text: "Создать инъекцию против действия наркотиков", cat: "health" },
            { num: 12, text: "Разработать успешное приложение или сайт", cat: "tech" },
            { num: 13, text: "Создать пассивный доход от инвестиций в ценные бумаги", cat: "business" },
            { num: 14, text: "Открыть сеть магазинов здорового питания", cat: "business" },
            { num: 15, text: "Инвестировать в стартапы с социальным воздействием", cat: "business" },
            { num: 16, text: "Создать образовательную платформу по финансовой грамотности", cat: "education" },
            { num: 17, text: "Запустить линию экологически чистой одежды", cat: "ecology" },
            { num: 18, text: "Открыть коворкинг для креативных предпринимателей", cat: "business" },
            { num: 19, text: "Создать венчурный фонд для зелёных технологий", cat: "business" },
            { num: 20, text: "Разработать блокчейн-решение для прозрачности благотворительности", cat: "tech" },
            { num: 21, text: "Внедрить программу переработки отходов в городе", cat: "ecology" },
            { num: 22, text: "Посадить 10 000 деревьев", cat: "ecology" },
            { num: 23, text: "Создать систему сбора дождевой воды", cat: "ecology" },
            { num: 24, text: "Разработать биоразлагаемую упаковку", cat: "ecology" },
            { num: 25, text: "Организовать кампанию по очистке океанов", cat: "ecology" },
            { num: 26, text: "Построить дом с нулевым углеродным следом", cat: "ecology" },
            { num: 27, text: "Запустить инициативу по защите исчезающих видов", cat: "ecology" },
            { num: 28, text: "Создать городскую вертикальную ферму", cat: "ecology" },
            { num: 29, text: "Внедрить солнечные панели на всех объектах", cat: "ecology" },
            { num: 30, text: "Разработать систему компостирования для городов", cat: "ecology" },
            { num: 31, text: "Получить степень магистра в области устойчивого развития", cat: "education" },
            { num: 32, text: "Выучить три иностранных языка", cat: "education" },
            { num: 33, text: "Освоить программирование на профессиональном уровне", cat: "education" },
            { num: 34, text: "Пройти курс по нейробиологии", cat: "education" },
            { num: 35, text: "Научиться играть на трёх музыкальных инструментах", cat: "creativity" },
            { num: 36, text: "Изучить основы архитектуры и дизайна", cat: "education" },
            { num: 37, text: "Получить сертификат по управлению проектами", cat: "education" },
            { num: 38, text: "Освоить искусство публичных выступлений", cat: "education" },
            { num: 39, text: "Изучить психологию и коучинг", cat: "education" },
            { num: 40, text: "Пройти курс по ИИ и машинному обучению", cat: "tech" },
            { num: 41, text: "Пробежать марафон", cat: "health" },
            { num: 42, text: "Заниматься йогой ежедневно в течение года", cat: "health" },
            { num: 43, text: "Освоить боевые искусства", cat: "health" },
            { num: 44, text: "Достичь оптимального уровня физической формы", cat: "health" },
            { num: 45, text: "Пройти курс по нутрициологии", cat: "health" },
            { num: 46, text: "Научиться медитации и практиковать её регулярно", cat: "health" },
            { num: 47, text: "Освоить дыхательные техники", cat: "health" },
            { num: 48, text: "Пройти детокс-программу", cat: "health" },
            { num: 49, text: "Создать личный план здорового питания", cat: "health" },
            { num: 50, text: "Заниматься плаванием три раза в неделю", cat: "health" },
            { num: 51, text: "Выпустить свой музыкальный альбом", cat: "creativity" },
            { num: 52, text: "Написать книгу о своём опыте", cat: "creativity" },
            { num: 53, text: "Научиться рисовать и провести выставку", cat: "creativity" },
            { num: 54, text: "Создать документальный фильм", cat: "creativity" },
            { num: 55, text: "Освоить фотографию на профессиональном уровне", cat: "creativity" },
            { num: 56, text: "Написать сценарий для короткометражки", cat: "creativity" },
            { num: 57, text: "Создать серию видеоблогов о ЗОЖ", cat: "creativity" },
            { num: 58, text: "Разработать серию образовательных инфографик", cat: "creativity" },
            { num: 59, text: "Научиться танцевать и выступить на сцене", cat: "creativity" },
            { num: 60, text: "Создать арт-инсталляцию на тему экологии", cat: "creativity" },
            { num: 61, text: "Создать благотворительный фонд", cat: "social" },
            { num: 62, text: "Организовать программу наставничества", cat: "social" },
            { num: 63, text: "Построить школу в развивающейся стране", cat: "social" },
            { num: 64, text: "Запустить программу бесплатных обедов", cat: "social" },
            { num: 65, text: "Создать приют для бездомных животных", cat: "social" },
            { num: 66, text: "Организовать бесплатные курсы профподготовки", cat: "social" },
            { num: 67, text: "Запустить программу психологической поддержки", cat: "social" },
            { num: 68, text: "Создать центр реабилитации для зависимых", cat: "social" },
            { num: 69, text: "Организовать помощь одиноким пожилым людям", cat: "social" },
            { num: 70, text: "Запустить инициативу по борьбе с бедностью", cat: "social" },
            { num: 71, text: "Разработать приложение для мониторинга экологического следа", cat: "tech" },
            { num: 72, text: "Создать платформу для объединения волонтёров", cat: "tech" },
            { num: 73, text: "Запустить AI-помощника для ЗОЖ", cat: "tech" },
            { num: 74, text: "Разработать систему умного дома на возобновляемой энергии", cat: "tech" },
            { num: 75, text: "Создать блокчейн-платформу для органических продуктов", cat: "tech" },
            { num: 76, text: "Внедрить IoT-решения на своей ферме", cat: "tech" },
            { num: 77, text: "Разработать VR-приложение для образования", cat: "tech" },
            { num: 78, text: "Создать платформу для краудфандинга социальных проектов", cat: "tech" },
            { num: 79, text: "Запустить онлайн-маркетплейс для местных фермеров", cat: "tech" },
            { num: 80, text: "Разработать систему прогнозирования урожайности с помощью AI", cat: "tech" },
            { num: 81, text: "Посетить 50 стран", cat: "travel" },
            { num: 82, text: "Пожить в трёх разных странах минимум по полгода", cat: "travel" },
            { num: 83, text: "Изучить культуры коренных народов", cat: "travel" },
            { num: 84, text: "Совершить экологичное кругосветное путешествие", cat: "travel" },
            { num: 85, text: "Посетить все континенты", cat: "travel" },
            { num: 86, text: "Принять участие в культурном обмене", cat: "travel" },
            { num: 87, text: "Документировать исчезающие традиции", cat: "travel" },
            { num: 88, text: "Изучить историю семьи и создать генеалогическое древо", cat: "personal" },
            { num: 89, text: "Посетить все объекты ЮНЕСКО в своей стране", cat: "travel" },
            { num: 90, text: "Организовать культурный фестиваль", cat: "creativity" },
            { num: 91, text: "Построить крепкие отношения с семьёй", cat: "personal" },
            { num: 92, text: "Создать круг единомышленников", cat: "personal" },
            { num: 93, text: "Стать ментором для 10 человек", cat: "personal" },
            { num: 94, text: "Развить эмоциональный интеллект", cat: "personal" },
            { num: 95, text: "Научиться прощать и отпускать прошлое", cat: "personal" },
            { num: 96, text: "Практиковать благодарность ежедневно", cat: "personal" },
            { num: 97, text: "Развить навыки активного слушания", cat: "personal" },
            { num: 98, text: "Найти баланс между работой и личной жизнью", cat: "personal" },
            { num: 99, text: "Создать личную миссию и следовать ей", cat: "personal" },
            { num: 100, text: "Оставить позитивное наследие для будущих поколений", cat: "personal" }
        ];

        const categoryNames = {
            ecology: "Экология",
            business: "Бизнес",
            education: "Образование",
            health: "Здоровье",
            creativity: "Творчество",
            social: "Социум",
            tech: "Технологии",
            travel: "Путешествия",
            personal: "Личность"
        };

        function createParticles() {
            const container = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                const size = Math.random() * 5 + 2;
                particle.style.width = size + 'px';
                particle.style.height = size + 'px';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                container.appendChild(particle);
            }
        }

        function renderGoals(category = 'all') {
            const grid = document.getElementById('goalsGrid');
            grid.innerHTML = '';
            
            const filteredGoals = category === 'all' 
                ? goals 
                : goals.filter(g => g.cat === category);
            
            filteredGoals.forEach((goal, index) => {
                const card = document.createElement('div');
                card.className = 'goal-card';
                card.style.animationDelay = (index * 0.05) + 's';
                card.innerHTML = `
                    <div class="goal-number">${goal.num}</div>
                    <div class="goal-title">${goal.text}</div>
                    <span class="goal-category">${categoryNames[goal.cat]}</span>
                `;
                grid.appendChild(card);
            });
        }

        document.querySelectorAll('.filter-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                renderGoals(this.dataset.category);
            });
        });

        createParticles();
        renderGoals();
    </script>
</body>
</html>
