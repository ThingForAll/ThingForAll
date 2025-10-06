<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ThingForAll - Premium Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes glow {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 215, 0, 0.5); }
            50% { box-shadow: 0 0 40px rgba(255, 215, 0, 0.8), 0 0 60px rgba(255, 215, 0, 0.6); }
        }

        @keyframes shimmer {
            0% { background-position: -1000px 0; }
            100% { background-position: 1000px 0; }
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(-45deg, #0a0a0a, #1a1a2e, #16213e, #0f3460);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: float 3s ease-in-out infinite;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 10;
        }

        .header {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, rgba(255,215,0,0.1) 0%, rgba(218,165,32,0.1) 100%);
            border-radius: 30px;
            border: 2px solid rgba(255,215,0,0.3);
            margin-bottom: 50px;
            animation: glow 3s ease-in-out infinite, slideIn 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,215,0,0.1), transparent);
            animation: rotate 4s linear infinite;
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .logo {
            font-size: 72px;
            font-weight: bold;
            background: linear-gradient(135deg, #FFD700, #FFA500, #FFD700);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 3s ease infinite, pulse 2s ease-in-out infinite;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(255,215,0,0.5);
        }

        .tagline {
            font-size: 24px;
            color: #DAA520;
            margin-bottom: 10px;
            animation: slideIn 1.2s ease-out;
        }

        .price-tag {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(135deg, #FFD700, #FFA500);
            border-radius: 50px;
            font-size: 20px;
            font-weight: bold;
            color: #000;
            margin-top: 20px;
            animation: shimmer 3s infinite, pulse 2s ease-in-out infinite;
            background-size: 1000px 100%;
            position: relative;
            overflow: hidden;
        }

        .price-tag::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.6), transparent);
            animation: shimmer 2s infinite;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(255,215,0,0.05) 0%, rgba(218,165,32,0.05) 100%);
            padding: 40px;
            border-radius: 20px;
            border: 2px solid rgba(255,215,0,0.2);
            text-align: center;
            animation: float 3s ease-in-out infinite, slideIn 1.4s ease-out;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: rgba(255,215,0,0.6);
            box-shadow: 0 20px 60px rgba(255,215,0,0.3);
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,215,0,0.1) 0%, transparent 70%);
            animation: rotate 8s linear infinite;
        }

        .stat-value {
            font-size: 48px;
            font-weight: bold;
            color: #FFD700;
            margin-bottom: 10px;
            position: relative;
        }

        .stat-label {
            font-size: 18px;
            color: #DAA520;
            position: relative;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(255,215,0,0.08) 0%, rgba(218,165,32,0.08) 100%);
            padding: 30px;
            border-radius: 20px;
            border: 2px solid rgba(255,215,0,0.2);
            animation: slideIn 1.6s ease-out;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card:hover {
            transform: translateY(-15px) scale(1.03);
            border-color: rgba(255,215,0,0.6);
            box-shadow: 0 25px 70px rgba(255,215,0,0.4);
        }

        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,215,0,0.1), transparent);
            transition: left 0.5s ease;
        }

        .project-card:hover::after {
            left: 100%;
        }

        .project-icon {
            font-size: 48px;
            margin-bottom: 20px;
            animation: pulse 2s ease-in-out infinite;
        }

        .project-title {
            font-size: 24px;
            font-weight: bold;
            color: #FFD700;
            margin-bottom: 15px;
        }

        .project-desc {
            color: #ccc;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tech-badge {
            padding: 8px 16px;
            background: linear-gradient(135deg, rgba(255,215,0,0.2), rgba(218,165,32,0.2));
            border-radius: 20px;
            font-size: 14px;
            border: 1px solid rgba(255,215,0,0.3);
            animation: pulse 3s ease-in-out infinite;
        }

        .skills-section {
            background: linear-gradient(135deg, rgba(255,215,0,0.05) 0%, rgba(218,165,32,0.05) 100%);
            padding: 50px;
            border-radius: 30px;
            border: 2px solid rgba(255,215,0,0.2);
            margin-bottom: 50px;
            animation: slideIn 1.8s ease-out;
        }

        .skills-title {
            text-align: center;
            font-size: 36px;
            color: #FFD700;
            margin-bottom: 40px;
            animation: pulse 2s ease-in-out infinite;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill-item {
            text-align: center;
            padding: 25px;
            background: linear-gradient(135deg, rgba(255,215,0,0.1), rgba(218,165,32,0.1));
            border-radius: 15px;
            border: 1px solid rgba(255,215,0,0.2);
            transition: all 0.3s ease;
            animation: float 4s ease-in-out infinite;
        }

        .skill-item:hover {
            transform: scale(1.15) rotate(5deg);
            border-color: rgba(255,215,0,0.8);
            box-shadow: 0 15px 40px rgba(255,215,0,0.4);
        }

        .skill-icon {
            font-size: 40px;
            margin-bottom: 10px;
        }

        .footer {
            text-align: center;
            padding: 40px;
            background: linear-gradient(135deg, rgba(255,215,0,0.05) 0%, rgba(218,165,32,0.05) 100%);
            border-radius: 20px;
            border: 2px solid rgba(255,215,0,0.2);
            animation: glow 3s ease-in-out infinite;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
        }

        .social-link {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #FFD700, #FFA500);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            transition: all 0.3s ease;
            animation: pulse 2s ease-in-out infinite;
            cursor: pointer;
        }

        .social-link:hover {
            transform: scale(1.3) rotate(360deg);
            box-shadow: 0 10px 30px rgba(255,215,0,0.6);
        }

        @media (max-width: 768px) {
            .logo { font-size: 48px; }
            .tagline { font-size: 18px; }
            .stat-value { font-size: 36px; }
            .projects, .stats-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container">
        <div class="header">
            <div class="header-content">
                <div class="logo">⚡ ThingForAll</div>
                <div class="tagline">Premium Full-Stack Developer & Tech Innovator</div>
                <p style="color: #DAA520; font-size: 18px; margin-top: 15px;">Crafting Digital Excellence Since 2020</p>
                <div class="price-tag">🏆 Trophy Premium Collection 🏆</div>
            </div>
        </div>

        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-value">150+</div>
                <div class="stat-label">Projects Completed</div>
            </div>
            <div class="stat-card" style="animation-delay: 0.2s">
                <div class="stat-value">500K+</div>
                <div class="stat-label">Lines of Code</div>
            </div>
            <div class="stat-card" style="animation-delay: 0.4s">
                <div class="stat-value">50+</div>
                <div class="stat-label">Happy Clients</div>
            </div>
            <div class="stat-card" style="animation-delay: 0.6s">
                <div class="stat-value">24/7</div>
                <div class="stat-label">Available Support</div>
            </div>
        </div>

        <div class="projects">
            <div class="project-card">
                <div class="project-icon">🚀</div>
                <div class="project-title">Quantum Cloud Platform</div>
                <div class="project-desc">Next-generation cloud infrastructure with AI-powered auto-scaling and quantum encryption for enterprise solutions.</div>
                <div class="tech-stack">
                    <span class="tech-badge">React</span>
                    <span class="tech-badge">Node.js</span>
                    <span class="tech-badge">AWS</span>
                    <span class="tech-badge">Kubernetes</span>
                </div>
            </div>

            <div class="project-card" style="animation-delay: 0.2s">
                <div class="project-icon">🤖</div>
                <div class="project-title">AI Neural Network Suite</div>
                <div class="project-desc">Advanced machine learning platform with real-time data processing and predictive analytics capabilities.</div>
                <div class="tech-stack">
                    <span class="tech-badge">Python</span>
                    <span class="tech-badge">TensorFlow</span>
                    <span class="tech-badge">PyTorch</span>
                    <span class="tech-badge">Docker</span>
                </div>
            </div>

            <div class="project-card" style="animation-delay: 0.4s">
                <div class="project-icon">💳</div>
                <div class="project-title">Blockchain FinTech App</div>
                <div class="project-desc">Decentralized financial platform with smart contracts, crypto wallet integration, and P2P transactions.</div>
                <div class="tech-stack">
                    <span class="tech-badge">Solidity</span>
                    <span class="tech-badge">Web3.js</span>
                    <span class="tech-badge">Ethereum</span>
                    <span class="tech-badge">Next.js</span>
                </div>
            </div>
        </div>

        <div class="skills-section">
            <div class="skills-title">🏆 Premium Tech Stack</div>
            <div class="skills-grid">
                <div class="skill-item"><div class="skill-icon">⚛️</div>React</div>
                <div class="skill-item" style="animation-delay: 0.1s"><div class="skill-icon">📱</div>React Native</div>
                <div class="skill-item" style="animation-delay: 0.2s"><div class="skill-icon">🟢</div>Node.js</div>
                <div class="skill-item" style="animation-delay: 0.3s"><div class="skill-icon">🐍</div>Python</div>
                <div class="skill-item" style="animation-delay: 0.4s"><div class="skill-icon">☁️</div>AWS</div>
                <div class="skill-item" style="animation-delay: 0.5s"><div class="skill-icon">🔷</div>TypeScript</div>
                <div class="skill-item" style="animation-delay: 0.6s"><div class="skill-icon">🐳</div>Docker</div>
                <div class="skill-item" style="animation-delay: 0.7s"><div class="skill-icon">⚙️</div>Kubernetes</div>
            </div>
        </div>

        <div class="footer">
            <h2 style="color: #FFD700; margin-bottom: 15px; font-size: 32px;">Let's Build Something Amazing</h2>
            <p style="color: #DAA520; font-size: 18px;">Premium development services for visionary projects</p>
            <div class="social-links">
                <div class="social-link">💼</div>
                <div class="social-link">📧</div>
                <div class="social-link">🐙</div>
                <div class="social-link">🔗</div>
            </div>
            <p style="margin-top: 30px; color: #888;">© 2025 ThingForAll - Elite Digital Solutions</p>
        </div>
    </div>

    <script>
        // Generate random stars
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.animationDelay = Math.random() * 3 + 's';
            star.style.animationDuration = (Math.random() * 2 + 2) + 's';
            starsContainer.appendChild(star);
        }

        // Add parallax effect
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.stat-card, .project-card, .skill-item');
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            cards.forEach((card, index) => {
                const speed = (index + 1) * 0.5;
                const xMove = (x - 0.5) * speed * 10;
                const yMove = (y - 0.5) * speed * 10;
                card.style.transform = `translate(${xMove}px, ${yMove}px)`;
            });
        });

        // Smooth scroll animation
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.project-card, .stat-card').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>