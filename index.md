---
layout: default
title: Youssef Elsheikh - Security Researcher
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Youssef Elsheikh - Security Researcher</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --background: #0f1419;
            --foreground: #f5f7fa;
            --card: #171c22;
            --card-foreground: #f5f7fa;
            --primary: #3db2ff;
            --primary-foreground: #ffffff;
            --secondary: #1e252e;
            --secondary-foreground: #f5f7fa;
            --muted: #1a2027;
            --muted-foreground: #a0aec0;
            --accent: #1e252e;
            --accent-foreground: #f5f7fa;
            --border: #2a3441;
            --input: #2a3441;
            --ring: #3db2ff;
            --radius: 0.75rem;
            --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-sans);
            background-color: var(--background);
            color: var(--foreground);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        /* Layout */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }

        .section {
            padding: 5rem 0;
        }

        .grid {
            display: grid;
            gap: 1.5rem;
        }

        .grid-2 {
            grid-template-columns: repeat(1, 1fr);
        }

        .grid-3 {
            grid-template-columns: repeat(1, 1fr);
        }

        .grid-4 {
            grid-template-columns: repeat(1, 1fr);
        }

        @media (min-width: 768px) {
            .grid-2 {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .grid-3 {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .grid-4 {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .grid-4 {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        .flex {
            display: flex;
        }

        .flex-col {
            flex-direction: column;
        }

        .items-center {
            align-items: center;
        }

        .justify-between {
            justify-content: space-between;
        }

        .justify-center {
            justify-content: center;
        }

        .gap-4 {
            gap: 1rem;
        }

        .gap-6 {
            gap: 1.5rem;
        }

        .gap-8 {
            gap: 2rem;
        }

        /* Typography */
        h1, h2, h3, h4, h5, h6 {
            font-weight: 600;
            line-height: 1.2;
            margin-bottom: 1rem;
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
        }

        h2 {
            font-size: 2rem;
        }

        h3 {
            font-size: 1.5rem;
        }

        h4 {
            font-size: 1.25rem;
        }

        p {
            margin-bottom: 1rem;
        }

        @media (min-width: 768px) {
            h1 {
                font-size: 3.5rem;
            }
            
            h2 {
                font-size: 2.5rem;
            }
        }

        .text-lg {
            font-size: 1.125rem;
        }

        .text-xl {
            font-size: 1.25rem;
        }

        .text-2xl {
            font-size: 1.5rem;
        }

        .font-medium {
            font-weight: 500;
        }

        .font-semibold {
            font-weight: 600;
        }

        .font-bold {
            font-weight: 700;
        }

        .text-center {
            text-align: center;
        }

        .text-primary {
            color: var(--primary);
        }

        .text-muted {
            color: var(--muted-foreground);
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(15, 20, 25, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid var(--border);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 4rem;
            padding: 0 1.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .nav-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            transition: color 0.3s ease;
        }

        .nav-logo:hover {
            color: var(--primary-foreground);
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
        }

        .nav-link {
            color: var(--muted-foreground);
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-link:hover,
        .nav-link.active {
            color: var(--primary);
        }

        .nav-link.active::after {
            content: '';
            position: absolute;
            bottom: -0.5rem;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--primary);
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 0.25rem;
        }

        .hamburger span {
            width: 1.5rem;
            height: 2px;
            background: var(--foreground);
            transition: 0.3s;
        }

        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 4rem;
                flex-direction: column;
                background-color: var(--background);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
                padding: 2rem 0;
                z-index: 1000;
            }

            .nav-menu.active {
                left: 0;
            }

            .hamburger {
                display: flex;
            }
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 0.75rem 1.5rem;
            border-radius: var(--radius);
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            font-size: 1rem;
        }

        .btn-lg {
            padding: 1rem 2rem;
            font-size: 1.125rem;
        }

        .btn-primary {
            background-color: var(--primary);
            color: var(--primary-foreground);
        }

        .btn-primary:hover {
            background-color: color-mix(in srgb, var(--primary) 90%, black);
            transform: translateY(-2px);
        }

        .btn-outline {
            background-color: transparent;
            border: 1px solid var(--primary);
            color: var(--primary);
        }

        .btn-outline:hover {
            background-color: color-mix(in srgb, var(--primary) 10%, transparent);
            transform: translateY(-2px);
        }

        .btn-ghost {
            background-color: transparent;
            color: var(--primary);
        }

        .btn-ghost:hover {
            background-color: color-mix(in srgb, var(--primary) 10%, transparent);
        }

        /* Cards */
        .card {
            background-color: var(--card);
            border-radius: var(--radius);
            border: 1px solid var(--border);
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: color-mix(in srgb, var(--primary) 30%, transparent);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .card-content {
            padding: 1.5rem;
        }

        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            padding: 5rem 0;
        }

        .hero-content {
            max-width: 800px;
            z-index: 2;
        }

        .hero-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }

        .floating-element {
            position: absolute;
            width: 200px;
            height: 200px;
            background: linear-gradient(45deg, rgba(61, 178, 255, 0.1), rgba(61, 178, 255, 0.05));
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .floating-element:nth-child(1) {
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-element:nth-child(2) {
            top: 60%;
            right: 10%;
            animation-delay: 2s;
        }

        .floating-element:nth-child(3) {
            bottom: 20%;
            left: 50%;
            animation-delay: 4s;
        }

        /* Blog Cards */
        .blog-card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .blog-date {
            color: var(--muted-foreground);
            font-size: 0.875rem;
        }

        .blog-tags {
            display: flex;
            gap: 0.5rem;
        }

        .tag {
            background: color-mix(in srgb, var(--primary) 10%, transparent);
            color: var(--primary);
            padding: 0.25rem 0.75rem;
            border-radius: 1rem;
            font-size: 0.75rem;
            font-weight: 500;
        }

        /* Project Cards */
        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }

        .project-status {
            padding: 0.25rem 0.75rem;
            border-radius: 1rem;
            font-size: 0.75rem;
            font-weight: 500;
            background: color-mix(in srgb, var(--primary) 10%, transparent);
            color: var(--primary);
        }

        .project-features {
            margin-bottom: 1.5rem;
        }

        .project-features ul {
            list-style: none;
            padding-left: 0;
        }

        .project-features li {
            color: var(--muted-foreground);
            margin-bottom: 0.5rem;
            position: relative;
            padding-left: 1.5rem;
        }

        .project-features li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--primary);
            font-weight: bold;
        }

        .project-tech {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: var(--muted);
            color: var(--muted-foreground);
            padding: 0.25rem 0.75rem;
            border-radius: 0.5rem;
            font-size: 0.75rem;
            font-weight: 500;
        }

        /* Timeline */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 1.5rem;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--primary);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 2rem;
            padding-left: 3rem;
        }

        .timeline-marker {
            position: absolute;
            left: 0.75rem;
            top: 0;
            width: 1rem;
            height: 1rem;
            background: var(--primary);
            border-radius: 50%;
            border: 3px solid var(--background);
            transform: translateX(-50%);
        }

        .timeline-content {
            background: var(--card);
            padding: 1.5rem;
            border-radius: var(--radius);
            border: 1px solid var(--border);
        }

        .timeline-date {
            color: var(--primary);
            font-weight: 500;
            font-size: 0.875rem;
        }

        /* Social Links */
        .social-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: var(--card);
            border-radius: var(--radius);
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-3px);
            border-color: color-mix(in srgb, var(--primary) 30%, transparent);
        }

        .social-icon {
            width: 2.5rem;
            height: 2.5rem;
            border-radius: 50%;
            background: var(--muted);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-icon svg {
            width: 1.25rem;
            height: 1.25rem;
        }

        /* Form Elements */
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
            padding: 0.75rem 1rem;
            background: var(--muted);
            border: 1px solid var(--border);
            border-radius: var(--radius);
            color: var(--foreground);
            font-family: inherit;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        /* Utility Classes */
        .mb-1 { margin-bottom: 0.25rem; }
        .mb-2 { margin-bottom: 0.5rem; }
        .mb-3 { margin-bottom: 0.75rem; }
        .mb-4 { margin-bottom: 1rem; }
        .mb-6 { margin-bottom: 1.5rem; }
        .mb-8 { margin-bottom: 2rem; }
        .mb-12 { margin-bottom: 3rem; }
        .mb-16 { margin-bottom: 4rem; }

        .mt-4 { margin-top: 1rem; }
        .mt-8 { margin-top: 2rem; }
        .mt-12 { margin-top: 3rem; }
        .mt-16 { margin-top: 4rem; }
        .mt-24 { margin-top: 6rem; }

        .py-16 { padding-top: 4rem; padding-bottom: 4rem; }
        .px-6 { padding-left: 1.5rem; padding-right: 1.5rem; }

        .w-full { width: 100%; }
        .max-w-4xl { max-width: 56rem; }
        .max-w-5xl { max-width: 64rem; }
        .mx-auto { margin-left: auto; margin-right: auto; }

        .hidden { display: none; }
        .block { display: block; }

        .relative { position: relative; }
        .absolute { position: absolute; }

        .overflow-hidden { overflow: hidden; }

        /* Animations */
        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            opacity: 0;
            animation: fadeInUp 0.8s ease forwards;
        }

        .delay-100 { animation-delay: 0.1s; }
        .delay-200 { animation-delay: 0.2s; }
        .delay-300 { animation-delay: 0.3s; }
        .delay-400 { animation-delay: 0.4s; }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 1rem;
            }

            .hero {
                padding: 4rem 0;
            }

            .timeline::before {
                left: 1rem;
            }

            .timeline-item {
                padding-left: 2.5rem;
            }

            .timeline-marker {
                left: 0.5rem;
            }
        }

        /* Print styles */
        @media print {
            .navbar,
            .btn {
                display: none;
            }

            body {
                background: white;
                color: black;
            }

            .card {
                break-inside: avoid;
            }
        }

        /* Accessibility */
        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }

        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }

        /* Focus styles for accessibility */
        a:focus,
        button:focus,
        input:focus,
        textarea:focus {
            outline: 2px solid var(--primary);
            outline-offset: 2px;
        }

        /* Tab navigation */
        .tab-container {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 2rem;
            overflow-x: auto;
            padding-bottom: 0.5rem;
        }

        .tab-btn {
            padding: 0.5rem 1rem;
            border-radius: 9999px;
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid var(--border);
            background: transparent;
            color: var(--muted-foreground);
            white-space: nowrap;
        }

        .tab-btn.active {
            background-color: var(--primary);
            color: var(--primary-foreground);
            border-color: var(--primary);
        }

        .tab-btn:hover:not(.active) {
            border-color: color-mix(in srgb, var(--primary) 30%, transparent);
            color: var(--primary);
        }

        /* Page content */
        .page-content {
            padding-top: 5rem;
            min-height: 100vh;
        }

        /* Icons */
        .icon {
            display: inline-block;
            width: 1.5rem;
            height: 1.5rem;
            stroke-width: 0;
            stroke: currentColor;
            fill: currentColor;
            vertical-align: middle;
        }

        .icon-sm {
            width: 1rem;
            height: 1rem;
        }

        .icon-lg {
            width: 2rem;
            height: 2rem;
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-container">
            <a href="#home" class="nav-logo">nem0x00</a>
            <div class="nav-menu">
                <a href="#home" class="nav-link active" data-section="home">Home</a>
                <a href="#about" class="nav-link" data-section="about">About</a>
                <a href="#blog" class="nav-link" data-section="blog">Blog</a>
                <a href="#projects" class="nav-link" data-section="projects">Projects</a>
                <a href="#cv" class="nav-link" data-section="cv">CV</a>
                <a href="#contact" class="nav-link" data-section="contact">Contact</a>
            </div>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Home Section -->
    <section id="home" class="section hero">
        <div class="hero-background">
            <div class="floating-element"></div>
            <div class="floating-element"></div>
            <div class="floating-element"></div>
        </div>
        
        <div class="container">
            <div class="hero-content fade-in">
                <p class="text-muted mb-2">Hey, I'm</p>
                <h1 class="mb-2">Youssef Elsheikh</h1>
                <p class="text-muted mb-6">— also known as <span class="text-primary">nem0x00</span></p>
                
                <p class="text-xl mb-8">
                    I'm a bug bounty hunter and Android security researcher passionate about 
                    <span class="text-primary">automation</span>, <span class="text-primary">tooling</span>, and 
                    <span class="text-primary">responsible disclosure</span>.
                </p>
                
                <div class="flex gap-4 mb-16">
                    <a href="#about" class="btn btn-primary btn-lg">About Me</a>
                    <a href="#blog" class="btn btn-outline btn-lg">Read My Blog</a>
                </div>
            </div>
            
            <div class="mt-24">
                <h2 class="mb-8">Recent Articles</h2>
                <div class="grid grid-2 gap-6">
                    <div class="card fade-in delay-100">
                        <img src="https://placeholder.com/800x400" alt="Android SSL Pinning" class="card-image">
                        <div class="card-content">
                            <div class="blog-card-header">
                                <span class="blog-date">Dec 15, 2024</span>
                                <div class="blog-tags">
                                    <span class="tag">Android</span>
                                    <span class="tag">Frida</span>
                                </div>
                            </div>
                            <h3 class="mb-3">Advanced Android SSL Pinning Bypass with Frida</h3>
                            <p class="text-muted mb-4">Deep dive into bypassing modern SSL pinning implementations in Android applications using custom Frida scripts and runtime manipulation techniques...</p>
                            <a href="#blog" class="text-primary font-medium">Read More →</a>
                        </div>
                    </div>
                    
                    <div class="card fade-in delay-200">
                        <img src="https://placeholder.com/800x400" alt="IDOR Detection" class="card-image">
                        <div class="card-content">
                            <div class="blog-card-header">
                                <span class="blog-date">Nov 28, 2024</span>
                                <div class="blog-tags">
                                    <span class="tag">Bug Bounty</span>
                                    <span class="tag">Web</span>
                                </div>
                            </div>
                            <h3 class="mb-3">Automating IDOR Detection in Large Applications</h3>
                            <p class="text-muted mb-4">How I built a custom tool to automatically detect Insecure Direct Object References across thousands of endpoints, leading to multiple critical findings...</p>
                            <a href="#blog" class="text-primary font-medium">Read More →</a>
                        </div>
                    </div>
                </div>
                
                <div class="text-center mt-8">
                    <a href="#blog" class="btn btn-ghost">View All Articles</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section page-content">
        <div class="container max-w-4xl">
            <div class="mb-16 fade-in">
                <h1 class="mb-6">About Me</h1>
                <p class="text-xl text-muted">
                    I'm a cybersecurity researcher specializing in Android and web app penetration testing. Acknowledged by 
                    <span class="text-primary">Google</span>, <span class="text-primary">Unity</span>,
                    <span class="text-primary"> Swisscom</span>, <span class="text-primary">Estonia Gov</span>, and 
                    others. Currently pursuing <span class="text-primary">OSCE3</span> and multiple eLearnSecurity 
                    certifications. I build tools to automate and enhance bug bounty workflows.
                </p>
            </div>

            <div class="mb-16 fade-in delay-100">
                <h2 class="mb-8">Recognition Timeline</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="flex justify-between mb-2">
                                <h3>Google Security Acknowledgment</h3>
                                <span class="timeline-date">2024</span>
                            </div>
                            <p class="text-muted">Recognized for responsible disclosure of security vulnerabilities</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="flex justify-between mb-2">
                                <h3>Unity Technologies</h3>
                                <span class="timeline-date">2023</span>
                            </div>
                            <p class="text-muted">Security research acknowledgment for platform vulnerabilities</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="flex justify-between mb-2">
                                <h3>Swisscom Bug Bounty</h3>
                                <span class="timeline-date">2023</span>
                            </div>
                            <p class="text-muted">Successful vulnerability disclosure and bounty award</p>
                        </div>
                    </div>
                    
                    <div class="timeline-item">
                        <div class="timeline-marker"></div>
                        <div class="timeline-content">
                            <div class="flex justify-between mb-2">
                                <h3>Estonia Government</h3>
                                <span class="timeline-date">2022</span>
                            </div>
                            <p class="text-muted">Critical infrastructure security research acknowledgment</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="fade-in delay-200">
                <h2 class="mb-8">Certifications & Learning</h2>
                <div class="grid grid-3 gap-6">
                    <div class="card">
                        <div class="card-content">
                            <h3 class="mb-2">OSCE3</h3>
                            <span class="tag mb-3" style="background-color: rgba(245, 158, 11, 0.1); color: rgb(245, 158, 11);">In Progress</span>
                            <p class="text-muted">Advanced Windows Exploitation</p>
                        </div>
                    </div>
                    
                    <div class="card">
                        <div class="card-content">
                            <h3 class="mb-2">eLearnSecurity</h3>
                            <span class="tag mb-3" style="background-color: rgba(245, 158, 11, 0.1); color: rgb(245, 158, 11);">Multiple Tracks</span>
                            <p class="text-muted">Web App & Mobile Security</p>
                        </div>
                    </div>
                    
                    <div class="card">
                        <div class="card-content">
                            <h3 class="mb-2">Android Security</h3>
                            <span class="tag mb-3" style="background-color: rgba(16, 185, 129, 0.1); color: rgb(16, 185, 129);">Self-Taught</span>
                            <p class="text-muted">Frida, Static Analysis, Reverse Engineering</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog" class="section page-content">
        <div class="container max-w-5xl">
            <div class="mb-16 fade-in">
                <h1 class="mb-6">Security Research & Writeups</h1>
                <p class="text-xl text-muted">
                    Sharing knowledge through detailed vulnerability research and tool development insights
                </p>
            </div>

            <div class="grid grid-2 gap-8">
                <div class="card fade-in delay-100">
                    <img src="https://placeholder.com/800x400" alt="Android SSL Pinning" class="card-image">
                    <div class="card-content">
                        <div class="blog-card-header">
                            <span class="blog-date">Dec 15, 2024</span>
                            <div class="blog-tags">
                                <span class="tag">Android</span>
                                <span class="tag">Frida</span>
                            </div>
                        </div>
                        <h2 class="mb-3">Advanced Android SSL Pinning Bypass with Frida</h2>
                        <p class="text-muted mb-4">Deep dive into bypassing modern SSL pinning implementations in Android applications using custom Frida scripts and runtime manipulation techniques...</p>
                        <a href="#" class="text-primary font-medium">Read More →</a>
                    </div>
                </div>
                
                <div class="card fade-in delay-200">
                    <img src="https://placeholder.com/800x400" alt="IDOR Detection" class="card-image">
                    <div class="card-content">
                        <div class="blog-card-header">
                            <span class="blog-date">Nov 28, 2024</span>
                            <div class="blog-tags">
                                <span class="tag">Bug Bounty</span>
                                <span class="tag">Web</span>
                            </div>
                        </div>
                        <h2 class="mb-3">Automating IDOR Detection in Large Applications</h2>
                        <p class="text-muted mb-4">How I built a custom tool to automatically detect Insecure Direct Object References across thousands of endpoints, leading to multiple critical findings...</p>
                        <a href="#" class="text-primary font-medium">Read More →</a>
                    </div>
                </div>
                
                <div class="card fade-in delay-300">
                    <img src="https://placeholder.com/800x400" alt="BADGPT" class="card-image">
                    <div class="card-content">
                        <div class="blog-card-header">
                            <span class="blog-date">Oct 12, 2024</span>
                            <div class="blog-tags">
                                <span class="tag">Tools</span>
                                <span class="tag">Go</span>
                            </div>
                        </div>
                        <h2 class="mb-3">Building BADGPT: AI-Powered Security Testing</h2>
                        <p class="text-muted mb-4">The story behind creating BADGPT, a tool that leverages AI to enhance bug bounty workflows and automate vulnerability discovery processes...</p>
                        <a href="#" class="text-primary font-medium">Read More →</a>
                    </div>
                </div>
                
                <div class="card fade-in delay-400">
                    <img src="https://placeholder.com/800x400" alt="Android APK Analysis" class="card-image">
                    <div class="card-content">
                        <div class="blog-card-header">
                            <span class="blog-date">Sep 5, 2024</span>
                            <div class="blog-tags">
                                <span class="tag">Mobile</span>
                                <span class="tag">Research</span>
                            </div>
                        </div>
                        <h2 class="mb-3">Static Analysis of Android APKs at Scale</h2>
                        <p class="text-muted mb-4">Techniques and tools for performing efficient static analysis on thousands of Android applications to identify common vulnerability patterns...</p>
                        <a href="#" class="text-primary font-medium">Read More →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section page-content">
        <div class="container max-w-5xl">
            <div class="mb-12 fade-in">
                <h1 class="mb-6">Security Tools & Projects</h1>
                <p class="text-xl text-muted">
                    Open-source tools built to enhance security research and bug bounty workflows
                </p>
            </div>

            <div class="tab-container mb-12 fade-in delay-100">
                <button class="tab-btn active" data-category="all">All Projects</button>
                <button class="tab-btn" data-category="automation">Automation</button>
                <button class="tab-btn" data-category="mobile">Mobile Security</button>
                <button class="tab-btn" data-category="web">Web Security</button>
            </div>

            <div class="grid grid-2 gap-8">
                <div class="card project-card fade-in delay-200" data-category="automation" style="border-color: rgba(61, 178, 255, 0.2); background-color: rgba(61, 178, 255, 0.05);">
                    <div class="card-content">
                        <div class="project-header">
                            <h2>BADGPT</h2>
                            <span class="project-status">Featured</span>
                        </div>
                        
                        <p class="text-muted mb-6">
                            AI-powered security testing tool that leverages GPT models to enhance bug bounty workflows, 
                            automate vulnerability discovery, and generate intelligent test cases.
                        </p>
                        
                        <div class="project-features">
                            <h4 class="mb-3">Key Features:</h4>
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
                        
                        <a href="https://github.com/NeM0x00" class="btn btn-primary w-full" target="_blank">
                            <svg class="icon icon-sm mr-2" viewBox="0 0 24 24">
                                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                            </svg>
                            View on GitHub
                        </a>
                    </div>
                </div>
                
                <div class="card project-card fade-in delay-300" data-category="mobile">
                    <div class="card-content">
                        <div class="project-header">
                            <h2>Frida Android Scanner</h2>
                            <span class="project-status">Active</span>
                        </div>
                        
                        <p class="text-muted mb-6">
                            Comprehensive Android security scanner built with Frida for dynamic analysis, 
                            runtime manipulation, and vulnerability detection in mobile applications.
                        </p>
                        
                        <div class="project-features">
                            <h4 class="mb-3">Key Features:</h4>
                            <ul>
                                <li>SSL pinning bypass automation</li>
                                <li>Runtime method hooking</li>
                                <li>Certificate validation bypass</li>
                                <li>Custom payload injection</li>
                            </ul>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">Frida</span>
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Android</span>
                        </div>
                        
                        <a href="https://github.com/NeM0x00" class="btn btn-primary w-full" target="_blank">
                            <svg class="icon icon-sm mr-2" viewBox="0 0 24 24">
                                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                            </svg>
                            View on GitHub
                        </a>
                    </div>
                </div>
                
                <div class="card project-card fade-in delay-400" data-category="web">
                    <div class="card-content">
                        <div class="project-header">
                            <h2>IDOR Hunter</h2>
                            <span class="project-status">Beta</span>
                        </div>
                        
                        <p class="text-muted mb-6">
                            Automated tool for detecting Insecure Direct Object References (IDOR) vulnerabilities 
                            across web applications with intelligent parameter fuzzing.
                        </p>
                        
                        <div class="project-features">
                            <h4 class="mb-3">Key Features:</h4>
                            <ul>
                                <li>Automated endpoint discovery</li>
                                <li>Parameter manipulation testing</li>
                                <li>Session management bypass</li>
                                <li>Detailed vulnerability reporting</li>
                            </ul>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Requests</span>
                            <span class="tech-tag">Threading</span>
                        </div>
                        
                        <a href="https://github.com/NeM0x00" class="btn btn-primary w-full" target="_blank">
                            <svg class="icon icon-sm mr-2" viewBox="0 0 24 24">
                                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                            </svg>
                            View on GitHub
                        </a>
                    </div>
                </div>
                
                <div class="card project-card fade-in delay-400" data-category="automation">
                    <div class="card-content">
                        <div class="project-header">
                            <h2>Recon Automation Suite</h2>
                            <span class="project-status">Maintained</span>
                        </div>
                        
                        <p class="text-muted mb-6">
                            Complete reconnaissance automation framework for bug bounty hunters, 
                            integrating multiple tools and providing comprehensive target analysis.
                        </p>
                        
                        <div class="project-features">
                            <h4 class="mb-3">Key Features:</h4>
                            <ul>
                                <li>Subdomain enumeration</li>
                                <li>Port scanning and service detection</li>
                                <li>Technology stack identification</li>
                                <li>Automated report generation</li>
                            </ul>
                        </div>
                        
                        <div class="project-tech">
                            <span class="tech-tag">Bash</span>
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Docker</span>
                        </div>
                        
                        <a href="https://github.com/NeM0x00" class="btn btn-primary w-full" target="_blank">
                            <svg class="icon icon-sm mr-2" viewBox="0 0 24 24">
                                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                            </svg>
                            View on GitHub
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CV Section -->
    <section id="cv" class="section page-content">
        <div class="container max-w-4xl">
            <div class="mb-16 fade-in">
                <h1 class="mb-6">Curriculum Vitae</h1>
                <p class="text-xl text-muted">
                    Cybersecurity researcher and bug bounty hunter with expertise in Android security, web application penetration 
                    testing, and security automation. Proven track record of responsible disclosure with major technology 
                    companies.
                </p>
            </div>

            <div class="space-y-12">
                <section class="fade-in delay-100">
                    <h2 class="mb-8">Professional Experience</h2>
                    <div class="card" style="border-left-width: 4px; border-left-color: var(--primary);">
                        <div class="card-content">
                            <div class="flex justify-between mb-4">
                                <h3>Independent Security Researcher</h3>
                                <span class="text-primary font-medium">2020 - Present</span>
                            </div>
                            <p class="text-muted italic mb-4">Freelance Bug Bounty Hunter</p>
                            <ul class="space-y-2">
                                <li class="text-muted flex items-start">
                                    <span class="text-primary mr-3">•</span>
                                    Conducted security assessments for web and mobile applications
                                </li>
                                <li class="text-muted flex items-start">
                                    <span class="text-primary mr-3">•</span>
                                    Discovered and responsibly disclosed vulnerabilities to major companies
                                </li>
                                <li class="text-muted flex items-start">
                                    <span class="text-primary mr-3">•</span>
                                    Developed custom tools for automation and vulnerability discovery
                                </li>
                                <li class="text-muted flex items-start">
                                    <span class="text-primary mr-3">•</span>
                                    Maintained active participation in bug bounty programs
                                </li>
                            </ul>
                        </div>
                    </div>
                </section>

                <section class="fade-in delay-200">
                    <h2 class="mb-8">Technical Skills</h2>
                    <div class="grid grid-4 gap-6">
                        <div class="card">
                            <div class="card-content">
                                <h4 class="text-primary mb-4">Security Testing</h4>
                                <ul class="space-y-2">
                                    <li class="text-muted text-sm">Web Application Security</li>
                                    <li class="text-muted text-sm">Mobile Application Security</li>
                                    <li class="text-muted text-sm">Android Reverse Engineering</li>
                                    <li class="text-muted text-sm">Static & Dynamic Analysis</li>
                                </ul>
                            </div>
                        </div>
                        
                        <div class="card">
                            <div class="card-content">
                                <h4 class="text-primary mb-4">Tools & Frameworks</h4>
                                <ul class="space-y-2">
                                    <li class="text-muted text-sm">Frida & Dynamic Instrumentation</li>
                                    <li class="text-muted text-sm">Burp Suite Professional</li>
                                    <li class="text-muted text-sm">OWASP Testing Framework</li>
                                    <li class="text-muted text-sm">Custom Tool Development</li>
                                </ul>
                            </div>
                        </div>
                        
                        <div class="card">
                            <div class="card-content">
                                <h4 class="text-primary mb-4">Programming Languages</h4>
                                <ul class="space-y-2">
                                    <li class="text-muted text-sm">Go (Golang)</li>
                                    <li class="text-muted text-sm">Python</li>
                                    <li class="text-muted text-sm">JavaScript</li>
                                    <li class="text-muted text-sm">Bash Scripting</li>
                                </ul>
                            </div>
                        </div>
                        
                        <div class="card">
                            <div class="card-content">
                                <h4 class="text-primary mb-4">Specializations</h4>
                                <ul class="space-y-2">
                                    <li class="text-muted text-sm">Android Security Research</li>
                                    <li class="text-muted text-sm">Automation & Tooling</li>
                                    <li class="text-muted text-sm">Vulnerability Research</li>
                                    <li class="text-muted text-sm">Responsible Disclosure</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </section>

                <section class="fade-in delay-300">
                    <h2 class="mb-8">Recognition & Acknowledgments</h2>
                    <div class="grid grid-4 gap-6">
                        <div class="card text-center">
                            <div class="card-content">
                                <h4 class="text-primary mb-3">Google</h4>
                                <p class="text-muted text-sm">Security vulnerability disclosure acknowledgment</p>
                            </div>
                        </div>
                        
                        <div class="card text-center">
                            <div class="card-content">
                                <h4 class="text-primary mb-3">Unity Technologies</h4>
                                <p class="text-muted text-sm">Platform security research recognition</p>
                            </div>
                        </div>
                        
                        <div class="card text-center">
                            <div class="card-content">
                                <h4 class="text-primary mb-3">Swisscom</h4>
                                <p class="text-muted text-sm">Bug bounty program participation and award</p>
                            </div>
                        </div>
                        
                        <div class="card text-center">
                            <div class="card-content">
                                <h4 class="text-primary mb-3">Estonia Government</h4>
                                <p class="text-muted text-sm">Critical infrastructure security research</p>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section page-content">
        <div class="container max-w-4xl">
            <div class="mb-16 fade-in">
                <h1 class="mb-6">Get In Touch</h1>
                <p class="text-xl text-muted">
                    Interested in collaboration, security research, or just want to connect? 
                    Feel free to reach out through any of the platforms below.
                </p>
            </div>

            <div class="grid grid-2 gap-12">
                <div class="fade-in delay-100">
                    <h2 class="mb-6">Let's Connect</h2>
                    <p class="text-muted mb-8">
                        I'm always open to discussing security research, bug bounty collaboration, 
                        tool development, or sharing knowledge with the cybersecurity community.
                    </p>
                    
                    <div class="space-y-4">
                        <a href="https://github.com/NeM0x00" class="social-link" target="_blank">
                            <div class="social-icon">
                                <svg viewBox="0 0 24 24" fill="currentColor">
                                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                                </svg>
                            </div>
                            <div>
                                <h3 class="font-medium">GitHub</h3>
                                <p class="text-muted">github.com/NeM0x00</p>
                            </div>
                            <svg class="icon ml-auto" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                                <polyline points="15 3 21 3 21 9"></polyline>
                                <line x1="10" y1="14" x2="21" y2="3"></line>
                            </svg>
                        </a>
                        
                        <a href="https://linkedin.com/in/yousef-elsheikh-b1573a1b0/" class="social-link" target="_blank">
                            <div class="social-icon" style="color: #0077b5;">
                                <svg viewBox="0 0 24 24" fill="currentColor">
                                    <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.
\`\`\`

The file is too large for a single response. Let me provide you with a more compact version that will work well for GitHub Pages:

<CodeProject id="Youssef Elsheikh Portfolio">
