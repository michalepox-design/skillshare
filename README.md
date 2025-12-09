<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SkillShift - Learn the Skills of Tomorrow, Updated Overnight</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Header & Navigation */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .cta-button {
            background: white;
            color: #667eea;
            padding: 0.7rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: transform 0.3s;
            cursor: pointer;
        }

        .cta-button:hover {
            transform: scale(1.05);
        }

        /* Mobile Menu Toggle */
        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 10rem 2rem 6rem;
            text-align: center;
            margin-top: 70px;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 0.8s ease;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 0.8s ease 0.2s backwards;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease 0.4s backwards;
        }

        .btn-primary {
            background: white;
            color: #667eea;
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s;
            border: 2px solid white;
            cursor: pointer;
        }

        .btn-primary:hover {
            background: transparent;
            color: white;
            transform: translateY(-3px);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 1rem 2.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            border: 2px solid white;
            transition: all 0.3s;
            cursor: pointer;
        }

        .btn-secondary:hover {
            background: white;
            color: #667eea;
            transform: translateY(-3px);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.8);
            animation: fadeIn 0.3s;
        }

        .modal-content {
            background: white;
            margin: 3% auto;
            padding: 0;
            width: 90%;
            max-width: 900px;
            border-radius: 20px;
            max-height: 90vh;
            overflow-y: auto;
            animation: slideDown 0.3s;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .modal-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2rem;
            border-radius: 20px 20px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .close {
            color: white;
            font-size: 2rem;
            font-weight: bold;
            cursor: pointer;
            background: none;
            border: none;
            transition: transform 0.3s;
        }

        .close:hover {
            transform: scale(1.2);
        }

        .modal-body {
            padding: 2rem;
        }

        .lecture-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .lecture-card {
            background: #f8f9fa;
            padding: 1.5rem;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }

        .lecture-card:hover {
            transform: translateY(-5px);
            border-color: #667eea;
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.3);
        }

        .lecture-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .lecture-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .lecture-duration {
            color: #666;
            font-size: 0.9rem;
        }

        .lecture-badge {
            display: inline-block;
            background: #667eea;
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            margin-top: 0.5rem;
        }

        /* Video Player */
        .video-container {
            background: #000;
            border-radius: 10px;
            overflow: hidden;
            margin: 2rem 0;
        }

        .video-player {
            width: 100%;
            aspect-ratio: 16/9;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            flex-direction: column;
            gap: 1rem;
        }

        .play-button {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: white;
            color: #667eea;
            border: none;
            font-size: 2rem;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .play-button:hover {
            transform: scale(1.1);
        }

        /* Features Grid */
        .features {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #667eea;
        }

        .feature-card p {
            color: #666;
            line-height: 1.8;
        }

        /* How It Works Section */
        .how-it-works {
            background: #f8f9fa;
            padding: 6rem 2rem;
        }

        .how-it-works-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .step {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            position: relative;
        }

        .step-number {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
            margin: 0 auto 1rem;
        }

        /* Interactive Demo */
        .demo-section {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 2rem;
        }

        .demo-container {
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            overflow: hidden;
            margin-top: 3rem;
        }

        .demo-tabs {
            display: flex;
            background: #f8f9fa;
            border-bottom: 2px solid #e9ecef;
            flex-wrap: wrap;
        }

        .demo-tab {
            flex: 1;
            padding: 1.5rem;
            text-align: center;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            border: none;
            background: transparent;
            font-size: 1rem;
            min-width: 150px;
        }

        .demo-tab:hover {
            background: #e9ecef;
        }

        .demo-tab.active {
            background: white;
            color: #667eea;
            border-bottom: 3px solid #667eea;
        }

        .demo-content {
            padding: 3rem;
            min-height: 400px;
        }

        .demo-panel {
            display: none;
        }

        .demo-panel.active {
            display: block;
            animation: fadeIn 0.5s;
        }

        /* Skill Path Visualization */
        .skill-path {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 2rem 0;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .skill-node {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1.5rem;
            border-radius: 15px;
            text-align: center;
            flex: 1;
            min-width: 150px;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .skill-node:hover {
            transform: scale(1.05);
        }

        .skill-node::after {
            content: '→';
            position: absolute;
            right: -1.5rem;
            font-size: 2rem;
            color: #667eea;
        }

        .skill-node:last-child::after {
            content: '';
        }

        /* Pricing Section */
        .pricing {
            background: #f8f9fa;
            padding: 6rem 2rem;
        }

        .pricing-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .currency-toggle {
            text-align: center;
            margin-bottom: 2rem;
        }

        .currency-toggle button {
            background: white;
            border: 2px solid #667eea;
            padding: 0.5rem 1.5rem;
            margin: 0 0.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .currency-toggle button.active {
            background: #667eea;
            color: white;
        }

        .pricing-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .pricing-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .pricing-card:hover {
            transform: translateY(-10px);
        }

        .pricing-card.featured {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            transform: scale(1.05);
        }

        .plan-name {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .plan-price {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .plan-period {
            opacity: 0.7;
            margin-bottom: 2rem;
        }

        .plan-features {
            list-style: none;
            margin: 2rem 0;
            text-align: left;
        }

        .plan-features li {
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        .plan-features li::before {
            content: '✓ ';
            color: #667eea;
            font-weight: bold;
            margin-right: 0.5rem;
        }

        .featured .plan-features li::before {
            color: white;
        }

        .featured .plan-features li {
            border-bottom-color: rgba(255,255,255,0.2);
        }

        /* CTA Section */
        .cta-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 6rem 2rem;
            text-align: center;
        }

        .cta-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .cta-section p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            padding: 3rem 2rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #667eea;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section a {
            color: #ccc;
            text-decoration: none;
            line-height: 2;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: white;
        }

        .footer-bottom {
            text-align: center;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid #333;
            color: #999;
        }

        /* Animations */
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

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Progress Bar */
        .progress-container {
            width: 100%;
            background: #e9ecef;
            border-radius: 10px;
            overflow: hidden;
            margin: 1rem 0;
        }

        .progress-bar {
            height: 30px;
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            transition: width 0.5s ease;
        }

        /* Stats Section */
        .stats {
            background: white;
            padding: 4rem 2rem;
        }

        .stats-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
        }

        .stat-item {
            padding: 2rem;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: #666;
            font-size: 1.1rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .nav-links {
                display: none;
            }

            .menu-toggle {
                display: block;
            }

            .skill-path {
                flex-direction: column;
            }

            .skill-node::after {
                content: '↓';
                right: auto;
                bottom: -2rem;
            }

            .modal-content {
                width: 95%;
                margin: 5% auto;
            }

            .demo-content {
                padding: 1.5rem;
            }
        }

        /* Success Message */
        .success-message {
            background: #d4edda;
            border: 1px solid #c3e6cb;
            color: #155724;
            padding: 1rem;
            border-radius: 10px;
            margin-top: 1rem;
            display: none;
            animation: fadeIn 0.3s;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo" onclick="window.location.reload()">
                🚀 SkillShift
            </div>
            <ul class="nav-links">
                <li><a href="#features">Features</a></li>
                <li><a href="#how-it-works">How It Works</a></li>
                <li><a href="#demo">Demo</a></li>
                <li><a href="#pricing">Pricing</a></li>
            </ul>
            <button class="menu-toggle">☰</button>
            <a class="cta-button" onclick="openFreeLectures()">Start Learning Free</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Learn the Skills of Tomorrow, Updated Overnight</h1>
        <p>The adaptive AI learning platform that evolves with industry changes in real-time</p>
        <div class="hero-buttons">
            <button class="btn-primary" onclick="openFreeLectures()">Get Started Free</button>
            <a href="#demo" class="btn-secondary">See Demo</a>
        </div>
    </section>

    <!-- Free Lectures Modal -->
    <div id="lecturesModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>🎓 Free Lectures - Start Learning Now!</h2>
                <button class="close" onclick="closeModal('lecturesModal')">&times;</button>
            </div>
            <div class="modal-body">
                <p style="color: #666; margin-bottom: 1rem;">Choose a free lecture to begin your learning journey. No signup required!</p>
                
                <h3 style="margin-top: 2rem; color: #667eea;">📊 Data Skills</h3>
                <div class="lecture-grid">
                    <div class="lecture-card" onclick="playLecture('Python Basics', 'data')">
                        <div class="lecture-icon">🐍</div>
                        <div class="lecture-title">Python for Beginners</div>
                        <div class="lecture-duration">⏱️ 12 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('SQL Introduction', 'data')">
                        <div class="lecture-icon">🗄️</div>
                        <div class="lecture-title">SQL Introduction</div>
                        <div class="lecture-duration">⏱️ 15 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('Data Visualization', 'data')">
                        <div class="lecture-icon">📈</div>
                        <div class="lecture-title">Data Visualization Basics</div>
                        <div class="lecture-duration">⏱️ 10 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                </div>

                <h3 style="margin-top: 2rem; color: #667eea;">🤖 AI Skills</h3>
                <div class="lecture-grid">
                    <div class="lecture-card" onclick="playLecture('AI Fundamentals', 'ai')">
                        <div class="lecture-icon">🧠</div>
                        <div class="lecture-title">What is Artificial Intelligence?</div>
                        <div class="lecture-duration">⏱️ 14 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('Prompt Engineering', 'ai')">
                        <div class="lecture-icon">💬</div>
                        <div class="lecture-title">Prompt Engineering 101</div>
                        <div class="lecture-duration">⏱️ 18 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('ChatGPT Mastery', 'ai')">
                        <div class="lecture-icon">🤖</div>
                        <div class="lecture-title">Using ChatGPT Effectively</div>
                        <div class="lecture-duration">⏱️ 16 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                </div>

                <h3 style="margin-top: 2rem; color: #667eea;">🌍 Climate Tech</h3>
                <div class="lecture-grid">
                    <div class="lecture-card" onclick="playLecture('Climate Change Basics', 'climate')">
                        <div class="lecture-icon">🌡️</div>
                        <div class="lecture-title">Understanding Climate Change</div>
                        <div class="lecture-duration">⏱️ 13 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('Carbon Footprint', 'climate')">
                        <div class="lecture-icon">👣</div>
                        <div class="lecture-title">Carbon Footprint Calculation</div>
                        <div class="lecture-duration">⏱️ 11 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                    <div class="lecture-card" onclick="playLecture('Renewable Energy', 'climate')">
                        <div class="lecture-icon">⚡</div>
                        <div class="lecture-title">Renewable Energy Overview</div>
                        <div class="lecture-duration">⏱️ 15 minutes</div>
                        <span class="lecture-badge">FREE</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Video Player Modal -->
    <div id="videoModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="videoTitle">Lecture Title</h2>
                <button class="close" onclick="closeModal('videoModal')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="video-container">
                    <div class="video-player">
                        <button class="play-button">▶</button>
                        <p>Video player placeholder</p>
                        <p style="font-size: 0.9rem; opacity: 0.8;">In the full version, this will be a real video lecture</p>
                    </div>
                </div>
                <div style="margin-top: 2rem;">
                    <h3>📝 Lecture Notes</h3>
                    <p id="lectureDescription" style="color: #666; margin: 1rem 0; line-height: 1.8;">
                        This is a comprehensive introduction to the topic. You'll learn the fundamentals and get hands-on practice.
                    </p>
                    <div style="display: flex; gap: 1rem; flex-wrap: wrap; margin-top: 2rem;">
                        <button class="btn-primary" onclick="alert('Download feature coming soon!')">📥 Download Notes</button>
                        <button class="btn-secondary" onclick="alert('Quiz feature coming soon!')">📝 Take Quiz</button>
                    </div>
                </div>
                <div class="success-message" id="successMessage">
                    ✅ Great! You've started your learning journey. Continue with more free lectures or upgrade to Pro for unlimited access!
                </div>
            </div>
        </div>
    </div>

    <!-- Stats Section -->
    <section class="stats">
        <div class="stats-grid">
            <div class="stat-item">
                <div class="stat-number">10K+</div>
                <div class="stat-label">Active Learners</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">500+</div>
                <div class="stat-label">Adaptive Modules</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">Weekly</div>
                <div class="stat-label">Curriculum Updates</div>
            </div>
            <div class="stat-item">
                <div class="stat-number">95%</div>
                <div class="stat-label">Skill Achievement Rate</div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features">
        <h2 class="section-title">What Makes SkillShift Unique</h2>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">🧠</div>
                <h3>Living Curriculum Engine</h3>
                <p>AI automatically updates lessons based on latest research papers, job postings, and industry reports. Your education never becomes outdated.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎯</div>
                <h3>Adaptive AI Learning Path</h3>
                <p>Personalized journey that adjusts to your performance, job role, and industry needs. No two paths are the same.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">👨‍🏫</div>
                <h3>AI Tutor & Skill Coach</h3>
                <p>Built-in mentor that explains concepts, helps with assignments, generates quizzes, and tracks your progress.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">
