
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mon Portfolio - Vert Émeraude</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            /* Dégradé remplacé par des verts émeraude */
            background: linear-gradient(135deg, #2E8B57 0%, #1D5E3F 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animations globales améliorées */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(60px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes slideInBlur {
            from {
                opacity: 0;
                transform: translateX(-50px);
                filter: blur(10px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
                filter: blur(0);
            }
        }

        @keyframes float {
            0% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-15px);
            }
            100% {
                transform: translateY(0px);
            }
        }

        @keyframes floatRotate {
            0% {
                transform: translateY(0px) rotate(0deg);
            }
            50% {
                transform: translateY(-10px) rotate(2deg);
            }
            100% {
                transform: translateY(0px) rotate(0deg);
            }
        }

        @keyframes pulseGlow {
            0% {
                box-shadow: 0 0 0 0 rgba(46, 139, 86, 0.4); /* émeraude avec transparence */
                transform: scale(1);
            }
            50% {
                box-shadow: 0 0 20px 10px rgba(46, 139, 86, 0.2);
                transform: scale(1.02);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(46, 139, 86, 0.4);
                transform: scale(1);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -200% 0;
            }
            100% {
                background-position: 200% 0;
            }
        }

        @keyframes rotateGradient {
            0% {
                transform: rotate(0deg) scale(1);
            }
            50% {
                transform: rotate(180deg) scale(1.1);
            }
            100% {
                transform: rotate(360deg) scale(1);
            }
        }

        @keyframes borderPulse {
            0%, 100% {
                border-color: rgba(46, 139, 86, 0.3);
            }
            50% {
                border-color: rgba(46, 139, 86, 0.8);
            }
        }

        /* Header avec animation améliorée */
        header {
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
            animation: slideDown 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%) rotateX(-90deg);
                opacity: 0;
            }
            to {
                transform: translateY(0) rotateX(0);
                opacity: 1;
            }
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #2c3e50;
            text-decoration: none;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .logo::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(46, 139, 86, 0.2), transparent);
            animation: shimmer 3s infinite;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: #2E8B57; /* émeraude */
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s;
        }

        .logo:hover {
            color: #2E8B57;
            transform: scale(1.05);
        }

        .logo:hover::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #2c3e50;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            width: 0;
            height: 2px;
            background: #2E8B57;
            transition: all 0.3s;
            transform: translateX(-50%);
        }

        .nav-links a:hover {
            color: #2E8B57;
            transform: translateY(-2px);
        }

        .nav-links a:hover::before {
            width: 100%;
        }

        /* Sections avec animations d'entrée */
        section {
            padding: 100px 0;
            min-height: 100vh;
            display: flex;
            align-items: center;
            opacity: 0;
            animation: fadeInUp 1s cubic-bezier(0.215, 0.610, 0.355, 1) forwards;
            position: relative;
            overflow: hidden;
        }

        section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            opacity: 0;
            animation: rotateGradient 20s linear infinite;
            pointer-events: none;
        }

        section:hover::before {
            opacity: 0.5;
        }

        /* Accueil amélioré - palette émeraude */
        #accueil {
            text-align: center;
            background: linear-gradient(135deg, rgba(46, 139, 86, 0.95), rgba(29, 94, 63, 0.9));
            animation: fadeInScale 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            animation: float 4s ease-in-out infinite;
            text-shadow: 2px 2px 4px rgba(255,255,255,0.5);
        }

        .hero p {
            font-size: 1.3rem;
            color: #2c3e50;
            max-width: 600px;
            margin: 0 auto 2rem;
            animation: fadeInUp 1s ease-out 0.3s both, float 5s ease-in-out 1s infinite;
            font-weight: 500;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(135deg, #1D5E3F, #2E8B57);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s;
            font-weight: 500;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            z-index: 1;
            animation: pulseGlow 3s infinite;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
            z-index: -1;
        }

        .btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 30px rgba(46, 139, 86, 0.4);
            animation: none;
        }

        .btn:hover::before {
            left: 100%;
        }

        /* À propos amélioré - tons émeraude clairs */
        #apropos {
            background: linear-gradient(135deg, #C1E1C1, #A0D6A0); /* verts doux */
            position: relative;
        }

        .apropos-content {
            display: flex;
            align-items: center;
            gap: 4rem;
        }

        .apropos-text {
            flex: 1;
            animation: slideInBlur 1s ease-out;
        }

        .apropos-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #2c3e50;
            position: relative;
            display: inline-block;
        }

        .apropos-text h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 3px;
            background: #2E8B57;
            animation: slideWidth 2s ease-in-out infinite;
        }

        .apropos-text h2::before {
            content: '';
            position: absolute;
            bottom: -10px;
            right: 0;
            width: 50px;
            height: 3px;
            background: #2E8B57;
            animation: slideWidth 2s ease-in-out 1s infinite;
        }

        @keyframes slideWidth {
            0%, 100% {
                width: 50px;
            }
            50% {
                width: 100px;
            }
        }

        .apropos-text p {
            color: #2c3e50;
            margin-bottom: 1rem;
            transition: all 0.3s;
            position: relative;
            padding-left: 0;
            font-weight: 500;
        }

        .apropos-text p:hover {
            transform: translateX(15px);
            color: #2E8B57;
            padding-left: 10px;
        }

        .apropos-text p::before {
            content: '→';
            position: absolute;
            left: -20px;
            opacity: 0;
            transition: all 0.3s;
            color: #2E8B57;
        }

        .apropos-text p:hover::before {
            opacity: 1;
            left: -10px;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 2rem;
        }

        .skill {
            background: rgba(255, 255, 255, 0.8);
            padding: 10px 20px;
            border-radius: 30px;
            color: #2c3e50;
            font-weight: 500;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            animation: fadeInUp 0.5s ease-out;
            animation-fill-mode: both;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            border: 2px solid transparent;
        }

        .skill:nth-child(1) { animation-delay: 0.1s; }
        .skill:nth-child(2) { animation-delay: 0.2s; }
        .skill:nth-child(3) { animation-delay: 0.3s; }

        .skill::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(46, 139, 86, 0.2);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
            z-index: 0;
        }

        .skill:hover {
            transform: translateY(-8px) scale(1.1);
            background: #2E8B57;
            color: white;
            box-shadow: 0 10px 25px rgba(46, 139, 86, 0.5);
            border-color: #1D5E3F;
            animation: borderPulse 1.5s infinite;
        }

        .skill:hover::before {
            width: 200px;
            height: 200px;
        }

        .apropos-image {
            flex: 1;
            display: flex;
            justify-content: center;
            animation: fadeInRight 1s ease-out;
        }

        .apropos-image img {
            width: 80%;
            max-width: 300px;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            animation: floatRotate 5s ease-in-out infinite;
            border: 3px solid transparent;
            background: linear-gradient(white, white) padding-box,
                        linear-gradient(135deg, #2E8B57, #1D5E3F) border-box;
        }

        .apropos-image img:hover {
            transform: scale(1.08) rotate(3deg);
            box-shadow: 0 30px 60px rgba(46, 139, 86, 0.4);
        }

        /* Contact amélioré avec effets de cartes - thème émeraude */
        #contact {
            background: linear-gradient(135deg, #2E8B57 0%, #1D5E3F 100%);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        #contact::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 50%);
            animation: rotateGradient 25s linear infinite;
        }

        #contact h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease-out;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            color: #2c3e50;
        }

        .contact-content p {
            color: #2c3e50;
            font-weight: 500;
        }

        .contact-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
            perspective: 1000px;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 20px;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 2px solid rgba(255, 255, 255, 0.3);
            animation: fadeInScale 0.8s ease-out;
            animation-fill-mode: both;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
        }

        .contact-card:nth-child(1) { animation-delay: 0.2s; }
        .contact-card:nth-child(2) { animation-delay: 0.4s; }
        .contact-card:nth-child(3) { animation-delay: 0.6s; }

        .contact-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .contact-card:hover {
            transform: translateY(-20px) rotateX(5deg) scale(1.05);
            background: rgba(255, 255, 255, 0.3);
            box-shadow: 0 30px 50px rgba(0,0,0,0.2);
            border-color: rgba(255, 255, 255, 0.6);
            animation: pulseGlow 2s infinite;
        }

        .contact-card:hover::before {
            left: 100%;
        }

        .contact-card:hover::after {
            width: 300px;
            height: 300px;
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: inline-block;
            animation: float 3s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }

        .contact-card:hover .contact-icon {
            animation: pulseGlow 1s infinite, float 2s ease-in-out infinite;
            transform-origin: center;
        }

        .contact-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            transition: all 0.3s;
            position: relative;
            z-index: 1;
        }

        .contact-card:hover h3 {
            transform: scale(1.15);
            text-shadow: 0 0 10px rgba(255,255,255,0.5);
        }

        .contact-card p {
            margin-bottom: 1.5rem;
            color: #2c3e50;
            word-break: break-word;
            transition: all 0.3s;
            position: relative;
            z-index: 1;
            font-weight: 500;
        }

        .contact-card:hover p {
            transform: scale(1.05);
        }

        .contact-card .contact-link {
            display: inline-block;
            padding: 12px 28px;
            background: white;
            color: #2E8B57;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: none;
            position: relative;
            overflow: hidden;
            z-index: 1;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .contact-card .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.8), transparent);
            transition: left 0.5s;
            z-index: -1;
        }

        .contact-card .contact-link:hover {
            transform: scale(1.1) translateY(-3px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .contact-card .contact-link:hover::before {
            left: 100%;
        }

        .card-whatsapp .contact-link {
            background: #25D366;
            color: white;
        }

        .card-phone .contact-link {
            background: #2E8B57;
            color: white;
        }

        .card-email .contact-link {
            background: #1D5E3F;
            color: white;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .contact-links .contact-link {
            background: #1D5E3F;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            animation: fadeInUp 0.5s ease-out;
            animation-fill-mode: both;
            position: relative;
            overflow: hidden;
            color: white;
        }

        .contact-links .contact-link:nth-child(1) { animation-delay: 0.8s; }
        .contact-links .contact-link:nth-child(2) { animation-delay: 1s; }

        .contact-links .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .contact-links .contact-link:hover {
            transform: translateY(-8px) scale(1.1);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
            animation: pulseGlow 1.5s infinite;
        }

        .contact-links .contact-link:hover::before {
            left: 100%;
        }

        /* Footer amélioré - adapté émeraude */
        footer {
            background: #1D5E3F;
            color: white;
            text-align: center;
            padding: 2rem 0;
            position: relative;
            overflow: hidden;
        }

        footer p {
            animation: fadeInUp 1s ease-out, float 4s ease-in-out infinite;
            position: relative;
            z-index: 1;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            animation: slide 4s linear infinite;
        }

        footer::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #C1E1C1, transparent);
            animation: slideWidth 3s linear infinite;
        }

        @keyframes slide {
            0% {
                left: -100%;
            }
            100% {
                left: 200%;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 1rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .apropos-content {
                flex-direction: column-reverse;
                text-align: center;
            }

            .skills {
                justify-content: center;
            }

            .logo {
                font-size: 1.2rem;
                text-align: center;
            }

            .contact-cards {
                grid-template-columns: 1fr;
            }

            .apropos-image img {
                width: 70%;
                max-width: 250px;
            }

            .contact-card:hover {
                transform: translateY(-15px) scale(1.02);
            }
        }

        @media (max-width: 480px) {
            .apropos-image img {
                width: 90%;
                max-width: 220px;
            }

            .hero h1 {
                font-size: 1.8rem;
            }

            .contact-card {
                padding: 1.5rem;
            }

            .contact-card .contact-link {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
        }

        /* Animation de chargement de page */
        @keyframes pageLoad {
            0% {
                opacity: 0;
            }
            100% {
                opacity: 1;
            }
        }

        body {
            animation: pageLoad 0.5s ease-out;
        }

        /* Effet de vague pour le fond - adapté émeraude */
        .wave-bg {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 100px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.2" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,154.7C960,171,1056,181,1152,165.3C1248,149,1344,107,1392,85.3L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-repeat: no-repeat;
            background-size: cover;
            animation: wave 10s linear infinite;
            opacity: 0.2;
            pointer-events: none;
        }

        @keyframes wave {
            0% {
                transform: translateX(0) scaleX(1);
            }
            50% {
                transform: translateX(-25%) scaleX(1.2);
            }
            100% {
                transform: translateX(0) scaleX(1);
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <a href="#accueil" class="logo">RALAIARIMANANA Rindrarilaza Tsihosena Miharizo</a>
            <div class="nav-links">
                <a href="#accueil">Accueil</a>
                <a href="#apropos">À propos</a>
                <a href="#contact">Contact</a>
            </div>
        </nav>
    </header>

    <section id="accueil">
        <div class="container hero">
            <h1>Hello, je suis RALAIARIMANANA Rindrarilaza Tsihosena Miharizo</h1>
            <p>Développeur de site web et codage, j'aime crée des sites webs pour améliorer mes comptétences</p>
            <a href="#apropos" class="btn">En savoir plus</a>
        </div>
        <div class="wave-bg"></div>
    </section>

    <section id="apropos">
        <div class="container apropos-content">
            <div class="apropos-text">
                <h2>À propos de moi</h2>
                <p>Je suis un développeur passionné par le site web. J'aime transformer des idées créatives en solutions numériques fonctionnelles.J'ai acquis des bases en programmation (HTML,CSS, JavaSCRIPT).</p>
                <div class="skills">
                    <span class="skill">HTML</span>
                    <span class="skill">CSS</span>
                    <span class="skill">JavaScript</span>
                </div>
            </div>
            <div class="apropos-image">
                <img src="https://scontent-jnb2-1.xx.fbcdn.net/v/t39.30808-6/644817714_1510285927479413_1409992658423246295_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=cSnPtpTs9kwQ7kNvwG85bNE&_nc_oc=AdnUMjts8EhJ-r7LpQeEw6NHE4Bts3W0TVBctXQYa5UgmWaTFmmiv6z1M7616Y1zyDoaIluTNSvhU08wTzGWPq5r&_nc_zt=23&_nc_ht=scontent-jnb2-1.xx&_nc_gid=VmRvEJQrS9Xs-OJEWr9aHA&_nc_ss=8&oh=00_Afue_UxTWVW0bCxF5h4qY6UgOVewLGqRBzvIdqkYHeTovg&oe=69AA10FF" alt="Photo de profil">
            </div>
        </div>
        <div class="wave-bg"></div>
    </section>

    <section id="contact">
        <div class="container contact-content">
            <h2>Travaillons ensemble</h2>
            <p style="margin-bottom: 2rem; animation: fadeInUp 1s ease-out 0.2s both;">Vous avez un projet en tête ? N'hésitez pas à me contacter !</p>
            
            <div class="contact-cards">
                <!-- Carte WhatsApp -->
                <div class="contact-card card-whatsapp">
                    <span class="contact-icon">📱</span>
                    <h3>WhatsApp</h3>
                    <p>+261 38 62 419 92</p>
                    <a href="https://wa.me/261386241992?text=Bonjour%20Matthieu%2C%20je%20souhaite%20vous%20contacter%20pour%20un%20projet" 
                       class="contact-link" 
                       target="_blank">
                        Envoyer un message
                    </a>
                </div>

                <!-- Carte Téléphone -->
                <div class="contact-card card-phone">
                    <span class="contact-icon">📞</span>
                    <h3>Téléphone</h3>
                    <p>+261 38 62 419 92</p>
                    <a href="tel:+261386241992" class="contact-link">
                        Appeler maintenant
                    </a>
                </div>

                <!-- Carte Email -->
                <div class="contact-card card-email">
                    <span class="contact-icon">✉️</span>
                    <h3>Email</h3>
                    <p>ralaiarimananamiharizo@gmail.com</p>
                    <a href="mailto:ralaiarimananamiharizo@gmail.com?subject=Contact%20depuis%20mon%20portfolio&body=Bonjour%20Matthieu%2C" 
                       class="contact-link">
                        Envoyer un email
                    </a>
                </div>
            </div>

            <!-- Liens sociaux supplémentaires -->
            <div style="margin-top: 2rem;">
                <p style="margin-bottom: 1rem; animation: fadeInUp 1s ease-out 0.6s both;">Ou retrouvez-moi sur :</p>
                <div class="contact-links">
                    <a href="#" class="contact-link" style="background: #0077b5;">LinkedIn</a>
                    <a href="#" class="contact-link" style="background: #333;">GitHub</a>
                </div>
            </div>
        </div>
        <div class="wave-bg"></div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2026 RALAIARIMANANA Rindrarilaza Tsihosena Miharizo. Tous droits réservés.</p>
        </div>
    </footer>
</body>
</html>
