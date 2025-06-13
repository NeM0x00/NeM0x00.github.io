<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Youssef Elsheikh | Security Researcher</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --background: #050814;
            --text: #ffffff;
            --accent: #8A5CF5;
            --accent-light: #9D78F3;
            --secondary: #FF3A5E;
            --card-bg: rgba(30, 30, 50, 0.4);
            --border: rgba(255, 255, 255, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 80px;
        }

        body {
            background-color: var(--background);
            color: var(--text);
            overflow-x: hidden;
        }

        /* Loader */
        .loader-wrapper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--background);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            transition: opacity 0.5s ease-out, visibility 0.5s ease-out;
        }

        .loader {
            width: 48px;
            height: 48px;
            border: 5px solid var(--accent);
            border-bottom-color: transparent;
            border-radius: 50%;
            animation: rotation 1s linear infinite;
        }

        @keyframes rotation {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100;
            transition: background-color 0.3s ease;
        }

        header.scrolled {
            background-color: rgba(5, 8, 20, 0.9);
            backdrop-filter: blur(10px);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
        }

        .logo {
            display: flex;
            align-items: center;
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--text);
            text-decoration: none;
        }

        .logo-icon {
            color: var(--secondary);
            margin-right: 0.5rem;
            font-size: 1.5rem;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 2rem;
        }

        nav ul li a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            transition: color 0.3s ease;
            position: relative;
        }

        nav ul li a:hover {
            color: var(--accent);
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            transition: width 0.3s ease;
        }

        nav ul li a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 2rem;
            overflow: hidden;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
        }

        .hero-title {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1rem;
            line-height: 1.1;
        }

        .hero-title span {
            color: var(--accent);
            position: relative;
        }

        .hero-title span::before {
            content: '';
            position: absolute;
            left: -20px;
            top: 50%;
            width: 10px;
            height: 10px;
            background-color: var(--accent);
            border-radius: 50%;
            transform: translateY(-50%);
        }

        .hero-subtitle {
            font-size: 1.5rem;
            font-weight: 400;
            margin-bottom: 2rem;
            max-width: 600px;
            line-height: 1.5;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 2rem;
            background-color: transparent;
            border: 2px solid var(--accent);
            color: var(--text);
            font-weight: 600;
            text-decoration: none;
            border-radius: 4px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-primary {
            background-color: var(--accent);
        }

        .btn:hover {
            background-color: var(--accent);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(138, 92, 245, 0.3);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
        }

        .scroll-indicator .text {
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            opacity: 0.7;
        }

        .scroll-indicator .icon {
            width: 30px;
            height: 50px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 15px;
            position: relative;
        }

        .scroll-indicator .icon::before {
            content: '';
            position: absolute;
            top: 8px;
            left: 50%;
            width: 6px;
            height: 6px;
            background-color: var(--text);
            border-radius: 50%;
            transform: translateX(-50%);
            animation: scrollAnim 2s infinite;
        }

        @keyframes scrollAnim {
            0% { top: 8px; opacity: 1; }
            80% { opacity: 0; }
            100% { top: 32px; opacity: 0; }
        }

        .progress-bar {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 10;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Background Animation */
        .bg-animation {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            opacity: 0.6;
        }

        /* About Section */
        .section {
            padding: 6rem 2rem;
            position: relative;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background-color: var(--accent);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-text .highlight {
            color: var(--accent);
            font-weight: 600;
        }

        .timeline {
            position: relative;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 2px;
            height: 100%;
            background-color: var(--accent);
        }

        .timeline-item {
            position: relative;
            padding-left: 30px;
            margin-bottom: 2rem;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -6px;
            top: 8px;
            width: 14px;
            height: 14px;
            background-color: var(--accent);
            border-radius: 50%;
        }

        .timeline-title {
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .timeline-date {
            font-size: 0.9rem;
            color: var(--accent);
            margin-bottom: 0.5rem;
        }

        .timeline-description {
            font-size: 0.95rem;
            opacity: 0.8;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.2);
        }

        .project-card.featured {
            grid-column: span 2;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-tag {
            display: inline-block;
            padding: 0.3rem 0.8rem;
            background-color: rgba(138, 92, 245, 0.2);
            color: var(--accent);
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .project-description {
            font-size: 1rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            opacity: 0.8;
        }

        .project-features {
            margin-bottom: 1.5rem;
        }

        .project-features h4 {
            font-size: 1rem;
            margin-bottom: 0.8rem;
        }

        .project-features ul {
            list-style: none;
        }

        .project-features li {
            position: relative;
            padding-left: 1.5rem;
            margin-bottom: 0.5rem;
            font-size: 0.95rem;
            opacity: 0.8;
        }

        .project-features li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--accent);
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            padding: 0.3rem 0.8rem;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            font-size: 0.8rem;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        /* Blog Section */
        .blog-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .blog-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .blog-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.2);
        }

        .blog-image {
            height: 200px;
            overflow: hidden;
        }

        .blog-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .blog-card:hover .blog-image img {
            transform: scale(1.05);
        }

        .blog-content {
            padding: 1.5rem;
        }

        .blog-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .blog-date {
            font-size: 0.9rem;
            opacity: 0.7;
        }

        .blog-tags {
            display: flex;
            gap: 0.5rem;
        }

        .blog-tag {
            padding: 0.2rem 0.6rem;
            background-color: rgba(138, 92, 245, 0.2);
            color: var(--accent);
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .blog-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 1rem;
            line-height: 1.4;
        }

        .blog-excerpt {
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            opacity: 0.8;
        }

        .blog-link {
            color: var(--accent);
            text-decoration: none;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: gap 0.3s ease;
        }

        .blog-link:hover {
            gap: 0.8rem;
        }

        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .contact-info p {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 2rem;
            opacity: 0.8;
        }

        .social-links {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 8px;
            text-decoration: none;
            color: var(--text);
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateX(10px);
            border-color: var(--accent);
        }

        .social-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-icon svg {
            width: 20px;
            height: 20px;
            fill: currentColor;
        }

        .social-info h4 {
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
        }

        .social-info p {
            font-size: 0.9rem;
            opacity: 0.7;
            margin: 0;
        }

        .contact-form {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 2rem;
        }

        .contact-form h3 {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            background-color: rgba(255, 255, 255, 0.1);
            border: 1px solid var(--border);
            border-radius: 4px;
            color: var(--text);
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            padding: 2rem;
            text-align: center;
            border-top: 1px solid var(--border);
        }

        footer p {
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero-title {
                font-size: 3rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .contact-container {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .project-card.featured {
                grid-column: span 1;
            }
        }

        @media (max-width: 768px) {
            header {
                padding: 1rem;
            }

            nav {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                height: 100vh;
                background-color: var(--background);
                display: flex;
                align-items: center;
                justify-content: center;
                transition: right 0.3s ease;
                z-index: 99;
            }

            nav.active {
                right: 0;
                box-shadow: -5px 0 20px rgba(0, 0, 0, 0.2);
            }

            nav ul {
                flex-direction: column;
                align-items: center;
            }

            nav ul li {
                margin: 1.5rem 0;
            }

            .mobile-menu-btn {
                display: block;
                z-index: 100;
            }

            .hero {
                padding: 0 1rem;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.2rem;
            }

            .section {
                padding: 4rem 1rem;
            }

            .projects-grid,
            .blog-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Loader -->
    <div class="loader-wrapper">
        <div class="loader"></div>
    </div>

    <!-- Progress Bar -->
    <div class="progress-bar">0.00%</div>

    <!-- Header -->
    <header>
        <a href="#" class="logo">
            <span class="logo-icon">⚡</span>
            nem0x00
        </a>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <button class="mobile-menu-btn">☰</button>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="bg-animation">
            <canvas id="waveCanvas"></canvas>
        </div>
        <div class="hero-content">
            <h1 class="hero-title fade-in">Hi, I'm <span>Youssef</span></h1>
            <p class="hero-subtitle fade-in">
                I'm a bug bounty hunter and Android security researcher passionate about automation, tooling, and responsible disclosure.
            </p>
            <div class="cta-buttons fade-in">
                <a href="#projects" class="btn btn-primary">View Projects</a>
                <a href="#contact" class="btn">Get In Touch</a>
            </div>
        </div>
        <div class="scroll-indicator" onclick="scrollToSection('#about')">
            <span class="text">Scroll Down</span>
            <div class="icon"></div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title fade-in">About Me</h2>
            <div class="about-content">
                <div class="about-text fade-in">
                    <p>
                        I'm a cybersecurity researcher specializing in Android and web app penetration testing. Acknowledged by 
                        <span class="highlight">Google</span>, <span class="highlight">Unity</span>, 
                        <span class="highlight">Swisscom</span>, <span class="highlight">Estonia Gov</span>, and others.
                    </p>
                    <p>
                        Currently pursuing <span class="highlight">OSCE3</span> and multiple eLearnSecurity certifications. 
                        I build tools to automate and enhance bug bounty workflows, focusing on creating efficient solutions 
                        for security testing and vulnerability discovery.
                    </p>
                    <p>
                        My expertise includes Android security research, web application penetration testing, and developing 
                        custom security tools. I'm passionate about sharing knowledge with the cybersecurity community and 
                        contributing to a more secure digital environment.
                    </p>
                </div>
                <div class="timeline fade-in">
                    <div class="timeline-item">
                        <h3 class="timeline-title">Google Security Acknowledgment</h3>
                        <div class="timeline-date">2024</div>
                        <p class="timeline-description">Recognized for responsible disclosure of security vulnerabilities</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="timeline-title">Unity Technologies</h3>
                        <div class="timeline-date">2023</div>
                        <p class="timeline-description">Security research acknowledgment for platform vulnerabilities</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="timeline-title">Swisscom Bug Bounty</h3>
                        <div class="timeline-date">2023</div>
                        <p class="timeline-description">Successful vulnerability disclosure and bounty award</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="timeline-title">Estonia Government</h3>
                        <div class="timeline-date">2022</div>
                        <p class="timeline-description">Critical infrastructure security research acknowledgment</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Projects</h2>
            <div class="projects-grid">
                <div class="project-card featured fade-in">
                    <div class="project-content">
                        <div class="project-tag">Featured</div>
                        <h3 class="project-title">BADGPT</h3>
                        <p class="project-description">
                            AI-powered security testing tool that leverages GPT models to enhance bug bounty workflows, 
                            automate vulnerability discovery, and generate intelligent test cases.
                        </p>
                        <div class="project-features">
                            <h4>Key Features:</h4>
                            <ul>
                                <li>Automated payload generation</li>
                                <li>Intelligent vulnerability analysis</li>
                                <li>Custom prompt engineering for security testing</li>
                                <li>Integration with popular security tools</li>
                            </ul>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">Go</span>
                            <span class="tech-tag">OpenAI API</span>
                            <span class="tech-tag">CLI</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NeM0x00" target="_blank" class="btn btn-primary">View on GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-content">
                        <div class="project-tag">Active</div>
                        <h3 class="project-title">Frida Android Scanner</h3>
                        <p class="project-description">
                            Comprehensive Android security scanner built with Frida for dynamic analysis, 
                            runtime manipulation, and vulnerability detection in mobile applications.
                        </p>
                        <div class="project-features">
                            <h4>Key Features:</h4>
                            <ul>
                                <li>SSL pinning bypass automation</li>
                                <li>Runtime method hooking</li>
                                <li>Certificate validation bypass</li>
                            </ul>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">Frida</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Android</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NeM0x00" target="_blank" class="btn btn-primary">View on GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-content">
                        <div class="project-tag">Beta</div>
                        <h3 class="project-title">IDOR Hunter</h3>
                        <p class="project-description">
                            Automated tool for detecting Insecure Direct Object References (IDOR) vulnerabilities 
                            across web applications with intelligent parameter fuzzing.
                        </p>
                        <div class="project-features">
                            <h4>Key Features:</h4>
                            <ul>
                                <li>Automated endpoint discovery</li>
                                <li>Parameter manipulation testing</li>
                                <li>Session management bypass</li>
                            </ul>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Requests</span>
                            <span class="tech-tag">Threading</span>
                        </div>
                        <div class="project-links">
                            <a href="https://github.com/NeM0x00" target="_blank" class="btn btn-primary">View on GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Blog</h2>
            <div class="blog-grid">
                <div class="blog-card fade-in">
                    <div class="blog-image">
                        <img src="https://placehold.co/600x400/252538/CCCCCC?text=Android+Security" alt="Android Security">
                    </div>
                    <div class="blog-content">
                        <div class="blog-meta">
                            <span class="blog-date">Dec 15, 2024</span>
                            <div class="blog-tags">
                                <span class="blog-tag">Android</span>
                                <span class="blog-tag">Frida</span>
                            </div>
                        </div>
                        <h3 class="blog-title">Advanced Android SSL Pinning Bypass with Frida</h3>
                        <p class="blog-excerpt">
                            Deep dive into bypassing modern SSL pinning implementations in Android applications 
                            using custom Frida scripts and runtime manipulation techniques...
                        </p>
                        <a href="#" class="blog-link">
                            Read More
                            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </a>
                    </div>
                </div>
                <div class="blog-card fade-in">
                    <div class="blog-image">
                        <img src="https://placehold.co/600x400/252538/CCCCCC?text=Bug+Bounty" alt="Bug Bounty">
                    </div>
                    <div class="blog-content">
                        <div class="blog-meta">
                            <span class="blog-date">Nov 28, 2024</span>
                            <div class="blog-tags">
                                <span class="blog-tag">Bug Bounty</span>
                                <span class="blog-tag">Web</span>
                            </div>
                        </div>
                        <h3 class="blog-title">Automating IDOR Detection in Large Applications</h3>
                        <p class="blog-excerpt">
                            How I built a custom tool to automatically detect Insecure Direct Object References 
                            across thousands of endpoints, leading to multiple critical findings...
                        </p>
                        <a href="#" class="blog-link">
                            Read More
                            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </a>
                    </div>
                </div>
                <div class="blog-card fade-in">
                    <div class="blog-image">
                        <img src="https://placehold.co/600x400/252538/CCCCCC?text=AI+Security" alt="AI Security">
                    </div>
                    <div class="blog-content">
                        <div class="blog-meta">
                            <span class="blog-date">Oct 12, 2024</span>
                            <div class="blog-tags">
                                <span class="blog-tag">Tools</span>
                                <span class="blog-tag">Go</span>
                            </div>
                        </div>
                        <h3 class="blog-title">Building BADGPT: AI-Powered Security Testing</h3>
                        <p class="blog-excerpt">
                            The story behind creating BADGPT, a tool that leverages AI to enhance 
                            bug bounty workflows and automate vulnerability discovery processes...
                        </p>
                        <a href="#" class="blog-link">
                            Read More
                            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M5 12H19M19 12L12 5M19 12L12 19" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
        <div class="container">
            <h2 class="section-title fade-in">Contact</h2>
            <div class="contact-container">
                <div class="contact-info fade-in">
                    <h3>Let's Connect</h3>
                    <p>
                        I'm always open to discussing security research, bug bounty collaboration, 
                        tool development, or sharing knowledge with the cybersecurity community.
                    </p>
                    <div class="social-links">
                        <a href="https://github.com/NeM0x00" target="_blank" class="social-link">
                            <div class="social-icon">
                                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                                </svg>
                            </div>
                            <div class="social-info">
                                <h4>GitHub</h4>
                                <p>github.com/NeM0x00</p>
                            </div>
                        </a>
                        <a href="https://linkedin.com/in/yousef-elsheikh-b1573a1b0/" target="_blank" class="social-link">
                            <div class="social-icon">
                                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
                                </svg>
                            </div>
                            <div class="social-info">
                                <h4>LinkedIn</h4>
                                <p>Professional Network</p>
                            </div>
                        </a>
                        <a href="https://twitter.com/nem0x00" target="_blank" class="social-link">
                            <div class="social-icon">
                                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
                                </svg>
                            </div>
                            <div class="social-info">
                                <h4>Twitter/X</h4>
                                <p>@nem0x00</p>
                            </div>
                        </a>
                    </div>
                </div>
                <div class="contact-form fade-in">
                    <h3>Send a Message</h3>
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" name="subject" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" name="message" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Youssef Elsheikh (nem0x00). All rights reserved.</p>
    </footer>

    <script>
        // Loader
        window.addEventListener('load', function() {
            const loader = document.querySelector('.loader-wrapper');
            setTimeout(() => {
                loader.style.opacity = '0';
                setTimeout(() => {
                    loader.style.display = 'none';
                }, 500);
            }, 1000);
        });

        // Mobile Menu Toggle
        const menuBtn = document.querySelector('.mobile-menu-btn');
        const nav = document.querySelector('nav');
        
        menuBtn.addEventListener('click', function() {
            nav.classList.toggle('active');
            menuBtn.textContent = nav.classList.contains('active') ? '✕' : '☰';
        });

        // Close menu when clicking on a link
        document.querySelectorAll('nav a').forEach(link => {
            link.addEventListener('click', function() {
                nav.classList.remove('active');
                menuBtn.textContent = '☰';
            });
        });

        // Scroll to section
        function scrollToSection(selector) {
            const section = document.querySelector(selector);
            if (section) {
                window.scrollTo({
                    top: section.offsetTop - 80,
                    behavior: 'smooth'
                });
            }
        }

        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Scroll progress
        window.addEventListener('scroll', function() {
            const scrollTop = window.scrollY;
            const docHeight = document.documentElement.scrollHeight - window.innerHeight;
            const scrollPercent = (scrollTop / docHeight) * 100;
            document.querySelector('.progress-bar').textContent = scrollPercent.toFixed(2) + '%';
        });

        // Fade in animations
        const fadeElements = document.querySelectorAll('.fade-in');
        
        function checkFade() {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementBottom = element.getBoundingClientRect().bottom;
                
                if (elementTop < window.innerHeight - 100 && elementBottom > 0) {
                    element.classList.add('active');
                }
            });
        }
        
        window.addEventListener('scroll', checkFade);
        window.addEventListener('load', checkFade);

        // Contact form handling
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Simple validation
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            if (!name || !email || !subject || !message) {
                alert('Please fill in all fields.');
                return;
            }
            
            // Simulate form submission
            const submitBtn = this.querySelector('button[type="submit"]');
            const originalText = submitBtn.textContent;
            submitBtn.textContent = 'Sending...';
            submitBtn.disabled = true;
            
            setTimeout(() => {
                alert('Thank you for your message! I\'ll get back to you soon.');
                this.reset();
                submitBtn.textContent = originalText;
                submitBtn.disabled = false;
            }, 2000);
        });

        // Wave animation
        const canvas = document.getElementById('waveCanvas');
        const ctx = canvas.getContext('2d');
        let width, height;
        let points = [];
        let mouse = {
            x: 0,
            y: 0,
            px: 0,
            py: 0,
            active: false
        };

        function resize() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
            
            // Create points
            points = [];
            const spacing = 50;
            const xCount = Math.ceil(width / spacing) + 1;
            const yCount = Math.ceil(height / spacing) + 1;
            
            for (let y = 0; y < yCount; y++) {
                for (let x = 0; x < xCount; x++) {
                    points.push({
                        x: x * spacing,
                        y: y * spacing,
                        ox: x * spacing,
                        oy: y * spacing,
                        vx: 0,
                        vy: 0
                    });
                }
            }
        }

        function draw() {
            ctx.clearRect(0, 0, width, height);
            
            // Update points
            for (let i = 0; i < points.length; i++) {
                const point = points[i];
                
                // Mouse interaction
                if (mouse.active) {
                    const dx = point.x - mouse.x;
                    const dy = point.y - mouse.y;
                    const dist = Math.sqrt(dx * dx + dy * dy);
                    const influence = Math.max(0, 100 - dist) / 100;
                    
                    if (influence > 0) {
                        point.vx += (mouse.x - mouse.px) * influence;
                        point.vy += (mouse.y - mouse.py) * influence;
                    }
                }
                
                // Spring back to original position
                point.vx += (point.ox - point.x) * 0.05;
                point.vy += (point.oy - point.y) * 0.05;
                
                // Damping
                point.vx *= 0.95;
                point.vy *= 0.95;
                
                // Update position
                point.x += point.vx;
                point.y += point.vy;
            }
            
            // Draw grid
            ctx.beginPath();
            ctx.strokeStyle = 'rgba(138, 92, 245, 0.15)';
            ctx.lineWidth = 1;
            
            // Draw horizontal lines
            const spacing = 50;
            const xCount = Math.ceil(width / spacing) + 1;
            const yCount = Math.ceil(height / spacing) + 1;
            
            for (let y = 0; y < yCount; y++) {
                ctx.beginPath();
                for (let x = 0; x < xCount; x++) {
                    const i = y * xCount + x;
                    if (x === 0) {
                        ctx.moveTo(points[i].x, points[i].y);
                    } else {
                        ctx.lineTo(points[i].x, points[i].y);
                    }
                }
                ctx.stroke();
            }
            
            // Draw vertical lines
            for (let x = 0; x < xCount; x++) {
                ctx.beginPath();
                for (let y = 0; y < yCount; y++) {
                    const i = y * xCount + x;
                    if (y === 0) {
                        ctx.moveTo(points[i].x, points[i].y);
                    } else {
                        ctx.lineTo(points[i].x, points[i].y);
                    }
                }
                ctx.stroke();
            }
            
            // Update mouse previous position
            mouse.px = mouse.x;
            mouse.py = mouse.y;
            
            requestAnimationFrame(draw);
        }

        // Mouse events
        canvas.addEventListener('mousemove', function(e) {
            mouse.x = e.clientX;
            mouse.y = e.clientY;
            mouse.active = true;
        });

        canvas.addEventListener('mouseout', function() {
            mouse.active = false;
        });

        canvas.addEventListener('touchmove', function(e) {
            e.preventDefault();
            mouse.x = e.touches[0].clientX;
            mouse.y = e.touches[0].clientY;
            mouse.active = true;
        });

        canvas.addEventListener('touchend', function() {
            mouse.active = false;
        });

        // Initialize
        window.addEventListener('resize', resize);
        resize();
        draw();
    </script>
</body>
</html>
