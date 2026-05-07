<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Marica Rosas — Graphic Designer</title>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #0a0a0a;
            --surface: #141414;
            --surface-light: #1e1e1e;
            --text: #f5f5f5;
            --text-muted: #888888;
            --accent: #ff6b35;
            --accent-hover: #ff8555;
            --border: #2a2a2a;
            --gradient-1: #ff6b35;
            --gradient-2: #f7931e;
            --gradient-3: #ffd93d;
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
            font-family: 'Inter', sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Space Grotesk', sans-serif;
            font-weight: 600;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 10, 10, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
        }

        .logo {
            font-family: 'Space Grotesk', sans-serif;
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--gradient-1), var(--gradient-2));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--text);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
        }

        .menu-toggle span {
            width: 25px;
            height: 2px;
            background: var(--text);
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(ellipse at 20% 50%, rgba(255, 107, 53, 0.08) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 20%, rgba(247, 147, 30, 0.06) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 80%, rgba(255, 217, 61, 0.04) 0%, transparent 50%);
            pointer-events: none;
        }

        .hero-content {
            max-width: 900px;
            position: relative;
            z-index: 1;
        }

        .hero-tag {
            display: inline-block;
            padding: 0.5rem 1rem;
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 100px;
            font-size: 0.85rem;
            color: var(--accent);
            margin-bottom: 2rem;
            letter-spacing: 0.05em;
        }

        .hero h1 {
            font-size: clamp(3rem, 7vw, 5.5rem);
            line-height: 1.05;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .hero h1 .highlight {
            background: linear-gradient(135deg, var(--gradient-1), var(--gradient-2), var(--gradient-3));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--text-muted);
            max-width: 550px;
            margin-bottom: 2.5rem;
            line-height: 1.7;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border-radius: 100px;
            font-size: 0.95rem;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s;
            cursor: pointer;
            border: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--gradient-1), var(--gradient-2));
            color: white;
            box-shadow: 0 10px 40px rgba(255, 107, 53, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 50px rgba(255, 107, 53, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text);
            border: 1px solid var(--border);
        }

        .btn-secondary:hover {
            background: var(--surface);
            border-color: var(--text-muted);
        }

        .hero-stats {
            display: flex;
            gap: 3rem;
            margin-top: 4rem;
            padding-top: 2rem;
            border-top: 1px solid var(--border);
        }

        .stat h3 {
            font-size: 2rem;
            color: var(--text);
            margin-bottom: 0.25rem;
        }

        .stat p {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin: 0;
        }

        /* Section Styles */
        section {
            padding: 8rem 5%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-header h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 1rem;
        }

        .section-header p {
            color: var(--text-muted);
            max-width: 500px;
            margin: 0 auto;
        }

        /* Work/Portfolio Section */
        .work-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .work-card {
            background: var(--surface);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: all 0.4s;
            cursor: pointer;
            position: relative;
        }

        .work-card:hover {
            transform: translateY(-8px);
            border-color: var(--accent);
            box-shadow: 0 20px 60px rgba(255, 107, 53, 0.1);
        }

        .work-image {
            width: 100%;
            height: 280px;
            background: var(--surface-light);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .work-image .placeholder {
            font-size: 4rem;
            opacity: 0.3;
        }

        .work-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(10,10,10,0.9), transparent);
            display: flex;
            align-items: flex-end;
            padding: 1.5rem;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .work-card:hover .work-overlay {
            opacity: 1;
        }

        .work-overlay span {
            background: var(--accent);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 100px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .work-info {
            padding: 1.5rem;
        }

        .work-info h3 {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }

        .work-info p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        .work-tags {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
            flex-wrap: wrap;
        }

        .work-tags span {
            padding: 0.25rem 0.75rem;
            background: var(--surface-light);
            border-radius: 100px;
            font-size: 0.75rem;
            color: var(--text-muted);
            border: 1px solid var(--border);
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 2.5rem;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--gradient-1), var(--gradient-2));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s;
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-card:hover {
            border-color: var(--accent);
            transform: translateY(-4px);
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: var(--surface-light);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.75rem;
            margin-bottom: 1.5rem;
            border: 1px solid var(--border);
        }

        .service-card h3 {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }

        .service-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        /* About Section */
        .about-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            max-width: 1200px;
            margin: 0 auto;
            align-items: center;
        }

        .about-image {
            position: relative;
        }

        .about-image .img-frame {
            width: 100%;
            aspect-ratio: 4/5;
            background: var(--surface);
            border-radius: 24px;
            border: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;
        }

        .about-image .img-frame::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(255,107,53,0.1), transparent);
        }

        .about-image .img-placeholder {
            font-size: 6rem;
            opacity: 0.2;
        }

        .about-image .experience-badge {
            position: absolute;
            bottom: -20px;
            right: -20px;
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 1.5rem 2rem;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }

        .experience-badge h4 {
            font-size: 2.5rem;
            background: linear-gradient(135deg, var(--gradient-1), var(--gradient-2));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .experience-badge p {
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-top: 0.25rem;
        }

        .about-content h2 {
            font-size: clamp(2rem, 3vw, 2.5rem);
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }

        .about-content p {
            color: var(--text-muted);
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
            margin-top: 2rem;
        }

        .skill-tag {
            padding: 0.6rem 1.2rem;
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 100px;
            font-size: 0.85rem;
            color: var(--text);
            transition: all 0.3s;
        }

        .skill-tag:hover {
            border-color: var(--accent);
            color: var(--accent);
        }

        /* Testimonials */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .testimonial-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 20px;
            padding: 2.5rem;
            position: relative;
        }

        .testimonial-card::before {
            content: '"';
            font-family: 'Space Grotesk', sans-serif;
            font-size: 6rem;
            color: var(--accent);
            opacity: 0.2;
            position: absolute;
            top: 10px;
            left: 20px;
            line-height: 1;
        }

        .testimonial-text {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 2rem;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--surface-light);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            border: 2px solid var(--border);
        }

        .author-info h4 {
            font-size: 1rem;
            margin-bottom: 0.2rem;
        }

        .author-info p {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        /* Contact Section */
        .contact-container {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-container h2 {
            font-size: clamp(2rem, 4vw, 3rem);
            margin-bottom: 1rem;
        }

        .contact-container > p {
            color: var(--text-muted);
            margin-bottom: 3rem;
            font-size: 1.1rem;
        }

        .contact-form {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 24px;
            padding: 3rem;
            text-align: left;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--text-muted);
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 1rem 1.25rem;
            background: var(--bg);
            border: 1px solid var(--border);
            border-radius: 12px;
            color: var(--text);
            font-family: 'Inter', sans-serif;
            font-size: 0.95rem;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(255, 107, 53, 0.1);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 3rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        .contact-item span:first-child {
            font-size: 1.25rem;
        }

        /* Footer */
        footer {
            background: var(--surface);
            border-top: 1px solid var(--border);
            padding: 3rem 5%;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .social-links a {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--surface-light);
            border: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-muted);
            text-decoration: none;
            font-size: 1.25rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--accent);
            color: white;
            border-color: var(--accent);
            transform: translateY(-3px);
        }

        .footer-text {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s, transform 0.6s;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--bg);
                flex-direction: column;
                padding: 2rem;
                gap: 1.5rem;
                border-bottom: 1px solid var(--border);
            }

            .nav-links.active {
                display: flex;
            }

            .menu-toggle {
                display: flex;
            }

            .hero-stats {
                flex-direction: column;
                gap: 1.5rem;
            }

            .about-container {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .contact-info {
                flex-direction: column;
                gap: 1rem;
            }

            section {
                padding: 5rem 5%;
            }

            .work-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <div class="logo">Marica Rosas</div>
        <ul class="nav-links" id="navLinks">
            <li><a href="#work">Work</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#testimonials">Testimonials</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="menu-toggle" id="menuToggle">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <div class="hero-tag">✦ Available for freelance</div>
            <h1>Crafting <span class="highlight">visual stories</span> that captivate & convert</h1>
            <p>I'm Alex Morgan, a multidisciplinary graphic designer specializing in brand identity, digital experiences, and motion design. I help brands stand out in a crowded world.</p>
            <div class="hero-buttons">
                <a href="#work" class="btn btn-primary">View My Work →</a>
                <a href="#contact" class="btn btn-secondary">Let's Talk</a>
            </div>
            <div class="hero-stats">
                <div class="stat">
                    <h3>8+</h3>
                    <p>Years Experience</p>
                </div>
                <div class="stat">
                    <h3>150+</h3>
                    <p>Projects Completed</p>
                </div>
                <div class="stat">
                    <h3>50+</h3>
                    <p>Happy Clients</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Work/Portfolio Section -->
    <section id="work">
        <div class="section-header fade-in">
            <h2>Selected <span style="color: var(--accent);">Works</span></h2>
            <p>A curated collection of projects that showcase my passion for design and attention to detail.</p>
        </div>
        <div class="work-grid">
            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">🎨</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>Lumina Brand Identity</h3>
                    <p>Complete brand overhaul for a sustainable lighting company, including logo, packaging, and digital assets.</p>
                    <div class="work-tags">
                        <span>Branding</span>
                        <span>Packaging</span>
                        <span>Identity</span>
                    </div>
                </div>
            </div>

            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">📱</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>Nova Finance App</h3>
                    <p>UI/UX design for a modern fintech mobile application focused on investment tracking and portfolio management.</p>
                    <div class="work-tags">
                        <span>UI/UX</span>
                        <span>Mobile</span>
                        <span>Fintech</span>
                    </div>
                </div>
            </div>

            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">🏢</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>Vertex Architecture</h3>
                    <p>Editorial design and visual system for an award-winning architecture firm's portfolio and publication series.</p>
                    <div class="work-tags">
                        <span>Editorial</span>
                        <span>Print</span>
                        <span>Layout</span>
                    </div>
                </div>
            </div>

            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">🎬</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>Motion Reel 2024</h3>
                    <p>A collection of motion graphics and animated brand stories created for various clients across industries.</p>
                    <div class="work-tags">
                        <span>Motion</span>
                        <span>Animation</span>
                        <span>Video</span>
                    </div>
                </div>
            </div>

            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">🌿</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>GreenLeaf Organics</h3>
                    <p>E-commerce website design and brand collateral for an organic food delivery startup.</p>
                    <div class="work-tags">
                        <span>Web Design</span>
                        <span>E-commerce</span>
                        <span>Branding</span>
                    </div>
                </div>
            </div>

            <div class="work-card fade-in">
                <div class="work-image">
                    <div class="placeholder">🎵</div>
                    <div class="work-overlay"><span>View Project →</span></div>
                </div>
                <div class="work-info">
                    <h3>Sonic Waves Festival</h3>
                    <p>Complete visual campaign for a music festival including posters, social media, and stage visuals.</p>
                    <div class="work-tags">
                        <span>Campaign</span>
                        <span>Social Media</span>
                        <span>Events</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" style="background: var(--surface);">
        <div class="section-header fade-in">
            <h2>What I <span style="color: var(--accent);">Do</span></h2>
            <p>From concept to completion, I offer a full range of design services tailored to your needs.</p>
        </div>
        <div class="services-grid">
            <div class="service-card fade-in">
                <div class="service-icon">🎯</div>
                <h3>Brand Identity</h3>
                <p>Strategic brand development including logo design, color systems, typography, and comprehensive brand guidelines that tell your unique story.</p>
            </div>
            <div class="service-card fade-in">
                <div class="service-icon">💻</div>
                <h3>UI/UX Design</h3>
                <p>User-centered digital experiences for web and mobile. Wireframes, prototypes, and pixel-perfect interfaces that users love.</p>
            </div>
            <div class="service-card fade-in">
                <div class="service-icon">📐</div>
                <h3>Print & Editorial</h3>
                <p>Beautiful print collateral, magazines, books, and packaging design that makes a lasting impression in the physical world.</p>
            </div>
            <div class="service-card fade-in">
                <div class="service-icon">✨</div>
                <h3>Motion Design</h3>
                <p>Dynamic animations, explainer videos, and motion graphics that bring your brand to life and engage your audience.</p>
            </div>
            <div class="service-card fade-in">
                <div class="service-icon">📱</div>
                <h3>Social Media</h3>
                <p>Eye-catching content calendars, templates, and campaigns designed to grow your presence and drive engagement.</p>
            </div>
            <div class="service-card fade-in">
                <div class="service-icon">🎨</div>
                <h3>Art Direction</h3>
                <p>Creative vision and direction for photoshoots, campaigns, and visual storytelling that elevates your brand.</p>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="about-container">
            <div class="about-image fade-in">
                <div class="img-frame">
                    <div class="img-placeholder">👤</div>
                </div>
                <div class="experience-badge">
                    <h4>8+</h4>
                    <p>Years of<br>Experience</p>
                </div>
            </div>
            <div class="about-content fade-in">
                <h2>Design is not just what it looks like — it's how it <span style="color: var(--accent);">works</span></h2>
                <p>Hello! I'm Alex Morgan, a passionate graphic designer based in San Francisco. With over 8 years of experience in the creative industry, I've had the privilege of working with startups, agencies, and Fortune 500 companies.</p>
                <p>My approach combines strategic thinking with creative execution. I believe great design should solve problems, tell stories, and create meaningful connections between brands and their audiences.</p>
                <p>When I'm not designing, you'll find me exploring photography, experimenting with generative art, or hiking the beautiful trails of Northern California.</p>
                <div class="skills">
                    <span class="skill-tag">Adobe Creative Suite</span>
                    <span class="skill-tag">Figma</span>
                    <span class="skill-tag">Sketch</span>
                    <span class="skill-tag">After Effects</span>
                    <span class="skill-tag">Blender</span>
                    <span class="skill-tag">Webflow</span>
                    <span class="skill-tag">HTML/CSS</span>
                    <span class="skill-tag">Typography</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" style="background: var(--surface);">
        <div class="section-header fade-in">
            <h2>Client <span style="color: var(--accent);">Love</span></h2>
            <p>Don't just take my word for it — here's what my clients have to say.</p>
        </div>
        <div class="testimonials-grid">
            <div class="testimonial-card fade-in">
                <p class="testimonial-text">Alex transformed our brand from forgettable to unforgettable. The attention to detail and strategic thinking behind every design decision was remarkable. Our conversion rate increased by 40% after the rebrand.</p>
                <div class="testimonial-author">
                    <div class="author-avatar">👩‍💼</div>
                    <div class="author-info">
                        <h4>Sarah Chen</h4>
                        <p>CEO, Lumina Tech</p>
                    </div>
                </div>
            </div>
            <div class="testimonial-card fade-in">
                <p class="testimonial-text">Working with Alex was an absolute pleasure. They understood our vision immediately and delivered designs that exceeded our expectations. The motion graphics they created for our product launch were stunning.</p>
                <div class="testimonial-author">
                    <div class="author-avatar">👨‍💼</div>
                    <div class="author-info">
                        <h4>Marcus Johnson</h4>
                        <p>Marketing Director, Nova Finance</p>
                    </div>
                </div>
            </div>
            <div class="testimonial-card fade-in">
                <p class="testimonial-text">The editorial design Alex created for our architecture portfolio received numerous awards. Their ability to balance aesthetics with functionality is truly world-class. Highly recommended!</p>
                <div class="testimonial-author">
                    <div class="author-avatar">👩‍🎨</div>
                    <div class="author-info">
                        <h4>Elena Rodriguez</h4>
                        <p>Principal, Vertex Architecture</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="contact-container">
            <div class="section-header fade-in">
                <h2>Let's Create <span style="color: var(--accent);">Together</span></h2>
                <p>Have a project in mind? I'd love to hear about it. Let's discuss how we can bring your vision to life.</p>
            </div>
            <form class="contact-form fade-in">
                <div class="form-row">
                    <div class="form-group">
                        <label for="name">Your Name</label>
                        <input type="text" id="name" placeholder="John Doe" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" placeholder="john@example.com" required>
                    </div>
                </div>
                <div class="form-group">
                    <label for="project">Project Type</label>
                    <select id="project">
                        <option value="">Select a service...</option>
                        <option value="branding">Brand Identity</option>
                        <option value="uiux">UI/UX Design</option>
                        <option value="print">Print & Editorial</option>
                        <option value="motion">Motion Design</option>
                        <option value="social">Social Media</option>
                        <option value="other">Something Else</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="message">Tell me about your project</label>
                    <textarea id="message" placeholder="I'm looking for a designer to help with..."></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%; justify-content: center;">Send Message →</button>
            </form>
            <div class="contact-info">
                <div class="contact-item">
                    <span>📧</span>
                    <span>hello@alexmorgan.design</span>
                </div>
                <div class="contact-item">
                    <span>📱</span>
                    <span>+1 (555) 123-4567</span>
                </div>
                <div class="contact-item">
                    <span>📍</span>
                    <span>San Francisco, CA</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="social-links">
                <a href="#" title="Dribbble">🏀</a>
                <a href="#" title="Behance">🎨</a>
                <a href="#" title="Instagram">📷</a>
                <a href="#" title="LinkedIn">💼</a>
                <a href="#" title="Twitter">🐦</a>
            </div>
            <p class="footer-text">© 2024 Alex Morgan. Crafted with passion & pixels.</p>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        const menuToggle = document.getElementById('menuToggle');
        const navLinks = document.getElementById('navLinks');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Smooth scroll for navigation
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

        // Form submission handler
        document.querySelector('.contact-form').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thanks for reaching out! This is a template — connect your backend to handle real submissions.');
        });

        // Navbar background on scroll
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 50) {
                nav.style.background = 'rgba(10, 10, 10, 0.95)';
            } else {
                nav.style.background = 'rgba(10, 10, 10, 0.8)';
            }
        });
    </script>

</body>
</html>
