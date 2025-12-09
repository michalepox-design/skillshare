
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
        }

        .cta-button:hover {
            transform: scale(1.05);
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
        }

        .btn-secondary:hover {
            background: white;
            color: #667eea;
            transform: translateY(-3px);
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

            .skill-path {
                flex-direction: column;
            }

            .skill-node::after {
                content: '↓';
                right: auto;
                bottom: -2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">
                🚀 SkillShift
            </div>
            <ul class="nav-links">
                <li><a href="#features">Features</a></li>
                <li><a href="#how-it-works">How It Works</a></li>
                <li><a href="#demo">Demo</a></li>
                <li><a href="#pricing">Pricing</a></li>
            </ul>
            <a href="#signup" class="cta-button">Start Learning Free</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Learn the Skills of Tomorrow, Updated Overnight</h1>
        <p>The adaptive AI learning platform that evolves with industry changes in real-time</p>
        <div class="hero-buttons">
            <a href="#signup" class="btn-primary">Get Started Free</a>
            <a href="#demo" class="btn-secondary">See Demo</a>
        </div>
    </section>

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
                <div class="feature-icon">💼</div>
                <h3>Job-Market Scanner</h3>
                <p>Scans thousands of job postings daily to determine what skills employers need right now and updates lessons accordingly.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔬</div>
                <h3>Real-World Labs</h3>
                <p>Hands-on sandboxes for data analytics, AI tools, and climate tech. Practice with real datasets and tools.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🗺️</div>
                <h3>SkillMap Engine</h3>
                <p>Visual progress map showing everything you've mastered and what to learn next. Perfect for portfolio building.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">📊</div>
                <h3>Enterprise Dashboard</h3>
                <p>For companies: track employee skill growth, identify gaps, build custom pathways, and benchmark against industry standards.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">⚡</div>
                <h3>Microlearning</h3>
                <p>5-10 minute lessons designed to fit into your daily work schedule. Learn continuously without disruption.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🎮</div>
                <h3>Gamified Experience</h3>
                <p>Earn badges, XP points, maintain streaks, and compete on leaderboards. Make learning engaging and fun.</p>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section id="how-it-works" class="how-it-works">
        <div class="how-it-works-content">
            <h2 class="section-title">How SkillShift Works</h2>
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Take Assessment</h3>
                    <p>Quick skill assessment to understand your current level and learning goals.</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Get Personalized Path</h3>
                    <p>AI creates your unique learning journey based on your role, industry, and goals.</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Learn & Practice</h3>
                    <p>Engage with updated content, hands-on labs, and real-world projects.</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Earn Certifications</h3>
                    <p>Complete modules and earn industry-recognized micro-certifications.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Demo -->
    <section id="demo" class="demo-section">
        <h2 class="section-title">Experience SkillShift</h2>
        <div class="demo-container">
            <div class="demo-tabs">
                <button class="demo-tab active" onclick="showDemo('data')">Data Skills</button>
                <button class="demo-tab" onclick="showDemo('ai')">AI Skills</button>
                <button class="demo-tab" onclick="showDemo('climate')">Climate Tech</button>
            </div>
            <div class="demo-content">
                <div id="data-demo" class="demo-panel active">
                    <h3>📊 Data Skills Learning Path</h3>
                    <div class="skill-path">
                        <div class="skill-node">
                            <strong>Python Basics</strong>
                            <div>2 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>SQL Mastery</strong>
                            <div>3 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Data Viz</strong>
                            <div>2 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Analytics</strong>
                            <div>4 weeks</div>
                        </div>
                    </div>
                    <p style="margin-top: 2rem;"><strong>Your Progress:</strong></p>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 65%;">65% Complete</div>
                    </div>
                    <p style="margin-top: 1rem; color: #666;">
                        <strong>Next Lesson:</strong> Advanced SQL Joins - Updated 2 days ago based on latest industry practices
                    </p>
                </div>
                <div id="ai-demo" class="demo-panel">
                    <h3>🤖 AI Skills Learning Path</h3>
                    <div class="skill-path">
                        <div class="skill-node">
                            <strong>AI Fundamentals</strong>
                            <div>2 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Prompt Engineering</strong>
                            <div>1 week</div>
                        </div>
                        <div class="skill-node">
                            <strong>ML Basics</strong>
                            <div>4 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Ethical AI</strong>
                            <div>2 weeks</div>
                        </div>
                    </div>
                    <p style="margin-top: 2rem;"><strong>Your Progress:</strong></p>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 40%;">40% Complete</div>
                    </div>
                    <p style="margin-top: 1rem; color: #666;">
                        <strong>Next Lesson:</strong> GPT-4 Best Practices - Added this week based on latest research
                    </p>
                </div>
                <div id="climate-demo" class="demo-panel">
                    <h3>🌍 Climate Tech Learning Path</h3>
                    <div class="skill-path">
                        <div class="skill-node">
                            <strong>Carbon Accounting</strong>
                            <div>3 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Climate Data</strong>
                            <div>3 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>Renewable Energy</strong>
                            <div>4 weeks</div>
                        </div>
                        <div class="skill-node">
                            <strong>ESG Reporting</strong>
                            <div>2 weeks</div>
                        </div>
                    </div>
                    <p style="margin-top: 2rem;"><strong>Your Progress:</strong></p>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 25%;">25% Complete</div>
                    </div>
                    <p style="margin-top: 1rem; color: #666;">
                        <strong>Next Lesson:</strong> Net Zero Strategies - Updated today with COP28 outcomes
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="pricing">
        <div class="pricing-content">
            <h2 class="section-title">Choose Your Plan</h2>
            <div class="pricing-cards">
                <div class="pricing-card">
                    <div class="plan-name">Free</div>
                    <div class="plan-price">$0</div>
                    <div class="plan-period">forever</div>
                    <ul class="plan-features">
                        <li>Access to basic modules</li>
                        <li>5 lessons per month</li>
                        <li>Community support</li>
                        <li>Progress tracking</li>
                    </ul>
                    <a href="#signup" class="btn-secondary">Get Started</a>
                </div>
                <div class="pricing-card featured">
                    <div class="plan-name">Pro</div>
                    <div class="plan-price">$29</div>
                    <div class="plan-period">per month</div>
                    <ul class="plan-features">
                        <li>Unlimited lessons</li>
                        <li>AI Tutor access</li>
                        <li>All sandboxes</li>
                        <li>Certificates</li>
                        <li>Priority support</li>
                        <li>Job market insights</li>
                    </ul>
                    <a href="#signup" class="btn-primary">Start Free Trial</a>
                </div>
                <div class="pricing-card">
                    <div class="plan-name">Enterprise</div>
                    <div class="plan-price">Custom</div>
                    <div class="plan-period">contact us</div>
                    <ul class="plan-features">
                        <li>Everything in Pro</li>
                        <li>Team dashboard</li>
                        <li>Custom pathways</li>
                        <li>White-label option</li>
                        <li>Dedicated support</li>
                        <li>API access</li>
                    </ul>
                    <a href="#contact" class="btn-secondary">Contact Sales</a>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section id="signup" class="cta-section">
        <h2>Ready to Future-Proof Your Skills?</h2>
        <p>Join thousands of professionals learning the skills of tomorrow</p>
        <div style="max-width: 500px; margin: 2rem auto;">
            <form id="signup-form" style="display: flex; gap: 1rem; flex-wrap: wrap;">
                <input type="email" placeholder="Enter your email" required 
                       style="flex: 1; padding: 1rem; border-radius: 25px; border: none; font-size: 1rem; min-width: 250px;">
                <button type="submit" class="btn-primary" style="border: none; cursor: pointer;">
                    Start Free Trial
                </button>
            </form>
            <p style="font-size: 0.9rem; margin-top: 1rem; opacity: 0.8;">
                No credit card required • 7-day free trial • Cancel anytime
            </p>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>SkillShift</h3>
                <p>The adaptive AI learning platform for future skills</p>
            </div>
            <div class="footer-section">
                <h3>Product</h3>
                <ul>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#demo">Demo</a></li>
                    <li><a href="#enterprise">Enterprise</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Learn</h3>
                <ul>
                    <li><a href="#data">Data Skills</a></li>
                    <li><a href="#ai">AI Skills</a></li>
                    <li><a href="#climate">Climate Tech</a></li>
                    <li><a href="#blog">Blog</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Company</h3>
                <ul>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#careers">Careers</a></li>
                    <li><a href="#contact">Contact</a></li>
                    <li><a href="#privacy">Privacy Policy</a></li>
