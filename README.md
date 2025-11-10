<!DOCTYPE html>
<html lang="fa-IR" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ربات معاملاتی کوانتوم - تحلیل هوشمند، سود مستمر</title>
    <meta name="description" content="ربات معاملاتی کوانتوم با استفاده از هوش مصنوعی پیشرفته، بازار را تحلیل کرده و بهترین سیگنال‌های معاملاتی را ارائه می‌دهد">
    <meta name="keywords" content="ربات معاملاتی, کوانتوم, تحلیل بازار, سیگنال خرید, سیگنال فروش, ارز دیجیتال">
    <meta name="author" content="محمد امین بیکی">
    <style>
        /* Reset and Base Styles */
        :root {
            --primary: #2c5aa0;
            --primary-dark: #1e3d72;
            --secondary: #4CAF50;
            --accent: #FF9800;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --text: #333;
            --text-light: #fff;
            --gray: #6c757d;
            --border: #dee2e6;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --info: #17a2b8;
            --font-family: 'Vazir', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            --border-radius: 8px;
            --box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: var(--font-family);
            background-color: var(--light);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }
        
        ul, ol {
            list-style: none;
        }
        
        img {
            max-width: 100%;
            height: auto;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 10px 20px;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            font-size: 1rem;
            gap: 8px;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: var(--text-light);
        }
        
        .btn-primary:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--box-shadow);
        }
        
        .btn-secondary {
            background-color: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
        }
        
        .btn-secondary:hover {
            background-color: var(--primary);
            color: var(--text-light);
        }
        
        .btn-accent {
            background-color: var(--accent);
            color: var(--text-light);
        }
        
        .btn-accent:hover {
            background-color: #e68900;
            transform: translateY(-2px);
            box-shadow: var(--box-shadow);
        }
        
        .btn-success {
            background-color: var(--success);
            color: var(--text-light);
        }
        
        .btn-success:hover {
            background-color: #218838;
            transform: translateY(-2px);
        }
        
        .section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--dark);
            position: relative;
            display: inline-block;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            right: 50%;
            transform: translateX(50%);
            width: 80px;
            height: 3px;
            background-color: var(--accent);
        }
        
        .section-title p {
            color: var(--gray);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }
        
        /* Header Styles */
        header {
            background-color: var(--dark);
            color: var(--text-light);
            position: fixed;
            top: 0;
            right: 0;
            left: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
            font-weight: 700;
        }
        
        .logo-icon {
            color: var(--accent);
        }
        
        .nav-menu {
            display: flex;
            gap: 30px;
        }
        
        .nav-link {
            font-weight: 500;
            padding: 5px 0;
            position: relative;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            transition: var(--transition);
        }
        
        .nav-link:hover::after,
        .nav-link.active::after {
            width: 100%;
        }
        
        .nav-link:hover,
        .nav-link.active {
            color: var(--accent);
        }
        
        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-light);
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary), var(--dark));
            color: var(--text-light);
            padding: 180px 0 100px;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none"><path d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z" fill="%23ffffff" fill-opacity="0.1"></path></svg>');
            background-size: cover;
            background-position: center;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero-title {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .hero-subtitle {
            font-size: 1.3rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }
        
        .hero-description {
            font-size: 1.1rem;
            margin-bottom: 40px;
            opacity: 0.8;
            max-width: 600px;
            margin-right: auto;
            margin-left: auto;
        }
        
        .hero-actions {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        /* Features Section */
        .features {
            background-color: #fff;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background-color: #fff;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            text-align: center;
            border-top: 4px solid var(--primary);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .feature-description {
            color: var(--gray);
        }
        
        /* Pricing Section */
        .pricing {
            background-color: #f8f9fa;
        }
        
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .pricing-card {
            background-color: #fff;
            border-radius: var(--border-radius);
            padding: 0;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            overflow: hidden;
            position: relative;
        }
        
        .pricing-card.popular {
            transform: scale(1.05);
            border: 2px solid var(--accent);
        }
        
        .pricing-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .pricing-card.popular:hover {
            transform: scale(1.05) translateY(-5px);
        }
        
        .popular-badge {
            position: absolute;
            top: 20px;
            left: -30px;
            background-color: var(--accent);
            color: var(--text-light);
            padding: 5px 30px;
            transform: rotate(-45deg);
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .pricing-header {
            background-color: var(--primary);
            color: var(--text-light);
            padding: 30px;
            text-align: center;
        }
        
        .pricing-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        .pricing-price {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .pricing-period {
            opacity: 0.8;
        }
        
        .pricing-body {
            padding: 30px;
        }
        
        .pricing-features {
            margin-bottom: 30px;
        }
        
        .pricing-feature {
            padding: 10px 0;
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .pricing-feature:last-child {
            border-bottom: none;
        }
        
        .pricing-feature i {
            color: var(--success);
        }
        
        .pricing-actions {
            text-align: center;
        }
        
        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: #fff;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .service-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }
        
        .service-description {
            color: var(--gray);
            margin-bottom: 20px;
            flex-grow: 1;
        }
        
        .service-link {
            color: var(--primary);
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .service-link:hover {
            color: var(--primary-dark);
        }
        
        /* Contact Section */
        .contact {
            background-color: #f8f9fa;
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }
        
        .contact-card {
            background-color: #fff;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
        }
        
        .contact-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .contact-title i {
            color: var(--primary);
        }
        
        .contact-details {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .contact-detail {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .contact-detail i {
            color: var(--accent);
            width: 20px;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: var(--primary);
            color: var(--text-light);
            border-radius: 50%;
            transition: var(--transition);
        }
        
        .social-link:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
        }
        
        .contact-form {
            background-color: #fff;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border);
            border-radius: var(--border-radius);
            font-family: inherit;
            font-size: 1rem;
            transition: var(--transition);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(44, 90, 160, 0.1);
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: var(--text-light);
            padding: 60px 0 20px;
        }
        
        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-col h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--accent);
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-col h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 40px;
            height: 2px;
            background-color: var(--accent);
        }
        
        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .footer-link {
            transition: var(--transition);
        }
        
        .footer-link:hover {
            color: var(--accent);
            padding-right: 5px;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero-title {
                font-size: 2.8rem;
            }
            
            .pricing-card.popular {
                transform: scale(1);
            }
            
            .pricing-card.popular:hover {
                transform: translateY(-5px);
            }
        }
        
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                top: 70px;
                right: -100%;
                background-color: var(--dark);
                width: 80%;
                height: calc(100vh - 70px);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 50px;
                transition: var(--transition);
                box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            }
            
            .nav-menu.active {
                right: 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero-title {
                font-size: 2.2rem;
            }
            
            .hero-subtitle {
                font-size: 1.1rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .hero-actions {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
                max-width: 300px;
            }
        }
        
        @media (max-width: 576px) {
            .hero {
                padding: 150px 0 80px;
            }
            
            .hero-title {
                font-size: 1.8rem;
            }
            
            .section {
                padding: 60px 0;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .feature-card,
            .pricing-card,
            .service-card,
            .contact-card {
                padding: 20px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://cdn.jsdelivr.net/gh/rastikerdar/vazir-font@v30.1.0/dist/font-face.css" rel="stylesheet" type="text/css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-container">
                <a href="#" class="logo">
                    <i class="fas fa-robot logo-icon"></i>
                    <span>ربات کوانتوم</span>
                </a>
                
                <nav>
                    <ul class="nav-menu">
                        <li><a href="#home" class="nav-link active">صفحه اصلی</a></li>
                        <li><a href="#features" class="nav-link">ویژگی‌ها</a></li>
                        <li><a href="#pricing" class="nav-link">اشتراک‌ها</a></li>
                        <li><a href="#services" class="nav-link">خدمات ویژه</a></li>
                        <li><a href="#about" class="nav-link">درباره ما</a></li>
                        <li><a href="#contact" class="nav-link">تماس با ما</a></li>
                    </ul>
                </nav>
                
                <div class="header-actions">
                    <a href="#" class="btn btn-secondary">ورود</a>
                    <a href="#" class="btn btn-primary">ثبت‌نام</a>
                    <button class="mobile-menu-btn">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">ربات معاملاتی کوانتوم</h1>
                <p class="hero-subtitle">تحلیل هوشمند، سود مستمر</p>
                <p class="hero-description">با استفاده از هوش مصنوعی پیشرفته، بازار را تحلیل کرده و بهترین سیگنال‌های معاملاتی را دریافت کنید. ربات کوانتوم با تحلیل چندلایه و الگوریتم‌های پیچیده، راهنمای مطمئنی برای سرمایه‌گذاری شماست.</p>
                <div class="hero-actions">
                    <a href="#pricing" class="btn btn-accent">
                        <i class="fas fa-shopping-cart"></i>
                        خرید اشتراک
                    </a>
                    <a href="#" class="btn btn-secondary">
                        <i class="fas fa-robot"></i>
                        اتصال به ربات
                    </a>
                    <a href="#contact" class="btn btn-primary">
                        <i class="fas fa-phone"></i>
                        تماس با ما
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section features" id="features">
        <div class="container">
            <div class="section-title">
                <h2>ویژگی‌های ربات کوانتوم</h2>
                <p>با قابلیت‌های منحصر به فرد ربات معاملاتی ما آشنا شوید</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3 class="feature-title">تحلیل چندلایه</h3>
                    <p class="feature-description">تجزیه و تحلیل بازار با استفاده از الگوریتم‌های پیچیده و چندین لایه اطلاعاتی برای دقت بیشتر در پیش‌بینی روند بازار</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3 class="feature-title">سیگنال‌های دقیق</h3>
                    <p class="feature-description">دریافت سیگنال‌های خرید و فروش با دقت بالا و زمان‌بندی مناسب برای بهینه‌سازی سود و کاهش ریسک معاملات</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-link"></i>
                    </div>
                    <h3 class="feature-title">اتصال مستقیم</h3>
                    <p class="feature-description">اتصال مستقیم به صرافی مورد نظر و معامله خودکار با ارز دلخواه شما بدون نیاز به واسطه و با سرعت بالا</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-sync-alt"></i>
                    </div>
                    <h3 class="feature-title">بروزرسانی لحظه‌ای</h3>
                    <p class="feature-description">بررسی مداوم بازار و بروزرسانی تحلیل‌ها و سیگنال‌ها در لحظه برای واکنش سریع به تغییرات بازار</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3 class="feature-title">دسترسی آسان</h3>
                    <p class="feature-description">دسترسی از طریق وب‌سایت، اپلیکیشن موبایل و پیامرسان‌ها برای استفاده در هر زمان و مکان</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3 class="feature-title">امنیت بالا</h3>
                    <p class="feature-description">رمزنگاری پیشرفته و حفاظت از اطلاعات و سرمایه شما با استفاده از آخرین استانداردهای امنیتی</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section class="section pricing" id="pricing">
        <div class="container">
            <div class="section-title">
                <h2>پلن‌های اشتراک</h2>
                <p>پلن مناسب نیازهای معاملاتی خود را انتخاب کنید</p>
            </div>
            
            <div class="pricing-grid">
                <div class="pricing-card">
                    <div class="pricing-header">
                        <h3 class="pricing-title">اشتراک یک ماهه</h3>
                        <div class="pricing-price">۲۰۰,۰۰۰</div>
                        <div class="pricing-period">تومان / ماه</div>
                    </div>
                    <div class="pricing-body">
                        <ul class="pricing-features">
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                دسترسی نامحدود به ربات کوانتوم
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تحلیل لحظه‌ای بازار
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                سیگنال‌های خرید و فروش
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                پشتیبانی آنلاین
                            </li>
                        </ul>
                        <div class="pricing-actions">
                            <a href="#" class="btn btn-primary">خرید اشتراک</a>
                        </div>
                    </div>
                </div>
                
                <div class="pricing-card popular">
                    <div class="popular-badge">پیشنهاد ویژه</div>
                    <div class="pricing-header">
                        <h3 class="pricing-title">اشتراک سه ماهه</h3>
                        <div class="pricing-price">۷۰۰,۰۰۰</div>
                        <div class="pricing-period">تومان / سه ماه</div>
                    </div>
                    <div class="pricing-body">
                        <ul class="pricing-features">
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تمام امکانات پلن یک ماهه
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تحلیل اخبار اقتصادی و سیاسی
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                پیشنهاد ارز معتبر برای سرمایه‌گذاری
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تخفیف ۱۵٪ نسبت به خرید ماهانه
                            </li>
                        </ul>
                        <div class="pricing-actions">
                            <a href="#" class="btn btn-accent">خرید اشتراک</a>
                        </div>
                    </div>
                </div>
                
                <div class="pricing-card">
                    <div class="pricing-header">
                        <h3 class="pricing-title">اشتراک یک ساله</h3>
                        <div class="pricing-price">۱۰,۰۰۰,۰۰۰</div>
                        <div class="pricing-period">تومان / سال</div>
                    </div>
                    <div class="pricing-body">
                        <ul class="pricing-features">
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تمام امکانات پلن سه ماهه
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                دسترسی VIP به تمام خدمات
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                پیشنهاد میم‌کوین‌های ترند
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                پشتیبانی اختصاصی
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                تحلیل روان‌شناسی بازار
                            </li>
                            <li class="pricing-feature">
                                <i class="fas fa-check"></i>
                                دستیار هوش مصنوعی برای مشاوره
                            </li>
                        </ul>
                        <div class="pricing-actions">
                            <a href="#" class="btn btn-primary">خرید اشتراک</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="section services" id="services">
        <div class="container">
            <div class="section-title">
                <h2>خدمات ویژه</h2>
                <p>خدمات اختصاصی برای معامله‌گران حرفه‌ای</p>
            </div>
            
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-newspaper"></i>
                    </div>
                    <h3 class="service-title">تحلیل اخبار اقتصادی و سیاسی</h3>
                    <p class="service-description">تحلیل تأثیر اخبار مهم اقتصادی و سیاسی بر بازار ارزهای دیجیتال و ارائه راهکارهای معاملاتی مبتنی بر این تحلیلها</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-coins"></i>
                    </div>
                    <h3 class="service-title">پیشنهاد ارزهای معتبر</h3>
                    <p class="service-description">شناسایی و پیشنهاد ارزهای معتبر برای سرمایه‌گذاری بر اساس تحلیل فاندامنتال و تکنیکال با پتانسیل رشد بالا</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-dog"></i>
                    </div>
                    <h3 class="service-title">معرفی میم‌کوین‌های ترند</h3>
                    <p class="service-description">شناسایی میم‌کوین‌های پرطرفدار و تحلیل پتانسیل رشد آنها با در نظر گرفتن ریسک‌های مرتبط با این نوع ارزها</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3 class="service-title">تحلیل روان‌شناسی بازار</h3>
                    <p class="service-description">تحلیل رفتار معامله‌گران و روان‌شناسی بازار برای شناسایی نقاط转折 و فرصت‌های معاملاتی پنهان</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3 class="service-title">دستیار هوش مصنوعی</h3>
                    <p class="service-description">دستیار هوش مصنوعی برای مشاوره معاملاتی شخصی‌سازی شده بر اساس سبک معاملاتی و ریسک‌پذیری شما</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
                
                <div class="service-card">
                    <div class="service-icon">
                        <i class="fas fa-user-graduate"></i>
                    </div>
                    <h3 class="service-title">آموزش و مشاوره</h3>
                    <p class="service-description">دوره‌های آموزشی و مشاوره‌های تخصصی برای بهبود مهارت‌های معاملاتی و درک عمیق‌تر بازارهای مالی</p>
                    <a href="#" class="service-link">
                        اطلاعات بیشتر
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section about" id="about">
        <div class="container">
            <div class="section-title">
                <h2>درباره ما</h2>
                <p>با تیم پشت ربات معاملاتی کوانتوم آشنا شوید</p>
            </div>
            
            <div class="about-content">
                <div class="about-text">
                    <h3>داستان ساخت ربات کوانتوم</h3>
                    <p>ربات معاملاتی کوانتوم حاصل سال‌ها تجربه در بازارهای مالی و تخصص در زمینه هوش مصنوعی است. این پروژه با هدف ارائه ابزارهای هوشمند برای معامله‌گران ایرانی و تسهیل فرآیند تحلیل و معامله در بازارهای پیچیده مالی آغاز شد.</p>
                    
                    <h3>معرفی محمد امین بیکی</h3>
                    <p>محمد امین بیکی، سازنده ربات معاملاتی کوانتوم و مدیر این سایت خدماتی، با بیش از ۸ سال تجربه در بازارهای مالی و تخصص در توسعه الگوریتم‌های معاملاتی، تیم کوانتوم را راه‌اندازی کرده است. مأموریت او ارائه ابزارهای هوشمند و در دسترس برای معامله‌گران ایرانی است.</p>
                    
                    <h3>تیم توسعه</h3>
                    <p>تیم کوانتوم متشکل از متخصصان حوزه‌های مختلف شامل تحلیل‌گران بازار، توسعه‌دهندگان الگوریتم‌های هوش مصنوعی و متخصصان امنیت سایبری است که با همکاری یکدیگر، پیوسته در حال بهبود و توسعه ربات معاملاتی کوانتوم هستند.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>تماس با ما</h2>
                <p>برای دریافت اطلاعات بیشتر با ما در ارتباط باشید</p>
            </div>
            
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-card">
                        <h3 class="contact-title">
                            <i class="fas fa-info-circle"></i>
                            اطلاعات تماس
                        </h3>
                        <div class="contact-details">
                            <div class="contact-detail">
                                <i class="fas fa-user"></i>
                                <span>محمد امین بیکی</span>
                            </div>
                            <div class="contact-detail">
                                <i class="fas fa-phone"></i>
                                <span>۰۹۰۳۳۶۹۴۸۰۱</span>
                            </div>
                            <div class="contact-detail">
                                <i class="fas fa-briefcase"></i>
                                <span>سازنده ربات معاملاتی کوانتوم</span>
                            </div>
                            <div class="contact-detail">
                                <i class="fas fa-building"></i>
                                <span>مدیر سایت خدماتی</span>
                            </div>
                        </div>
                        
                        <div class="social-links">
                            <a href="#" class="social-link">
                                <i class="fab fa-telegram"></i>
                            </a>
                            <a href="#" class="social-link">
                                <i class="fab fa-instagram"></i>
                            </a>
                            <a href="#" class="social-link">
                                <i class="fab fa-twitter"></i>
                            </a>
                            <a href="#" class="social-link">
                                <i class="fas fa-envelope"></i>
                            </a>
                        </div>
                    </div>
                    
                    <div class="contact-card">
                        <h3 class="contact-title">
                            <i class="fas fa-map-marker-alt"></i>
                            اطلاعات بیشتر
                        </h3>
                        <div class="contact-details">
                            <div class="contact-detail">
                                <i class="fas fa-clock"></i>
                                <span>پشتیبانی: ۲۴ ساعته</span>
                            </div>
                            <div class="contact-detail">
                                <i class="fas fa-globe"></i>
                                <span>خدمات: بین‌المللی</span>
                            </div>
                            <div class="contact-detail">
                                <i class="fas fa-lock"></i>
                                <span>امنیت: تضمین شده</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="contact-form">
                    <h3 class="contact-title">
                        <i class="fas fa-paper-plane"></i>
                        ارسال پیام
                    </h3>
                    <form>
                        <div class="form-group">
                            <label for="name" class="form-label">نام و نام خانوادگی</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="email" class="form-label">ایمیل</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="phone" class="form-label">شماره تماس</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="subject" class="form-label">موضوع</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="message" class="form-label">پیام</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        
                        <button type="submit" class="btn btn-primary">
                            <i class="fas fa-paper-plane"></i>
                            ارسال پیام
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-col">
                    <h3>ربات کوانتوم</h3>
                    <p>ارائه دهنده پیشرفته‌ترین ابزارهای معاملاتی مبتنی بر هوش مصنوعی برای تریدرهای ایرانی. ما با استفاده از تکنولوژی‌های روز دنیا، تحلیل‌های دقیق و سیگنال‌های معاملاتی به موقع را در اختیار شما قرار می‌دهیم.</p>
                </div>
                
                <div class="footer-col">
                    <h3>لینک‌های سریع</h3>
                    <ul class="footer-links">
                        <li><a href="#home" class="footer-link">صفحه اصلی</a></li>
                        <li><a href="#features" class="footer-link">ویژگی‌ها</a></li>
                        <li><a href="#pricing" class="footer-link">اشتراک‌ها</a></li>
                        <li><a href="#services" class="footer-link">خدمات ویژه</a></li>
                        <li><a href="#about" class="footer-link">درباره ما</a></li>
                        <li><a href="#contact" class="footer-link">تماس با ما</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>خدمات ما</h3>
                    <ul class="footer-links">
                        <li><a href="#" class="footer-link">ربات معاملاتی</a></li>
                        <li><a href="#" class="footer-link">تحلیل اخبار</a></li>
                        <li><a href="#" class="footer-link">پیشنهاد ارز</a></li>
                        <li><a href="#" class="footer-link">مشاوره معاملاتی</a></li>
                        <li><a href="#" class="footer-link">آموزش ترید</a></li>
                        <li><a href="#" class="footer-link">تحلیل روان‌شناسی بازار</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3>اطلاعات قانونی</h3>
                    <ul class="footer-links">
                        <li><a href="#" class="footer-link">قوانین و مقررات</a></li>
                        <li><a href="#" class="footer-link">حریم خصوصی</a></li>
                        <li><a href="#" class="footer-link">هشدارهای ریسک</a></li>
                        <li><a href="#" class="footer-link">سوالات متداول</a></li>
                        <li><a href="#" class="footer-link">شرایط استفاده</a></li>
                        <li><a href="#" class="footer-link">خط‌مشی بازگشت وجه</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>© ۲۰۲۳ ربات معاملاتی کوانتوم - تمام حقوق محفوظ است. طراحی و توسعه توسط محمد امین بیکی</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            document.querySelector('.nav-menu').classList.toggle('active');
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function() {
                document.querySelector('.nav-menu').classList.remove('active');
            });
        });
        
        // Active navigation link on scroll
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('.nav-link');
            
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                
                if (scrollY >= (sectionTop - 100)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Form submission
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('پیام شما با موفقیت ارسال شد. به زودی با شما تماس خواهیم گرفت.');
            this.reset();
        });
    </script>
</body>
</html>
