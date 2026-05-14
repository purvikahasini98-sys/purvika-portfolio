<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Purvika Hasini Dondapati - Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #0f172a;
            --surface-color: rgba(30, 41, 59, 0.7);
            --primary-gradient: linear-gradient(135deg, #06b6d4, #8b5cf6);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --accent: #06b6d4;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 15% 50%, rgba(6, 182, 212, 0.15), transparent 25%),
                radial-gradient(circle at 85% 30%, rgba(139, 92, 246, 0.15), transparent 25%);
            background-attachment: fixed;
        }

        h1, h2, h3, h4 {
            font-family: 'Outfit', sans-serif;
        }

        /* Glassmorphism utility */
        .glass {
            background: var(--surface-color);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            padding: 15px 5%;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            color: var(--text-main);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.95rem;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--primary-gradient);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        header {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 10%;
            position: relative;
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            animation: fadeInUP 1s ease forwards;
        }

        .hero-greeting {
            color: var(--accent);
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 10px;
            display: block;
        }

        .hero-title {
            font-size: 4.5rem;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero-title span {
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-description {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 40px;
            max-width: 600px;
        }

        .btn {
            display: inline-block;
            padding: 15px 35px;
            border-radius: 30px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            font-family: 'Outfit', sans-serif;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: var(--primary-gradient);
            color: white;
            box-shadow: 0 10px 20px -10px rgba(139, 92, 246, 0.5);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 25px -10px rgba(139, 92, 246, 0.7);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-main);
            border: 2px solid var(--accent);
            margin-left: 15px;
        }

        .btn-secondary:hover {
            background: rgba(6, 182, 212, 0.1);
        }

        /* Sections General */
        section {
            padding: 100px 10%;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 50px;
            text-align: center;
        }

        .section-title span {
            color: var(--accent);
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .skill-card {
            padding: 30px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .skill-card h3 {
            margin-bottom: 15px;
            font-size: 1.5rem;
        }

        .skill-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }
        
        .languages-section {
            text-align: center;
        }

        .languages-section h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
        }

        .lang-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .lang-tag {
            background: rgba(139, 92, 246, 0.1);
            color: #f8fafc;
            border: 1px solid rgba(139, 92, 246, 0.3);
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 1rem;
            font-weight: 600;
        }

        /* Experience & Education Section */
        .timeline-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .timeline-column h3 {
            font-size: 1.8rem;
            margin-bottom: 30px;
            color: var(--accent);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .timeline-item {
            padding: 30px;
            margin-bottom: 20px;
            position: relative;
            border-left: 3px solid var(--accent);
            border-radius: 0 16px 16px 0;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            width: 15px;
            height: 15px;
            background: var(--accent);
            border-radius: 50%;
            left: -9px;
            top: 35px;
            box-shadow: 0 0 10px var(--accent);
        }

        .timeline-date {
            color: var(--accent);
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 10px;
        }

        .timeline-title {
            font-size: 1.3rem;
            margin-bottom: 5px;
        }

        .timeline-subtitle {
            color: var(--text-muted);
            font-size: 1rem;
            margin-bottom: 15px;
            font-weight: 600;
        }

        .timeline-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Achievements Section */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }

        .achievement-card {
            padding: 30px;
            border-radius: 16px;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .achievement-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px -10px rgba(0,0,0,0.5);
            border-color: rgba(6, 182, 212, 0.4);
        }

        .achievement-icon {
            font-size: 2.5rem;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        .achievement-title {
            font-size: 1.2rem;
            font-weight: 600;
        }

        .achievement-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            background: var(--surface-color);
            padding: 50px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(6, 182, 212, 0.1);
            color: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .contact-text h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }

        .contact-text p, .contact-text a {
            color: var(--text-muted);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .contact-text a:hover {
            color: var(--accent);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 15px 20px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: rgba(15, 23, 42, 0.5);
            color: var(--text-main);
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            transition: border-color 0.3s ease;
            outline: none;
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .form-group input:focus, .form-group textarea:focus {
            border-color: var(--accent);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            border-top: 1px solid rgba(255,255,255,0.05);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Animations */
        @keyframes fadeInUP {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 900px) {
            .timeline-container, .contact-grid {
                grid-template-columns: 1fr;
            }
            .hero-title {
                font-size: 3.5rem;
            }
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.8rem;
            }
            .nav-links {
                display: none;
            }
            .btn-secondary {
                margin-left: 0;
                margin-top: 15px;
            }
        }
    </style>
</head>
<body>

    <nav id="navbar">
        <a href="#" class="logo">Purvika<span>.</span></a>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#about">Skills</a>
            <a href="#experience">Experience & Education</a>
            <a href="#achievements">Achievements</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <header id="home">
        <div class="hero-content">
            <span class="hero-greeting">Hello, I am</span>
            <h1 class="hero-title">Purvika Hasini Dondapati</h1>
            <h2 class="hero-title" style="font-size: 2.5rem; color: var(--text-muted);">I build solutions & <span>Explore Tech</span>.</h2>
            <p class="hero-description">
                I am a passionate software developer skilled in Python, Java, and C. With a strong foundation in problem-solving and an enthusiasm for exploring cutting-edge technologies like Generative AI and Cloud Computing, I aim to build impactful applications.
            </p>
            <div>
                <a href="#contact" class="btn btn-primary">Get In Touch</a>
                <a href="#achievements" class="btn btn-secondary">View Achievements</a>
            </div>
        </div>
    </header>

    <section id="about">
        <h2 class="section-title">Technical <span>Skills</span></h2>
        <div class="skills-container">
            <div class="skill-card glass">
                <i class="fa-brands fa-python skill-icon"></i>
                <h3>Programming Languages</h3>
                <p>Proficient in Python, Java, and C, enabling me to build logic-driven backend systems and scalable software solutions.</p>
            </div>
            <div class="skill-card glass">
                <i class="fa-solid fa-cloud skill-icon"></i>
                <h3>Cloud & Emerging Tech</h3>
                <p>Experienced with AWS Fundamentals and Google Cloud's Generative AI Studio to leverage cutting-edge tools in applications.</p>
            </div>
            <div class="skill-card glass">
                <i class="fa-solid fa-laptop-code skill-icon"></i>
                <h3>Tools & Frameworks</h3>
                <p>Familiar with Full Stack Development principles and MS Excel for data organization and analysis.</p>
            </div>
        </div>

        <div class="languages-section glass" style="padding: 40px; border-radius: 16px;">
            <h3>Languages I Speak</h3>
            <div class="lang-tags">
                <span class="lang-tag">English</span>
                <span class="lang-tag">Hindi</span>
                <span class="lang-tag">Telugu</span>
                <span class="lang-tag">Malayalam</span>
            </div>
        </div>
    </section>

    <section id="experience">
        <h2 class="section-title">My <span>Journey</span></h2>
        <div class="timeline-container">
            <div class="timeline-column">
                <h3><i class="fa-solid fa-briefcase"></i> Experience</h3>
                
                <div class="timeline-item glass">
                    <div class="timeline-date">February 2026 - Current</div>
                    <h4 class="timeline-title">Intern</h4>
                    <div class="timeline-subtitle">Shaaka, Hyderabad</div>
                    <p class="timeline-desc">Explored new technologies and approaches to streamline processes. Earned this internship opportunity by winning 2nd Prize in a 36-hour National Level Hackathon.</p>
                </div>
                
                <div class="timeline-item glass">
                    <div class="timeline-date">Past</div>
                    <h4 class="timeline-title">Full Stack & AI Internships</h4>
                    <div class="timeline-subtitle">EduSkills</div>
                    <p class="timeline-desc">Completed specialized internship programs focusing on Google AI/ML and Java Full Stack Development.</p>
                </div>
            </div>

            <div class="timeline-column">
                <h3><i class="fa-solid fa-graduation-cap"></i> Education</h3>
                
                <div class="timeline-item glass">
                    <div class="timeline-date">Expected May 2028</div>
                    <h4 class="timeline-title">Bachelor of Technology</h4>
                    <div class="timeline-subtitle">Narsimha Reddy Engineering College</div>
                    <p class="timeline-desc">Pursuing B.Tech in Hyderabad, focusing on core computer science subjects, algorithms, and software engineering.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="achievements">
        <h2 class="section-title">Achievements & <span>Certifications</span></h2>
        <div class="achievements-grid">
            
            <div class="achievement-card glass">
                <i class="fa-solid fa-trophy achievement-icon"></i>
                <h3 class="achievement-title">Best GR Award</h3>
                <p class="achievement-desc">Awarded the Best GR Award at Narsimha Reddy Engineering College, recognizing strong leadership skills and outstanding contribution.</p>
            </div>

            <div class="achievement-card glass">
                <i class="fa-solid fa-medal achievement-icon"></i>
                <h3 class="achievement-title">2nd Prize - National Hackathon</h3>
                <p class="achievement-desc">Secured 2nd prize in an intensive 36-hour National Level Hackathon, demonstrating rapid problem solving and teamwork.</p>
            </div>

            <div class="achievement-card glass">
                <i class="fa-solid fa-award achievement-icon"></i>
                <h3 class="achievement-title">3rd Prize - PPT Presentation</h3>
                <p class="achievement-desc">Won 3rd prize for an excellent technical PPT presentation held at Anurag University.</p>
            </div>

            <div class="achievement-card glass">
                <i class="fa-solid fa-certificate achievement-icon"></i>
                <h3 class="achievement-title">NPTEL Python Certification</h3>
                <p class="achievement-desc">Achieved Elite + Silver tier in the prestigious NPTEL Python Programming Certification.</p>
            </div>

            <div class="achievement-card glass">
                <i class="fa-brands fa-aws achievement-icon"></i>
                <h3 class="achievement-title">AWS & Gen AI Certifications</h3>
                <p class="achievement-desc">Completed certifications in AWS Fundamentals, Generative AI (Google Cloud Simplilearn), and various Python/Java modules.</p>
            </div>

            <div class="achievement-card glass">
                <i class="fa-solid fa-file-excel achievement-icon"></i>
                <h3 class="achievement-title">Microsoft MS Excel</h3>
                <p class="achievement-desc">Received certificate from Microsoft Simplilearn for successfully completing the Introduction to MS Excel course.</p>
            </div>

        </div>
    </section>

    <section id="contact">
        <h2 class="section-title">Get In <span>Touch</span></h2>
        
        <div class="contact-grid">
            <div class="contact-info">
                <h3 style="font-size: 1.8rem; margin-bottom: 20px;">Contact Information</h3>
                <p style="color: var(--text-muted); margin-bottom: 30px;">Feel free to reach out to me for collaborations, tech discussions, or exciting new opportunities!</p>
                
                <div class="contact-item">
                    <div class="contact-icon"><i class="fa-solid fa-envelope"></i></div>
                    <div class="contact-text">
                        <h4>Email</h4>
                        <a href="mailto:purvikahasini98@gmail.com">purvikahasini98@gmail.com</a>
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon"><i class="fa-solid fa-phone"></i></div>
                    <div class="contact-text">
                        <h4>Phone</h4>
                        <a href="tel:+919014802210">+91 90148 02210</a>
                    </div>
                </div>

                <div class="contact-item">
                    <div class="contact-icon"><i class="fa-solid fa-location-dot"></i></div>
                    <div class="contact-text">
                        <h4>Location</h4>
                        <p>Hyderabad 500090, India</p>
                    </div>
                </div>
            </div>

            <form class="contact-form" onsubmit="submitForm(event)">
                <h3 style="font-size: 1.8rem; margin-bottom: 10px;">Send a Message</h3>
                <div class="form-group">
                    <input type="text" placeholder="Your Name" required>
                </div>
                <div class="form-group">
                    <input type="email" placeholder="Your Email" required>
                </div>
                <div class="form-group">
                    <textarea placeholder="Your Message" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary">Send Message <i class="fa-solid fa-paper-plane" style="margin-left: 5px;"></i></button>
            </form>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Purvika Hasini Dondapati. Built with passion.</p>
        <div style="margin-top: 15px; font-size: 1.5rem;">
            <a href="#" style="color: var(--text-muted); margin: 0 10px; text-decoration: none;"><i class="fa-brands fa-github"></i></a>
            <a href="#" style="color: var(--text-muted); margin: 0 10px; text-decoration: none;"><i class="fa-brands fa-linkedin"></i></a>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Form Submission placeholder
        function submitForm(e) {
            e.preventDefault();
            alert("Thank you for your message, Purvika will get back to you soon!");
            e.target.reset();
        }

        // Smooth reveal animation for sections
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = 1;
                    entry.target.style.transform = 'translateY(0)';
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('section').forEach(section => {
            section.style.opacity = 0;
            section.style.transform = 'translateY(50px)';
            section.style.transition = 'all 0.8s ease-out';
            observer.observe(section);
        });
    </script>
</body>
</html>
