# index.html
my personal website
```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rain Junyu Qian | Statistics & Data Science Portfolio</title>
    <style>
        /* --- Root Variables & Theme System --- */
        :root {
            --bg-primary: #f8fafc;
            --bg-surface: #ffffff;
            --bg-card: #ffffff;
            --text-main: #0f172a;
            --text-muted: #475569;
            
            /* Data/Tech Inspired Palette: Clean Navy, Deep Teal, and Soft Slate */
            --primary: #1e3a8a;
            --primary-light: #3b82f6;
            --primary-gradient: linear-gradient(135deg, #1e3a8a 0%, #0d9488 100%);
            --accent: #0f766e;
            --accent-bg: #f0fdfa;
            
            --border-color: #e2e8f0;
            --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
            --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.05), 0 2px 4px -2px rgb(0 0 0 / 0.05);
            --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.04), 0 4px 6px -4px rgb(0 0 0 / 0.04);
            --radius-md: 12px;
            --radius-lg: 16px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* --- Global Reset & Base Styles --- */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
            background-color: var(--bg-primary);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }

        a {
            color: inherit;
            text-decoration: none;
            transition: var(--transition);
        }

        li {
            list-style: none;
        }

        section {
            padding: 90px 24px;
            max-width: 1100px;
            margin: 0 auto;
            scroll-mt: 80px;
        }

        /* --- Typography Layouts --- */
        .section-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-header h2 {
            font-size: 2.25rem;
            font-weight: 800;
            color: var(--primary);
            letter-spacing: -0.025em;
            margin-bottom: 12px;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        /* --- Scroll Reveal Animation --- */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- Navigation Bar --- */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            height: 70px;
            background-color: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px border var(--border-color);
            z-index: 1000;
            transition: var(--transition);
        }

        .navbar.scrolled {
            box-shadow: var(--shadow-sm);
            background-color: rgba(255, 255, 255, 0.95);
        }

        .nav-container {
            max-width: 1200px;
            height: 100%;
            margin: 0 auto;
            padding: 0 24px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .nav-logo {
            font-weight: 700;
            font-size: 1.25rem;
            color: var(--primary);
            letter-spacing: -0.01em;
        }

        .nav-logo span {
            color: var(--primary-light);
        }

        .nav-links {
            display: flex;
            gap: 28px;
        }

        .nav-links a {
            font-size: 0.925rem;
            font-weight: 500;
            color: var(--text-muted);
            position: relative;
            padding: 4px 0;
        }

        .nav-links a:hover, .nav-links a.active {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary-light);
            transition: var(--transition);
        }

        .nav-links a.active::after, .nav-links a:hover::after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            flex-direction: column;
            gap: 5px;
            cursor: pointer;
            background: none;
            border: none;
        }

        .menu-toggle span {
            width: 24px;
            height: 2px;
            background-color: var(--text-main);
            transition: var(--transition);
        }

        /* --- Hero Section --- */
        .hero-section {
            padding: 160px 24px 100px;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            background: radial-gradient(circle at top right, rgba(59, 130, 246, 0.06), transparent 40%),
                        radial-gradient(circle at bottom left, rgba(15, 118, 110, 0.05), transparent 40%);
        }

        .hero-badge {
            background-color: #eff6ff;
            color: #1d4ed8;
            padding: 6px 16px;
            border-radius: 100px;
            font-size: 0.85rem;
            font-weight: 600;
            letter-spacing: 0.02em;
            margin-bottom: 24px;
            border: 1px solid #dbeafe;
            display: inline-block;
        }

        .hero-section h1 {
            font-size: 3.5rem;
            font-weight: 850;
            line-height: 1.15;
            letter-spacing: -0.03em;
            margin-bottom: 16px;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-tagline {
            font-size: 1.35rem;
            color: var(--text-muted);
            font-weight: 500;
            max-width: 750px;
            margin-bottom: 24px;
            line-height: 1.4;
        }

        .hero-intro {
            font-size: 1.1rem;
            color: var(--text-muted);
            max-width: 650px;
            margin-bottom: 36px;
        }

        .btn-container {
            display: flex;
            gap: 16px;
            justify-content: center;
        }

        .btn {
            padding: 12px 28px;
            border-radius: var(--radius-md);
            font-weight: 600;
            font-size: 0.975rem;
            cursor: pointer;
            box-shadow: var(--shadow-sm);
        }

        .btn-primary {
            background-color: var(--primary);
            color: #ffffff;
            border: 1px solid var(--primary);
        }

        .btn-primary:hover {
            background-color: #172554;
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .btn-secondary {
            background-color: var(--bg-surface);
            color: var(--text-main);
            border: 1px solid var(--border-color);
        }

        .btn-secondary:hover {
            background-color: var(--bg-primary);
            border-color: #cbd5e1;
            transform: translateY(-2px);
        }

        /* --- About Me Section --- */
        .about-grid {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 48px;
            align-items: center;
        }

        .about-content h3 {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 16px;
            font-weight: 700;
        }

        .about-content p {
            color: var(--text-muted);
            margin-bottom: 20px;
            font-size: 1.05rem;
            text-align: justify;
        }

        .profile-container {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        .profile-card {
            width: 320px;
            height: 380px;
            background: var(--bg-card);
            border-radius: var(--radius-lg);
            border: 1px solid var(--border-color);
            box-shadow: var(--shadow-lg);
            padding: 24px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: linear-gradient(180deg, #ffffff 0%, #f8fafc 100%);
        }

        .profile-avatar-placeholder {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: var(--primary-gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #ffffff;
            margin-bottom: 24px;
            box-shadow: var(--shadow-md);
        }

        .profile-avatar-placeholder svg {
            width: 64px;
            height: 64px;
            opacity: 0.95;
        }

        .profile-card h4 {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 4px;
        }

        .profile-card p {
            font-size: 0.875rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        .profile-meta {
            margin-top: 20px;
            padding-top: 16px;
            border-top: 1px solid var(--border-color);
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
        }

        .meta-item {
            font-size: 0.8rem;
            background-color: rgba(30, 58, 138, 0.04);
            padding: 6px;
            border-radius: 6px;
            color: var(--primary);
            font-weight: 600;
        }

        /* --- Academic Interests --- */
        .interests-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 24px;
        }

        .interest-card {
            background-color: var(--bg-card);
            padding: 32px;
            border-radius: var(--radius-md);
            border: 1px solid var(--border-color);
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .interest-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
            border-color: rgba(59, 130, 246, 0.3);
        }

        .interest-icon {
            width: 48px;
            height: 48px;
            border-radius: 10px;
            background-color: #eff6ff;
            color: var(--primary-light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
        }

        .interest-card h3 {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 12px;
            color: var(--primary);
        }

        .interest-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* --- Featured Project --- */
        .project-showcase {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-md);
            overflow: hidden;
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
        }

        .project-main {
            padding: 44px;
            border-right: 1px solid var(--border-color);
        }

        .project-tag {
            color: var(--accent);
            background-color: var(--accent-bg);
            padding: 4px 12px;
            border-radius: 6px;
            font-size: 0.85rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 16px;
        }

        .project-main h3 {
            font-size: 1.75rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 16px;
            line-height: 1.3;
        }

        .project-description {
            color: var(--text-muted);
            margin-bottom: 24px;
            font-size: 1.025rem;
        }

        .project-steps {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .step {
            display: flex;
            gap: 14px;
        }

        .step-num {
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background-color: var(--primary);
            color: #ffffff;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: 700;
            margin-top: 2px;
            flex-shrink: 0;
        }

        .step-text h4 {
            font-size: 0.975rem;
            font-weight: 600;
            color: var(--text-main);
        }

        .step-text p {
            font-size: 0.9rem;
            color: var(--text-muted);
        }

        .project-sidebar {
            background-color: rgba(248, 250, 252, 0.6);
            padding: 44px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .sidebar-block h4 {
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            color: var(--text-muted);
            margin-bottom: 12px;
            font-weight: 700;
        }

        .tech-pills {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 32px;
        }

        .pill {
            background-color: #ffffff;
            border: 1px solid var(--border-color);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--text-main);
            box-shadow: var(--shadow-sm);
        }

        .metric-card {
            background: var(--primary-gradient);
            color: #ffffff;
            padding: 20px;
            border-radius: var(--radius-md);
            box-shadow: var(--shadow-md);
        }

        .metric-title {
            font-size: 0.85rem;
            opacity: 0.85;
            font-weight: 500;
            margin-bottom: 4px;
        }

        .metric-value {
            font-size: 1.35rem;
            font-weight: 700;
        }

        /* --- Awards & Achievements --- */
        .awards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 20px;
        }

        .award-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            padding: 24px;
            display: flex;
            gap: 16px;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .award-card:hover {
            box-shadow: var(--shadow-md);
            border-color: rgba(15, 118, 110, 0.2);
            transform: translateY(-2px);
        }

        .award-badge {
            width: 44px;
            height: 44px;
            background-color: #fef3c7;
            color: #d97706;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .award-card.silver .award-badge {
            background-color: #f1f5f9;
            color: #475569;
        }

        .award-card.bronze .award-badge {
            background-color: #ffedd5;
            color: #c2410c;
        }

        .award-card.program .award-badge {
            background-color: #e0f2fe;
            color: #0369a1;
        }

        .award-info h3 {
            font-size: 1.05rem;
            font-weight: 700;
            color: var(--text-main);
            margin-bottom: 2px;
        }

        .award-scope {
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.02em;
            color: var(--accent);
            margin-bottom: 6px;
        }

        .award-desc {
            font-size: 0.875rem;
            color: var(--text-muted);
            line-height: 1.4;
        }

        /* --- Clubs & Activities --- */
        .activities-layout {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 24px;
            margin-bottom: 24px;
        }

        .activity-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-md);
            padding: 28px;
            box-shadow: var(--shadow-sm);
        }

        .activity-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 12px;
        }

        .activity-header h3 {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary);
        }

        .activity-date {
            font-size: 0.8rem;
            font-weight: 500;
            color: var(--text-muted);
            background-color: var(--bg-primary);
            padding: 4px 10px;
            border-radius: 4px;
            border: 1px solid var(--border-color);
        }

        .activity-card p {
            font-size: 0.95rem;
            color: var(--text-muted);
        }

        .featured-experience {
            grid-column: 1 / -1;
            background: linear-gradient(to right, #ffffff, #fafafa);
            border-left: 4px solid var(--primary-light);
            padding: 32px;
            border-radius: 0 var(--radius-md) var(--radius-md) 0;
            box-shadow: var(--shadow-sm);
            border-top: 1px solid var(--border-color);
            border-right: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
        }

        .featured-experience h4 {
            color: var(--primary);
            font-size: 1.15rem;
            font-weight: 700;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .featured-experience p {
            color: var(--text-muted);
            font-size: 1rem;
            line-height: 1.5;
        }

        /* --- Skills Framework --- */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            gap: 16px;
        }

        .skill-tag-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 16px 20px;
            border-radius: var(--radius-md);
            display: flex;
            align-items: center;
            gap: 12px;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .skill-tag-card:hover {
            border-color: var(--primary-light);
            box-shadow: var(--shadow-md);
            transform: translateY(-1px);
        }

        .skill-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: var(--accent);
        }

        .skill-tag-card span {
            font-weight: 600;
            font-size: 0.95rem;
            color: var(--text-main);
        }

        /* --- Career Goals --- */
        .goals-box {
            background: linear-gradient(135deg, rgba(30, 58, 138, 0.03) 0%, rgba(15, 118, 110, 0.03) 100%);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            padding: 44px;
            text-align: center;
            max-width: 850px;
            margin: 0 auto;
        }

        .goals-box h3 {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 16px;
        }

        .goals-box p {
            font-size: 1.1rem;
            color: var(--text-muted);
            line-height: 1.6;
            max-width: 700px;
            margin: 0 auto;
        }

        /* --- Contact --- */
        .contact-grid {
            display: grid;
            grid-template-columns: 0.9fr 1.1fr;
            gap: 48px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .contact-text p {
            color: var(--text-muted);
            font-size: 1.05rem;
            margin-bottom: 32px;
        }

        .contact-links {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 14px;
            background-color: var(--bg-card);
            padding: 16px;
            border-radius: var(--radius-md);
            border: 1px solid var(--border-color);
        }

        .contact-icon-wrapper {
            width: 40px;
            height: 40px;
            background-color: #f1f5f9;
            color: var(--primary);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .contact-details h4 {
            font-size: 0.75rem;
            text-transform: uppercase;
            color: var(--text-muted);
            letter-spacing: 0.02em;
        }

        .contact-details p {
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--text-main);
        }

        .contact-form {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 36px;
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-md);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-main);
            margin-bottom: 6px;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 10px 14px;
            border-radius: 6px;
            border: 1px solid var(--border-color);
            background-color: var(--bg-primary);
            font-family: inherit;
            font-size: 0.95rem;
            color: var(--text-main);
            transition: var(--transition);
        }

        .form-group input:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-light);
            background-color: #ffffff;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
        }

        .contact-form .btn {
            width: 100%;
            border: none;
        }

        /* --- Footer --- */
        footer {
            background-color: #0f172a;
            color: #94a3b8;
            padding: 40px 24px;
            text-align: center;
            border-top: 1px solid #1e293b;
            font-size: 0.9rem;
        }

        footer p {
            margin-bottom: 8px;
        }

        .footer-note {
            font-size: 0.8rem;
            opacity: 0.6;
        }

        /* --- Responsive Queries --- */
        @media (max-width: 968px) {
            section { padding: 60px 20px; }
            .hero-section h1 { font-size: 2.75rem; }
            .about-grid, .contact-grid { grid-template-columns: 1fr; gap: 36px; }
            .profile-container { order: -1; }
            .project-showcase { grid-template-columns: 1fr; }
            .project-main { border-right: none; border-bottom: 1px solid var(--border-color); padding: 32px; }
            .project-sidebar { padding: 32px; }
            .activities-layout { grid-template-columns: 1fr; }
        }

        @media (max-width: 768px) {
            .menu-toggle { display: flex; }
            .nav-links {
                position: absolute;
                top: 70px;
                left: 0;
                right: 0;
                background-color: #ffffff;
                flex-direction: column;
                gap: 0;
                width: 100%;
                border-bottom: 1px solid var(--border-color);
                box-shadow: var(--shadow-md);
                max-height: 0;
                overflow: hidden;
                transition: max-height 0.3s ease-out;
            }
            .nav-links.open { max-height: 400px; }
            .nav-links a { padding: 16px 24px; border-bottom: 1px solid #f1f5f9; display: block; }
            .nav-links a::after { display: none; }
            .hero-section h1 { font-size: 2.25rem; }
            .hero-tagline { font-size: 1.15rem; }
            .btn-container { flex-direction: column; width: 100%; max-width: 300px; }
        }
    </style>
</head>
<body>

    <header class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#hero" class="nav-logo">Rain<span>.Qian</span></a>
            <button class="menu-toggle" id="menuToggle" aria-label="Toggle navigation Menu">
                <span></span>
                <span></span>
                <span></span>
            </button>
            <nav class="nav-links" id="navLinks">
                <a href="#hero" class="nav-item active">Home</a>
                <a href="#about" class="nav-item">About</a>
                <a href="#interests" class="nav-item">Interests</a>
                <a href="#project" class="nav-item">Project</a>
                <a href="#awards" class="nav-item">Awards</a>
                <a href="#activities" class="nav-item">Activities</a>
                <a href="#skills" class="nav-item">Skills</a>
                <a href="#contact" class="nav-item">Contact</a>
            </nav>
        </div>
    </header>

    <section id="hero" class="hero-section">
        <div class="hero-badge">University Admissions Portfolio</div>
        <h1>Rain Junyu Qian</h1>
        <p class="hero-tagline">“Grade 11 Student | Statistics & Data Science Applicant | Aspiring Data Analyst”</p>
        <p class="hero-intro">
            Motivated researcher skilled in mathematical modeling, computational methodologies, and statistical synthesis to decode complex structural patterns within economy and modern society.
        </p>
        <div class="btn-container">
            <a href="#project" class="btn btn-primary">View Research Project</a>
            <a href="#contact" class="btn btn-secondary">Get In Touch</a>
        </div>
    </section>

    <section id="about" class="reveal">
        <div class="section-header">
            <h2>About Me</h2>
            <p>Driven by logic, grounded in quantitative research methodology</p>
        </div>
        <div class="about-grid">
            <div class="about-content">
                <h3>Bridging Numbers and Real-World Impact</h3>
                <p>
                    I am a highly driven Grade 11 student currently studying within the AS-1 academic stream. My academic journey is fueled by a profound fascination with Statistics and Data Science—specifically how pure mathematical matrices can be leveraged to understand complex structural problems within economics and human society.
                </p>
                <p>
                    Curious by nature and deeply self-disciplined, I enjoy moving past standard class syllabi to uncover hidden trends via statistical modeling. Whether executing code routines, compiling rigorous independent essays, or interpreting microeconomic fluctuations, I apply a critical framework focused on reliability, empirical data, and structural logic.
                </p>
            </div>
            <div class="profile-container">
                <div class="profile-card">
                    <div class="profile-avatar-placeholder">
                        <svg viewBox="0 0 24 24" fill="currentColor">
                            <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16 w-16v-2c0-2.66-5.33-4-8-4z"/>
                        </svg>
                    </div>
                    <h4>Rain Junyu Qian</h4>
                    <p>Class AS-1 Specialty</p>
                    <div class="profile-meta">
                        <div class="meta-item">Analytical Mind</div>
                        <div class="meta-item">Top 5% Rank</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="interests" class="reveal">
        <div class="section-header">
            <h2>Academic Focus & Interests</h2>
            <p>The core disciplines shaping my analytical framework and research pursuits</p>
        </div>
        <div class="interests-grid">
            <div class="interest-card">
                <div class="interest-icon">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 002 2h2a2 2 0 002-2"></path></svg>
                </div>
                <h3>Statistics</h3>
                <p>Analyzing probability distributions, sample matrices, and regression curves to systematically clear real-world uncertainty.</p>
            </div>
            <div class="interest-card">
                <div class="interest-icon">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"></path></svg>
                </div>
                <h3>Data Science</h3>
                <p>Processing structural databases through software calculations, pattern tracking, and optimization techniques.</p>
            </div>
            <div class="interest-card">
                <div class="interest-icon">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M4 7V4a1 1 0 011-1h3m12 4V4a1 1 0 00-1-1h-3M4 17v3a1 1 0 001 1h3m12-1v3a1 1 0 01-1 1h-3M9 9h6v6H9V9z"></path></svg>
                </div>
                <h3>Mathematics</h3>
                <p>Developing structural calculus, algebra matrices, and predictive game-theory foundations to model real-world trends.</p>
            </div>
            <div class="interest-card">
                <div class="interest-icon">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                </div>
                <h3>Economics</h3>
                <p>Applying mathematical regression models to tracking macro markets, pricing, and consumer behaviors.</p>
            </div>
            <div class="interest-card">
                <div class="interest-icon">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                </div>
                <h3>Physics</h3>
                <p>Studying thermodynamic mechanics and natural structural principles to build abstract mathematical frameworks.</p>
            </div>
        </div>
    </section>

    <section id="project" class="reveal">
        <div class="section-header">
            <h2>Featured Independent Project</h2>
            <p>Showcasing empirical investigation methods and academic output</p>
        </div>
        <div class="project-showcase">
            <div class="project-main">
                <span class="project-tag">Mathematics for Economics Research</span>
                <h3>“The Prediction of Consumer Spending”</h3>
                <p class="project-description">
                    An independent research project exploring consumer behaviors through empirical macroeconomic trends. By framing complex spending indices as measurable metrics, I formulated a predictive framework evaluating market elasticity.
                </p>
                <div class="project-steps">
                    <div class="step">
                        <div class="step-num">1</div>
                        <div class="step-text">
                            <h4>Academic Literature Synthesis</h4>
                            <p>Reviewed classical economic literature and foundational peer-reviewed studies to structure hypotheses.</p>
                        </div>
                    </div>
                    <div class="step">
                        <div class="step-num">2</div>
                        <div class="step-text">
                            <h4>Multiple Linear Regression Modelling</h4>
                            <p>Utilized multiple linear regression models to analyze compounding variables altering market parameters.</p>
                        </div>
                    </div>
                    <div class="step">
                        <div class="step-num">3</div>
                        <div class="step-text">
                            <h4>Data Calculation & Drafting</h4>
                            <p>Leveraged Excel computational environments to run regressions, track coefficients, and finalize the essay.</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="project-sidebar">
                <div class="sidebar-block">
                    <h4>Skills Developed</h4>
                    <div class="tech-pills">
                        <span class="pill">Multiple Linear Regression</span>
                        <span class="pill">Excel Matrix Operations</span>
                        <span class="pill">Literature Review</span>
                        <span class="pill">Quantitative Analysis</span>
                        <span class="pill">Academic Writing</span>
                    </div>
                </div>
                <div class="metric-card">
                    <div class="metric-title">Project Output</div>
                    <div class="metric-value">Independent Research Essay & Certification</div>
                </div>
            </div>
        </div>
    </section>

    <section id="awards" class="reveal">
        <div class="section-header">
            <h2>Awards & Achievements</h2>
            <p>National and international honors validating academic commitment</p>
        </div>
        <div class="awards-grid">
            <div class="award-card">
                <div class="award-badge">★</div>
                <div class="award-info">
                    <div class="award-scope">Global Gold</div>
                    <h3>SMC (Senior Mathematical Challenge)</h3>
                    <p class="award-desc">Achieved top-tier global placement demonstrating fast, innovative algorithmic problem-solving.</p>
                </div>
            </div>
            <div class="award-card">
                <div class="award-badge">★</div>
                <div class="award-info">
                    <div class="award-scope">Merit Distinction</div>
                    <h3>BMO (British Mathematical Olympiad) Round 1</h3>
                    <p class="award-desc">Recognized for advanced mastery over proof-oriented problems and theoretical mathematics.</p>
                </div>
            </div>
            <div class="award-card silver">
                <div class="award-badge">★</div>
                <div class="award-info">
                    <div class="award-scope">Global Silver</div>
                    <h3>SPC (Senior Physics Challenge)</h3>
                    <p class="award-desc">Earned high recognition for quantitative problem-solving under competitive parameters.</p>
                </div>
            </div>
            <div class="award-card bronze">
                <div class="award-badge">★</div>
                <div class="award-info">
                    <div class="award-scope">Global Bronze</div>
                    <h3>Physics Bowl</h3>
                    <p class="award-desc">Placed among global leaders evaluating physics mechanics and advanced conceptual reasoning.</p>
                </div>
            </div>
            <div class="award-card silver">
                <div class="award-badge">★</div>
                <div class="award-info">
                    <div class="award-scope">National Silver</div>
                    <h3>UKChO (UK Chemistry Olympiad)</h3>
                    <p class="award-desc">Demonstrated strong critical thinking and chemical logic under rigorous conditions.</p>
                </div>
            </div>
            <div class="award-card program">
                <div class="award-badge">◆</div>
                <div class="award-info">
                    <div class="award-scope">Academic Program</div>
                    <h3>Oxcom Research Summer School 2026</h3>
                    <p class="award-desc">Selected participant, immersing in advanced concepts and collaborative scholarly research workflows.</p>
                </div>
            </div>
            <div class="award-card program" style="grid-column: span 1;">
                <div class="award-badge">✓</div>
                <div class="award-info">
                    <div class="award-scope">Internal Assessment</div>
                    <h3>Mock Examination Results</h3>
                    <p class="award-desc">Ranked securely within the Top 5% of class cohort, verifying ongoing consistency.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="activities" class="reveal">
        <div class="section-header">
            <h2>Clubs & Extracurricular Activities</h2>
            <p>Cultivating leadership, deep intellectual curiosity, and holistic development</p>
        </div>
        <div class="activities-layout">
            <div class="activity-card">
                <div class="activity-header">
                    <h3>Badminton Club</h3>
                    <span class="activity-date">2024.07 – Present</span>
                </div>
                <p>Refining personal reflexes, dynamic motor responses, and long-term stamina. Active engagement reinforces physical health alongside strategy preparation within collective teams.</p>
            </div>
            <div class="activity-card">
                <div class="activity-header">
                    <h3>Physics Club</h3>
                    <span class="activity-date">2026.01 – 2026.06</span>
                </div>
                <p>Collaborated on foundational experiments, reviewing deep conceptual inquiries outside standard mechanics to explore real-world scientific solutions.</p>
            </div>
            <div class="activity-card" style="grid-column: 1 / -1; margin-bottom: 8px;">
                <div class="activity-header">
                    <h3>Drama & School Art Festival Performance</h3>
                    <span class="activity-date">Art Festival Contributor</span>
                </div>
                <p>Participated in collaborative team productions, sharpening expressive presentation skills, narrative empathy, and operational flexibility under live parameters.</p>
            </div>
            <div class="featured-experience">
                <h4>
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 20 20"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"></path></svg>
                    Highlight Experience: Mathematics Club (2024.09 – 2025.01)
                </h4>
                <p>
                    This collaborative environment served as a primary outlet for advanced exploration. I regularly led and participated in deep discussions regarding Game Theory matrices and foundational Number Theory. This space allowed me to present abstract methodologies, exchange peer critiques, and confidently face multi-layered theories far beyond textbook requirements.
                </p>
            </div>
        </div>
    </section>

    <section id="skills" class="reveal">
        <div class="section-header">
            <h2>Core Competencies</h2>
            <p>The technical frameworks, research proficiencies, and personal qualities I build upon</p>
        </div>
        <div class="skills-grid">
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Quantitative Reasoning</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Research Methodology</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Excel Data Operations</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Critical Thinking</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Problem Solving</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Goal Setting</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Self-Discipline</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Time Management</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Peer Knowledge Sharing</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Team Collaboration</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Reliability & Ownership</span></div>
            <div class="skill-tag-card"><div class="skill-dot"></div><span>Academic Curiosity</span></div>
        </div>
    </section>

    <section class="reveal">
        <div class="goals-box">
            <h3>Future Vision & Objectives</h3>
            <p>
                My goal is to dive deep into an elite university Statistics and Data Science curriculum, gaining mastery over advanced inference modeling and big data engineering. Ultimately, I aim to excel as a Data Analyst, transforming unstructured data arrays into actionable strategic insights that empower precision decision-making in socio-economic domains.
            </p>
        </div>
    </section>

    <section id="contact" class="reveal">
        <div class="section-header">
            <h2>Contact & Inquiries</h2>
            <p>Let's connect to discuss academic research opportunities and data collaborations</p>
        </div>
        <div class="contact-grid">
            <div class="contact-info">
                <div class="contact-text">
                    <p>
                        I am highly receptive to academic inquiries, research partnerships, and data analysis discussions. Feel free to contact me via the placeholder channels provided below.
                    </p>
                </div>
                <div class="contact-links">
                    <div class="contact-item">
                        <div class="contact-icon-wrapper">✉</div>
                        <div class="contact-details">
                            <h4>Email Address</h4>
                            <p>r.qian.portfolio@example.edu</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon-wrapper">🔗</div>
                        <div class="contact-details">
                            <h4>Professional Networks</h4>
                            <p>linkedin.com/in/rain-qian-placeholder</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon-wrapper">📂</div>
                        <div class="contact-details">
                            <h4>Code Repositories</h4>
                            <p>github.com/rainqian-data-science</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="contact-form">
                <form id="portfolioContactForm" onsubmit="event.preventDefault(); alert('Thank you for your message! This form serves as a front-end framework demonstration.');">
                    <div class="form-group">
                        <label for="form-name">Full Name</label>
                        <input type="text" id="form-name" placeholder="Your Name" required>
                    </div>
                    <div class="form-group">
                        <label for="form-email">Institutional Email</label>
                        <input type="email" id="form-email" placeholder="yourname@institution.com" required>
                    </div>
                    <div class="form-group">
                        <label for="form-msg">Message / Inquiry Scope</label>
                        <textarea id="form-msg" rows="5" placeholder="Outline the nature of your academic or institutional inquiry..." required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary">Transmit Inquiry</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Rain Junyu Qian. All Rights Reserved.</p>
        <p class="footer-note">Designed exclusively as an undergraduate portfolio platform | Class AS-1</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            /* --- Mobile Menu Interaction Logic --- */
            const menuToggle = document.getElementById('menuToggle');
            const navLinks = document.getElementById('navLinks');
            
            menuToggle.addEventListener('click', () => {
                navLinks.classList.toggle('open');
                // Simple accessibility/visual transformation feedback
                const spans = menuToggle.querySelectorAll('span');
                spans.forEach(span => span.style.backgroundColor = navLinks.classList.contains('open') ? '#3b82f6' : '#0f172a');
            });

            // Auto-collapse navigation panel upon item route execution
            document.querySelectorAll('.nav-item').forEach(link => {
                link.addEventListener('click', () => {
                    navLinks.classList.remove('open');
                });
            });

            /* --- Header Mutation on Scrolling Run --- */
            const navbar = document.getElementById('navbar');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 20) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classList.remove('scrolled');
                }
            });

            /* --- Scroll Reveal Framework via Intersection Observer --- */
            const revealElements = document.querySelectorAll('.reveal');
            const revealObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        // Unobserve after activation to guarantee performance stability
                        revealObserver.unobserve(entry.target);
                    }
                });
            }, {
                root: null,
                threshold: 0.12, // Activates when 12% of the component becomes visible
                rootMargin: "0px 0px -40px 0px"
            });

            revealElements.forEach(element => {
                revealObserver.observe(element);
            });

            /* --- Active Navigation Link Highlighting Mechanics --- */
            const sections = document.querySelectorAll('section[id]');
            const activeObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const id = entry.target.getAttribute('id');
                        document.querySelectorAll('.nav-item').forEach(navItem => {
                            navItem.classList.remove('active');
                            if (navItem.getAttribute('href') === `#${id}`) {
                                navItem.classList.add('active');
                            }
                        });
                    }
                });
            }, {
                root: null,
                threshold: 0.4, // Highlights item when section reaches 40% screen coverage
                rootMargin: "-20% 0px -40px 0px"
            });

            sections.forEach(section => {
                activeObserver.observe(section);
            });
        });
    </script>
</body>
</html>

```
