<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ФотоЛаб - Профессиональное фото на документы за 5 минут</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #0066FF;
            --primary-dark: #0052CC;
            --secondary: #00D4FF;
            --accent: #FF6B35;
            --light: #F8FAFC;
            --dark: #1E293B;
            --gray: #64748B;
            --success: #10B981;
            --white: #FFFFFF;
            --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
            --shadow: 0 10px 25px rgba(0, 102, 255, 0.1);
            --shadow-hover: 0 20px 40px rgba(0, 102, 255, 0.2);
        }

        body {
            background: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .header-scrolled {
            box-shadow: var(--shadow);
            background: rgba(255, 255, 255, 0.98);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo-icon {
            background: var(--gradient);
            width: 40px;
            height: 40px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
            align-items: center;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 8px;
            position: relative;
        }

        .nav-menu a:hover {
            color: var(--primary);
            background: rgba(0, 102, 255, 0.05);
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 2px;
            background: var(--gradient);
            transition: all 0.3s ease;
            transform: translateX(-50%);
        }

        .nav-menu a:hover::after {
            width: 80%;
        }

        .nav-cta {
            background: var(--accent);
            color: var(--white) !important;
            padding: 0.75rem 1.5rem !important;
            border-radius: 50px !important;
            font-weight: 600 !important;
            transition: all 0.3s ease !important;
        }

        .nav-cta:hover {
            background: #E55A2B !important;
            transform: translateY(-2px) !important;
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.3) !important;
        }

        .nav-cta::after {
            display: none !important;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, rgba(0, 102, 255, 0.9), rgba(0, 212, 255, 0.8)), 
                        url('https://images.unsplash.com/photo-1554080353-321e452ccf19?ixlib=rb-4.0.3&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            padding: 12rem 2rem 6rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23ffffff' fill-opacity='0.1' fill-rule='evenodd'/%3E%3C/svg%3E");
            animation: float 20s linear infinite;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-100px) rotate(360deg); }
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            opacity: 0.95;
        }

        .urgent-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            color: var(--white);
            padding: 0.75rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            margin-bottom: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { 
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(255, 107, 53, 0.7);
            }
            50% { 
                transform: scale(1.05);
                box-shadow: 0 0 0 10px rgba(255, 107, 53, 0);
            }
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            background: var(--accent);
            color: var(--white);
            padding: 1.25rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.3);
        }

        .cta-button:hover {
            background: #E55A2B;
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 107, 53, 0.4);
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
            padding: 0 2rem;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 0.5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 1rem;
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--dark);
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 4rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Services */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: var(--white);
            padding: 3rem 2rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }

        .service-icon {
            width: 80px;
            height: 80px;
            background: var(--gradient);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            color: var(--white);
            font-size: 2rem;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .service-card p {
            color: var(--gray);
            margin-bottom: 1.5rem;
        }

        .service-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .service-features {
            list-style: none;
            text-align: left;
        }

        .service-features li {
            padding: 0.5rem 0;
            color: var(--gray);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .service-features li::before {
            content: '✓';
            color: var(--success);
            font-weight: bold;
        }

        /* Documents */
        .documents-section {
            background: var(--white);
        }

        .documents-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .document-item {
            background: var(--light);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .document-item:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .document-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        /* Process */
        .process-steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            position: relative;
        }

        .process-steps::before {
            content: '';
            position: absolute;
            top: 60px;
            left: 0;
            right: 0;
            height: 2px;
            background: var(--gradient);
            z-index: 1;
        }

        .step {
            background: var(--white);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            position: relative;
            z-index: 2;
            box-shadow: var(--shadow);
        }

        .step-number {
            width: 60px;
            height: 60px;
            background: var(--gradient);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-weight: 700;
            font-size: 1.2rem;
        }

        /* Contacts */
        .contacts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
        }

        .contact-card {
            background: var(--white);
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: var(--shadow);
        }

        .contact-card h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .contact-info {
            margin-bottom: 2rem;
        }

        .contact-info p {
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--gray);
        }

        .contact-info i {
            color: var(--primary);
            width: 20px;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: var(--gradient);
            color: var(--white);
            border-radius: 12px;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.2rem;
        }

        .social-links a:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 10px 25px rgba(0, 102, 255, 0.3);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: var(--white);
            padding: 4rem 0 2rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .footer-section h3 {
            margin-bottom: 1.5rem;
            color: var(--secondary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.75rem;
        }

        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--secondary);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--gray);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            .process-steps::before {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="nav-container">
            <a href="#" class="logo">
                <div class="logo-icon">
                    <i class="fas fa-camera"></i>
                </div>
                ФотоЛаб
            </a>
            
            <nav>
                <ul class="nav-menu">
                    <li><a href="#services">Услуги</a></li>
                    <li><a href="#documents">Документы</a></li>
                    <li><a href="#process">Как работаем</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                    <li><a href="order.html" class="nav-cta">Срочный заказ</a></li>
                </ul>
            </nav>
            
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="urgent-badge">
                <i class="fas fa-bolt"></i>
                ФОТО ГОТОВО ЗА 5 МИНУТ!
            </div>
            <h1>Профессиональное фото на документы</h1>
            <p>Более 15 лет создаем качественные фотографии для любых целей. Срочная печать, ретушь, современное оборудование</p>
            <a href="order.html" class="cta-button">
                <i class="fas fa-camera"></i>
                Заказать фото онлайн
            </a>
        </div>
        
        <div class="stats">
            <div class="stat-item">
                <div class="stat-number">15+</div>
                <div>лет опыта</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">5 мин</div>
                <div>среднее время</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">5000+</div>
                <div>довольных клиентов</div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services">
        <div class="container">
            <h2 class="section-title">Наши услуги</h2>
            <p class="section-subtitle">Полный спектр фотографических услуг для любых потребностей</p>
            
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-id-card"></i>
                    </div>
                    <h3>Фото на документы</h3>
                    <p>Профессиональные фотографии для всех видов документов</p>
                    <div class="service-price">от 250₽</div>
                    <ul class="service-features">
                        <li>Паспорт РФ и загранпаспорт</li>
                        <li>Виза и международные документы</li>
                        <li>Студенческий и пропуска</li>
                        <li>Военный билет и мед. книжка</li>
                    </ul>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-print"></i>
                    </div>
                    <h3>Печать фото</h3>
                    <p>Качественная печать с любых носителей</p>
                    <div class="service-price">от 50₽</div>
                    <ul class="service-features">
                        <li>Цветная и черно-белая печать</li>
                        <li>Фото разных размеров</li>
                        <li>Превосходное качество</li>
                        <li>Быстрая обработка</li>
                    </ul>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-gift"></i>
                    </div>
                    <h3>Фотоподарки</h3>
                    <p>Уникальные подарки с вашими фотографиями</p>
                    <div class="service-price">от 500₽</div>
                    <ul class="service-features">
                        <li>Кружки и термосы</li>
                        <li>Фотокалендари</li>
                        <li>Холсты и постеры</li>
                        <li>Слайд-шоу и коллажи</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Documents Section -->
    <section id="documents" class="documents-section">
        <div class="container">
            <h2 class="section-title">Все виды документов</h2>
            <p class="section-subtitle">Фотографии для любых официальных целей</p>
            
            <div class="documents-grid">
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-passport"></i>
                    </div>
                    <h4>Паспорт РФ</h4>
                    <p>35×45 мм, матовая бумага</p>
                </div>
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-plane"></i>
                    </div>
                    <h4>Загранпаспорт</h4>
                    <p>Международные стандарты</p>
                </div>
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h4>Студенческий</h4>
                    <p>Для учебных заведений</p>
                </div>
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-briefcase"></i>
                    </div>
                    <h4>Трудоустройство</h4>
                    <p>Резюме и личные дела</p>
                </div>
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-user-tie"></i>
                    </div>
                    <h4>Виза</h4>
                    <p>Требования посольств</p>
                </div>
                <div class="document-item">
                    <div class="document-icon">
                        <i class="fas fa-heartbeat"></i>
                    </div>
                    <h4>Мед. книжка</h4>
                    <p>Для медицинских работников</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Process Section -->
    <section id="process">
        <div class="container">
            <h2 class="section-title">Как мы работаем</h2>
            <p class="section-subtitle">Простой и понятный процесс от заказа до получения</p>
            
            <div class="process-steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Выбор услуги</h3>
                    <p>Определите тип фото и дополнительные опции</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Съемка</h3>
                    <p>Профессиональная фотосессия в студии</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Обработка</h3>
                    <p>Ретушь и подготовка к печати</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Готово!</h3>
                    <p>Получайте качественные фото через 5 минут</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contacts Section -->
    <section id="contacts" class="documents-section">
        <div class="container">
            <h2 class="section-title">Наши контакты</h2>
            <p class="section-subtitle">Приходите в любой из наших удобно расположенных филиалов</p>
            
            <div class="contacts-grid">
                <div class="contact-card">
                    <h3><i class="fas fa-map-marker-alt"></i> Орехова 54</h3>
                    <div class="contact-info">
                        <p><i class="fas fa-phone"></i> 8-914175-46-20</p>
                        <p><i class="fas fa-envelope"></i> fotolabdzemgi@yandex.ru</p>
                        <p><i class="fas fa-clock"></i> Пн-Пт: 10:00-18:00</p>
                        <p><i class="fas fa-clock"></i> Сб-Вс: выходной</p>
                    </div>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-whatsapp"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-vk"></i></a>
                    </div>
                </div>
                
                <div class="contact-card">
                    <h3><i class="fas fa-map-marker-alt"></i> Парижской коммуны 30</h3>
                    <div class="contact-info">
                        <p><i class="fas fa-phone"></i> 8-914-403-28-85</p>
                        <p><i class="fas fa-envelope"></i> fotogorodkms@yandex.ru</p>
                        <p><i class="fas fa-clock"></i> Пн-Чт: 10:00-18:30</p>
                        <p><i class="fas fa-clock"></i> Пт: 10:00-18:00</p>
                        <p><i class="fas fa-clock"></i> Сб-Вс: выходной</p>
                    </div>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-whatsapp"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-vk"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>ФотоЛаб</h3>
                    <p>Профессиональные фотоуслуги с 2008 года. Качество, скорость и надежность.</p>
                </div>
                <div class="footer-section">
                    <h3>Услуги</h3>
                    <ul class="footer-links">
                        <li><a href="#">Фото на документы</a></li>
                        <li><a href="#">Печать фото</a></li>
                        <li><a href="#">Фотоподарки</a></li>
                        <li><a href="#">Багетные услуги</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Контакты</h3>
                    <ul class="footer-links">
                        <li><a href="#">Орехова 54</a></li>
                        <li><a href="#">Парижской коммуны 30</a></li>
                        <li><a href="#">+7 (914) 175-46-20</a></li>
                        <li><a href="mailto:fotolabdzemgi@yandex.ru">fotolabdzemgi@yandex.ru</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2024 ФотоЛаб. Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 100) {
                header.classList.add('header-scrolled');
            } else {
                header.classList.remove('header-scrolled');
            }
        });

        // Mobile menu
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            document.querySelector('.nav-menu').classList.toggle('show');
        });

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe elements for animation
        document.querySelectorAll('.service-card, .document-item, .step').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
