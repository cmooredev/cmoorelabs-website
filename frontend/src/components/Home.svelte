<script>
  import auralockedLogo from "/auralockedpngt.png";

  function scrollToSection(event) {
    event.preventDefault();
    const target = event.target.getAttribute("href");
    const targetElement = document.querySelector(target);
    const remValue =
      4 * parseFloat(getComputedStyle(document.documentElement).fontSize);
    const offsetPosition =
      targetElement.getBoundingClientRect().top + window.scrollY - remValue;
    window.scrollTo({ top: offsetPosition, behavior: "smooth" });
  }
</script>

<section id="home">
  <div class="hero-container">
    <div class="hero-left">
      <div class="hero-content">
        <h1 class="hero-title">Connor Moore</h1>
        <p class="role">Full Stack Developer</p>
        <div class="intro">
          <p>
            Building AI automation solutions at <span class="highlight"
              >Auralocked Systems</span
            >. I help businesses nationwide transform operations with custom AI,
            intelligent automation, and enterprise software.
          </p>
        </div>
      </div>
      <div class="cta-buttons">
        <a
          href="#auralocked"
          class="cta-button primary"
          on:click={scrollToSection}>See my work →</a
        >
        <a
          href="#lets-connect"
          class="cta-button secondary"
          on:click={scrollToSection}>Let's talk</a
        >
      </div>
    </div>

    <div class="hero-right">
      <div class="about-content">
        <h3>Full Stack Expertise</h3>
        <div class="specialties">
          <div class="specialty">
            <strong>Frontend</strong>
            <p>React, Svelte, TypeScript, responsive UI/UX</p>
          </div>
          <div class="specialty">
            <strong>Backend</strong>
            <p>Python, Node.js, APIs, databases</p>
          </div>
          <div class="specialty">
            <strong>DevOps & Cloud</strong>
            <p>AWS, CI/CD, infrastructure as code</p>
          </div>
        </div>
        <div class="skills">
          <h4>Tech Stack</h4>
          <ul>
            <li>React</li>
            <li>Python</li>
            <li>Node.js</li>
            <li>TypeScript</li>
            <li>PostgreSQL</li>
            <li>AWS</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  #home {
    text-align: center;
    padding: 0 1rem;
    min-height: calc(100vh - 2rem);
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  #home p {
    font-size: 1rem;
    color: #86868b;
    line-height: 1.6;
  }

  .hero-container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    max-width: 1000px;
    margin: 0 auto;
    align-items: start;
  }

  .hero-left {
    text-align: left;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-right: 2rem;
  }

  .hero-right {
    padding-left: 2rem;
    border-left: 1px solid #f5f5f7;
  }

  .hero-content {
    margin-bottom: 2rem;
  }

  .hero-title {
    font-size: 3rem;
    margin-bottom: 0.5rem;
    color: #333;
    font-weight: 600;
  }

  .role {
    font-size: 1.4rem;
    font-weight: 500;
    color: #0071e3;
    margin-bottom: 1.5rem;
  }

  .intro p {
    font-size: 1.1rem;
    line-height: 1.6;
    color: #444;
  }

  .about-content h3 {
    font-size: 1.6rem;
    color: #333;
    margin-bottom: 2rem;
    font-weight: 500;
  }

  .about-content h4 {
    font-size: 1.2rem;
    color: #333;
    margin: 2rem 0 1rem;
    font-weight: 500;
  }

  .specialties {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .specialty {
    display: flex;
    flex-direction: column;
    gap: 0.3rem;
  }

  .specialty strong {
    font-size: 1.1rem;
    color: #0071e3;
  }

  .specialty p {
    font-size: 0.95rem;
    color: #666;
    margin: 0;
  }

  .skills ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
  }

  .skills li {
    background: #f5f5f7;
    padding: 0.4rem 0.8rem;
    border-radius: 16px;
    font-size: 0.85rem;
    color: #666;
  }

  .cta-buttons {
    display: flex;
    gap: 1rem;
    margin: 2rem 0;
  }

  .cta-button {
    display: inline-block;
    padding: 0.6rem 1.2rem;
    border-radius: 20px;
    font-weight: 500;
    font-size: 0.9rem;
    transition: all 0.2s ease;
    text-decoration: none;
  }

  .cta-button.primary {
    background: #0071e3;
    color: white;
  }

  .cta-button.primary:hover {
    background: #0077ed;
    transform: translateY(-2px);
  }

  .cta-button.secondary {
    border: 2px solid #0071e3;
    color: #0071e3;
  }

  .cta-button.secondary:hover {
    background: #f5f5f7;
    transform: translateY(-2px);
  }

  .auralocked-header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1.5rem;
    margin-bottom: 2rem;
    text-align: center;
    width: 100%;
  }

  .auralocked-header h2 {
    margin-bottom: 0;
  }

  .auralocked-logo {
    width: 80px;
    height: 80px;
    object-fit: contain;
  }

  .value-prop {
    margin-bottom: 2rem;
  }

  .value-prop h3 {
    text-align: center;
    font-size: 1.8rem;
    margin-bottom: 1rem;
    color: #333;
  }

  .cta-container {
    text-align: center;
    margin-top: 3rem;
  }

  .cta-subtext {
    margin-top: 1rem;
    color: #666;
    font-size: 0.9rem;
  }

  @media (max-width: 768px) {
    .hero-container {
      grid-template-columns: 1fr;
      gap: 3rem;
      padding: 0 1.5rem;
    }

    .hero-left {
      text-align: center;
      padding-right: 0;
    }

    .hero-right {
      padding-left: 0;
      border-left: none;
      border-top: 1px solid #f5f5f7;
      padding-top: 3rem;
      text-align: left;
    }

    .hero-title {
      font-size: 2.2rem;
    }

    .role {
      font-size: 1.1rem;
    }

    .intro p {
      font-size: 1rem;
      max-width: 500px;
      margin: 0 auto;
    }

    .specialties {
      gap: 2rem;
      padding: 0 0.5rem;
    }

    .specialty {
      align-items: flex-start;
    }

    .skills {
      margin-top: 2.5rem;
    }

    .skills h4 {
      text-align: left;
    }

    .skills ul {
      justify-content: flex-start;
      margin-top: 1rem;
    }

    .cta-buttons {
      justify-content: center;
      margin-top: 2.5rem;
    }

    #home {
      padding: 2rem 0;
    }
  }

  #lets-connect {
    position: relative;
    margin: 6rem 0;
    text-align: left;
    padding-top: 4rem;
  }

  #lets-connect::before {
    content: "";
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 150px;
    height: 4px;
    background: linear-gradient(90deg, transparent, #0071e3, transparent);
    border-radius: 2px;
  }

  .community-intro {
    max-width: 600px;
    margin-bottom: 2rem;
  }

  .community-intro p {
    font-size: 1.1rem;
    color: #444;
    line-height: 1.6;
  }

  .community-links {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
  }

  .social-link {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 1.5rem;
    background: #f5f5f7;
    border-radius: 12px;
    text-decoration: none;
    color: inherit;
    transition: all 0.2s ease;
  }

  .social-link:hover {
    transform: translateY(-3px);
    background: #e5e5e7;
  }

  .social-link i {
    font-size: 1.5rem;
    color: #0071e3;
  }

  .social-text h4 {
    margin: 0;
    font-size: 1.1rem;
    color: #333;
  }

  .social-text p {
    margin: 0.2rem 0 0 0;
    font-size: 0.9rem;
    color: #666;
  }

  @media (max-width: 768px) {
    .community-links {
      grid-template-columns: 1fr;
    }

    .community-intro p {
      font-size: 1rem;
    }
  }

  .highlight {
    color: #0071e3;
  }

  em {
    font-style: italic;
  }

  strong {
    font-weight: 700;
  }
</style>
