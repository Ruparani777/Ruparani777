<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stunning README Preview</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0a0e27 0%, #1a1b3d 50%, #0a0e27 100%);
            font-family: 'JetBrains Mono', 'Courier New', monospace;
            color: #cdd6f4;
            padding: 40px 20px;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
        }

        /* Animated particles background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            background: rgba(203, 166, 247, 0.3);
            border-radius: 50%;
            animation: float 20s infinite ease-in-out;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0) scale(1); opacity: 0; }
            10% { opacity: 0.6; }
            50% { transform: translateY(-100vh) translateX(50px) scale(1.2); opacity: 0.3; }
            90% { opacity: 0.6; }
        }

        .content {
            position: relative;
            z-index: 1;
        }

        /* Hero section with 3D tilt effect */
        .hero {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(135deg, rgba(203, 166, 247, 0.1) 0%, rgba(137, 180, 250, 0.05) 100%);
            border-radius: 20px;
            border: 1px solid rgba(203, 166, 247, 0.2);
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            transition: transform 0.3s ease;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(203, 166, 247, 0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .hero h1 {
            font-size: 3em;
            background: linear-gradient(45deg, #cba6f7, #89b4fa, #f38ba8, #fab387);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient-shift 5s ease infinite;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        @keyframes gradient-shift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .typing-container {
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px 0;
        }

        .typing-text {
            font-size: 1.2em;
            color: #cba6f7;
            position: relative;
            z-index: 1;
            min-height: 1.5em;
        }

        /* Coffee cup animation */
        .coffee-cup {
            font-size: 4em;
            display: inline-block;
            animation: bounce 2s infinite ease-in-out;
            filter: drop-shadow(0 0 20px rgba(203, 166, 247, 0.5));
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            25% { transform: translateY(-20px) rotate(-5deg); }
            75% { transform: translateY(-10px) rotate(5deg); }
        }

        /* Section styling with parallax effect */
        .section {
            background: rgba(30, 30, 46, 0.6);
            backdrop-filter: blur(10px);
            padding: 40px;
            margin: 30px 0;
            border-radius: 15px;
            border: 1px solid rgba(203, 166, 247, 0.2);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            border-color: rgba(203, 166, 247, 0.5);
            box-shadow: 0 10px 30px rgba(203, 166, 247, 0.2);
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(203, 166, 247, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .section:hover::before {
            left: 100%;
        }

        .section-title {
            font-size: 2em;
            color: #cba6f7;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #cba6f7, #89b4fa);
            transition: width 0.5s ease;
        }

        .section:hover .section-title::after {
            width: 100%;
        }

        /* Tech badges with hover effects */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .tech-badge {
            background: linear-gradient(135deg, rgba(203, 166, 247, 0.2), rgba(137, 180, 250, 0.2));
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            border: 1px solid rgba(203, 166, 247, 0.3);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(203, 166, 247, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.5s ease, height 0.5s ease;
        }

        .tech-badge:hover::before {
            width: 300px;
            height: 300px;
        }

        .tech-badge:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(203, 166, 247, 0.3);
        }

        .tech-badge span {
            position: relative;
            z-index: 1;
            font-weight: bold;
            font-size: 1.1em;
        }

        /* Code block animation */
        .code-block {
            background: rgba(17, 17, 27, 0.8);
            padding: 30px;
            border-radius: 10px;
            border-left: 4px solid #cba6f7;
            font-family: 'Courier New', monospace;
            margin: 20px 0;
            position: relative;
            overflow: hidden;
        }

        .code-line {
            opacity: 0;
            animation: fadeInLine 0.5s ease forwards;
            color: #a6e3a1;
        }

        .code-line:nth-child(1) { animation-delay: 0.2s; }
        .code-line:nth-child(2) { animation-delay: 0.4s; }
        .code-line:nth-child(3) { animation-delay: 0.6s; }
        .code-line:nth-child(4) { animation-delay: 0.8s; }
        .code-line:nth-child(5) { animation-delay: 1s; }

        @keyframes fadeInLine {
            to { opacity: 1; }
        }

        /* Glowing orbs */
        .stat-card {
            background: linear-gradient(135deg, rgba(30, 30, 46, 0.8), rgba(49, 50, 68, 0.6));
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(203, 166, 247, 0.2);
            margin: 20px 0;
            position: relative;
            overflow: hidden;
        }

        .stat-card::after {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(203, 166, 247, 0.3) 0%, transparent 70%);
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.5); opacity: 0.8; }
        }

        .research-list {
            list-style: none;
            padding: 0;
        }

        .research-list li {
            padding: 15px;
            margin: 10px 0;
            background: rgba(203, 166, 247, 0.1);
            border-radius: 8px;
            border-left: 3px solid #cba6f7;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .research-list li::before {
            content: '→';
            position: absolute;
            left: -30px;
            color: #cba6f7;
            font-size: 1.5em;
            transition: left 0.3s ease;
        }

        .research-list li:hover::before {
            left: 10px;
        }

        .research-list li:hover {
            transform: translateX(20px);
            background: rgba(203, 166, 247, 0.2);
        }

        /* Footer with wave effect */
        .footer {
            text-align: center;
            padding: 40px;
            margin-top: 50px;
            position: relative;
        }

        .footer::before {
            content: '☕';
            font-size: 3em;
            display: block;
            margin-bottom: 20px;
            animation: spin 4s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(180deg) scale(1.2); }
            100% { transform: rotate(360deg) scale(1); }
        }

        .cta-text {
            font-size: 1.5em;
            font-weight: bold;
            background: linear-gradient(45deg, #cba6f7, #89b4fa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient-shift 3s ease infinite;
        }

        .profile-views {
            display: inline-block;
            margin: 20px 0;
            padding: 10px 20px;
            background: rgba(157, 124, 216, 0.2);
            border-radius: 20px;
            border: 1px solid rgba(157, 124, 216, 0.5);
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2em; }
            .section { padding: 20px; }
            .tech-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <div class="content">
            <div class="hero">
                <div class="coffee-cup">☕</div>
                <h1>RUPARANI</h1>
                <div class="typing-container">
                    <div class="typing-text" id="typing"></div>
                </div>
                <div class="profile-views">
                    👁️ Profile Views: <strong>Loading...</strong>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">☕ About Me — Brewing Intelligence</h2>
                <div class="code-block">
                    <div class="code-line">while (coffee.isHot()) {</div>
                    <div class="code-line">    thinkDeep();</div>
                    <div class="code-line">    trainModels();</div>
                    <div class="code-line">    writeCode();</div>
                    <div class="code-line">}</div>
                </div>
                <p style="font-size: 1.1em; line-height: 1.8;">
                    I am <strong style="color: #cba6f7;">Ruparani (@Ruparani777)</strong> — an <strong>AI/ML Engineer</strong> who builds intelligent systems powered by machine learning, deep learning, and generative AI. I thrive at the intersection of research depth, engineering discipline, and creative curiosity.
                </p>
            </div>

            <div class="section">
                <h2 class="section-title">🧠 Knowledge Stack</h2>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; margin-top: 20px;">
                    <div class="stat-card">
                        <div style="font-size: 2em; margin-bottom: 10px;">🤖</div>
                        <div style="font-weight: bold; color: #cba6f7; font-size: 1.2em;">AI / ML</div>
                        <div style="color: #a6adc8;">Predictive & intelligent systems</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size: 2em; margin-bottom: 10px;">🧬</div>
                        <div style="font-weight: bold; color: #89b4fa; font-size: 1.2em;">Deep Learning</div>
                        <div style="color: #a6adc8;">Neural architectures & optimization</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size: 2em; margin-bottom: 10px;">🗣️</div>
                        <div style="font-weight: bold; color: #f38ba8; font-size: 1.2em;">NLP</div>
                        <div style="color: #a6adc8;">Language understanding & generation</div>
                    </div>
                    <div class="stat-card">
                        <div style="font-size: 2em; margin-bottom: 10px;">🎨</div>
                        <div style="font-weight: bold; color: #fab387; font-size: 1.2em;">Generative AI</div>
                        <div style="color: #a6adc8;">GANs, CycleGAN, creative models</div>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">💻 Tech I Code With</h2>
                <div class="tech-grid">
                    <div class="tech-badge"><span>Python</span></div>
                    <div class="tech-badge"><span>C</span></div>
                    <div class="tech-badge"><span>C++</span></div>
                    <div class="tech-badge"><span>PyTorch</span></div>
                    <div class="tech-badge"><span>TensorFlow</span></div>
                    <div class="tech-badge"><span>scikit-learn</span></div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">🔬 Research & Curiosity</h2>
                <ul class="research-list">
                    <li>Generative Adversarial Networks (GANs)</li>
                    <li>CycleGAN & representation learning</li>
                    <li>Language-centric AI systems</li>
                    <li>Advanced and experimental architectures</li>
                    <li>Model efficiency and scalability</li>
                </ul>
            </div>

            <div class="section">
                <h2 class="section-title">📚 Author Mode — Words Matter</h2>
                <p style="font-size: 1.1em; line-height: 1.8;">
                    I am the author of <strong style="color: #cba6f7;">two books published on Amazon KDP</strong>. Writing helps me translate complex systems into meaningful stories and clear understanding.
                </p>
                <p style="margin-top: 20px; font-style: italic; color: #a6adc8; text-align: center; font-size: 1.2em;">
                    "Code teaches machines. Writing teaches humans."
                </p>
            </div>

            <div class="section">
                <h2 class="section-title">🛠️ Currently Brewing</h2>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin-top: 20px;">
                    <div style="padding: 20px; background: rgba(203, 166, 247, 0.1); border-radius: 10px; border: 1px solid rgba(203, 166, 247, 0.3);">
                        ☕ Generative AI & NLP experiments
                    </div>
                    <div style="padding: 20px; background: rgba(137, 180, 250, 0.1); border-radius: 10px; border: 1px solid rgba(137, 180, 250, 0.3);">
                        🧪 Research-driven ML prototypes
                    </div>
                    <div style="padding: 20px; background: rgba(243, 139, 168, 0.1); border-radius: 10px; border: 1px solid rgba(243, 139, 168, 0.3);">
                        🧩 Open-source contributions
                    </div>
                    <div style="padding: 20px; background: rgba(250, 179, 135, 0.1); border-radius: 10px; border: 1px solid rgba(250, 179, 135, 0.3);">
                        📖 Continuous learning
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title">🤝 Let's Build Over Coffee</h2>
                <p style="font-size: 1.1em; line-height: 1.8;">
                    I'm always interested in:
                </p>
                <ul class="research-list">
                    <li>Research collaborations</li>
                    <li>Generative AI & NLP projects</li>
                    <li>Open-source innovation</li>
                    <li>Deep-tech & startup ideas</li>
                </ul>
            </div>

            <div class="footer">
                <div class="cta-text">Research-driven mind. Startup-ready hands.</div>
            </div>
        </div>
    </div>

    <script>
        // Create animated particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.width = Math.random() * 5 + 2 + 'px';
            particle.style.height = particle.style.width;
            particle.style.animationDelay = Math.random() * 10 + 's';
            particle.style.animationDuration = Math.random() * 10 + 15 + 's';
            particlesContainer.appendChild(particle);
        }

        // Typing animation
        const phrases = [
            '☕ Coffee-fueled AI Engineer',
            '🤖 Machine Learning | Generative AI',
            '🔬 Research Thinking × Startup Execution',
            '✍️ Author | Open Source Contributor'
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            let typeSpeed = isDeleting ? 50 : 100;

            if (!isDeleting && charIndex === currentPhrase.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                typeSpeed = 500;
            }

            setTimeout(type, typeSpeed);
        }

        type();

        // 3D tilt effect on hero section
        const hero = document.querySelector('.hero');
        hero.addEventListener('mousemove', (e) => {
            const rect = hero.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;
            
            const centerX = rect.width / 2;
            const centerY = rect.height / 2;
            
            const rotateX = (y - centerY) / 20;
            const rotateY = (centerX - x) / 20;
            
            hero.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
        });

        hero.addEventListener('mouseleave', () => {
            hero.style.transform = 'perspective(1000px) rotateX(0) rotateY(0)';
        });
    </script>
</body>
</html>
