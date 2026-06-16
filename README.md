# index.html
my personal website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Jinru Li | Student Portfolio</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      color: #1f2937;
      background: #f8fafc;
    }

    header {
      background: white;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 10px rgba(0,0,0,0.06);
    }

    nav {
      max-width: 1100px;
      margin: auto;
      padding: 16px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-weight: bold;
      font-size: 1.3rem;
      color: #2563eb;
    }

    nav a {
      margin-left: 20px;
      text-decoration: none;
      color: #374151;
      font-weight: 500;
    }

    nav a:hover {
      color: #2563eb;
    }

    .hero {
      min-height: 85vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 60px 24px;
      background: linear-gradient(135deg, #eff6ff, #f5f3ff);
    }

    .hero h1 {
      font-size: 3rem;
      margin-bottom: 16px;
      color: #111827;
    }

    .hero p {
      font-size: 1.2rem;
      max-width: 700px;
      margin: auto;
      color: #4b5563;
    }

    .btn {
      display: inline-block;
      margin-top: 28px;
      padding: 12px 24px;
      background: #2563eb;
      color: white;
      border-radius: 999px;
      text-decoration: none;
      font-weight: bold;
    }

    .btn:hover {
      background: #1d4ed8;
    }

    section {
      max-width: 1100px;
      margin: auto;
      padding: 70px 24px;
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 24px;
      color: #111827;
    }

    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 24px;
    }

    .card {
      background: white;
      padding: 24px;
      border-radius: 18px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.06);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 30px rgba(0,0,0,0.1);
    }

    .card h3 {
      margin-bottom: 10px;
      color: #2563eb;
    }

    ul {
      padding-left: 20px;
    }

    .contact {
      text-align: center;
      background: #111827;
      color: white;
      border-radius: 24px;
    }

    .contact h2 {
      color: white;
    }

    footer {
      text-align: center;
      padding: 24px;
      color: #6b7280;
    }

    @media (max-width: 700px) {
      nav {
        flex-direction: column;
      }

      nav a {
        display: inline-block;
        margin: 8px;
      }

      .hero h1 {
        font-size: 2.2rem;
      }
    }
  </style>
</head>
<body>

  <header>
    <nav>
      <div class="logo">Jinru Li</div>
      <div>
        <a href="#about">About</a>
        <a href="#interests">Interests</a>
        <a href="#projects">Projects</a>
        <a href="#achievements">Achievements</a>
        <a href="#contact">Contact</a>
      </div>
    </nav>
  </header>

  <section class="hero">
    <div>
      <h1>Hi, I’m Jinru Li</h1>
      <p>
        A Grade 11 student passionate about science, especially physics.
        I enjoy exploring how the universe works, solving challenging problems,
        and developing my academic interests for future university study.
      </p>
      <a href="#about" class="btn">View My Portfolio</a>
    </div>
  </section>

  <section id="about">
    <h2>About Me</h2>
    <div class="card">
      <p>
        I am a Grade 11 student with a strong interest in science and physics.
        My academic journey has helped me develop curiosity, discipline, and
        problem-solving skills. I am especially interested in understanding
        physical laws, scientific reasoning, and how scientific ideas can be
        applied to real-world problems.
      </p>
    </div>
  </section>

  <section id="interests">
    <h2>Academic Interests</h2>
    <div class="card-grid">
      <div class="card">
        <h3>Physics</h3>
        <p>
          I am deeply interested in physics because it explains the fundamental
          principles behind motion, energy, forces, light, electricity, and the universe.
        </p>
      </div>
      <div class="card">
        <h3>Science</h3>
        <p>
          I enjoy studying science because it encourages curiosity, evidence-based
          thinking, and logical problem solving.
        </p>
      </div>
      <div class="card">
        <h3>Problem Solving</h3>
        <p>
          I like approaching difficult questions step by step and finding clear,
          logical solutions.
        </p>
      </div>
    </div>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <div class="card-grid">
      <div class="card">
        <h3>Physics Research Project</h3>
        <p>
          A placeholder project exploring a physics topic such as forces, energy,
          waves, or electricity.
        </p>
      </div>
      <div class="card">
        <h3>Science Presentation</h3>
        <p>
          A placeholder presentation explaining a scientific concept clearly to
          classmates or a wider audience.
        </p>
      </div>
      <div class="card">
        <h3>Data Analysis Project</h3>
        <p>
          A placeholder project involving collecting data, analyzing results,
          and presenting scientific conclusions.
        </p>
      </div>
    </div>
  </section>

  <section id="skills">
    <h2>Skills</h2>
    <div class="card-grid">
      <div class="card">
        <h3>Academic Skills</h3>
        <ul>
          <li>Scientific reasoning</li>
          <li>Problem solving</li>
          <li>Analytical thinking</li>
        </ul>
      </div>
      <div class="card">
        <h3>Personal Skills</h3>
        <ul>
          <li>Curiosity</li>
          <li>Discipline</li>
          <li>Independent learning</li>
        </ul>
      </div>
    </div>
  </section>

  <section id="achievements">
    <h2>Achievements</h2>
    <div class="card">
      <h3>IGCSE Results</h3>
      <p>
        Achieved <strong>5 A*</strong> grades in IGCSE, demonstrating strong
        academic performance and dedication to learning.
      </p>
    </div>
  </section>

  <section id="activities">
    <h2>Extracurricular Activities</h2>
    <div class="card">
      <p>
        Add your extracurricular activities here, such as science clubs,
        competitions, volunteering, reading, sports, music, or leadership roles.
      </p>
    </div>
  </section>

  <section id="contact" class="contact">
    <h2>Contact</h2>
    <p>Email: your.email@example.com</p>
    <p>Location: Add your city or country here</p>
  </section>

  <footer>
    <p>© 2026 Jinru Li. All rights reserved.</p>
  </footer>

</body>
</html>
