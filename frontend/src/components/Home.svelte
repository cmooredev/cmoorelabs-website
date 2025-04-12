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
  <div class="hero-content">
    <h1 class="hero-title">Connor Moore</h1>
    <p class="role">
      Full Stack Engineer & <span class="highlight">ML Enthusiast</span>
    </p>
  </div>
  <div class="intro">
    <p>
      Hey! 👋 I build cool stuff with code, from <em>Web3 games</em> to
      <em>AI tools</em>
    </p>
    <p>
      Currently cooking up something exciting at <span class="highlight"
        >Auralocked Systems</span
      >
    </p>
    <div class="cta-buttons">
      <a href="#about" class="cta-button primary" on:click={scrollToSection}
        >See my work →</a
      >
      <a href="#contact" class="cta-button secondary" on:click={scrollToSection}
        >Let's talk</a
      >
    </div>
  </div>
</section>

<section id="about">
  <h2>About Me</h2>
  <div class="about-content">
    <p>
      I love turning complex problems into elegant solutions. Whether it's
      building <em>data pipelines</em>, <em>ML systems</em>, or creating
      <em>user interfaces</em>, I'm all about making tech that actually helps
      people get things done.
    </p>
    <p>
      These days, I'm diving deeper into <strong>backend architecture</strong>
      and
      <strong>machine learning</strong>, while running
      <span class="highlight">Auralocked Systems</span> where we help local businesses
      level up their tech game.
    </p>
    <div class="skills">
      <h3>What I Work With</h3>
      <ul>
        <li>Python</li>
        <li>React/Next.js</li>
        <li>TypeScript</li>
        <li>FastAPI</li>
        <li>AWS</li>
        <li>Machine Learning</li>
      </ul>
    </div>
  </div>
</section>

<section id="auralocked">
  <div class="auralocked-header">
    <img
      src={auralockedLogo}
      alt="Auralocked Systems Logo"
      class="auralocked-logo"
    />
    <h2>Auralocked Systems</h2>
  </div>
  <div class="auralocked-content">
    <div class="value-prop">
      <h3>Looking for enterprise-grade tech solutions?</h3>
      <p>
        At Auralocked, we transform businesses in Simi Valley with custom tech
        solutions that actually pay for themselves. From automation to cloud
        infrastructure, we're your local tech partner that gets results.
      </p>
    </div>
    <div class="features">
      <div class="feature">
        <h4>Same-Day Response</h4>
        <p>Tech issues solved fast</p>
      </div>
      <div class="feature">
        <h4>Fixed Monthly Rates</h4>
        <p>No surprise bills</p>
      </div>
      <div class="feature">
        <h4>No Contracts</h4>
        <p>Stay because you want to</p>
      </div>
    </div>
    <div class="cta-container">
      <a
        href="https://auralocked.com"
        target="_blank"
        class="cta-button primary">Schedule a Free Consultation →</a
      >
      <p class="cta-subtext">or call (805) 304-3858</p>
    </div>
  </div>
</section>

<section id="community">
  <h2>Let's Connect</h2>
  <div class="community-content">
    <div class="community-intro">
      <p>
        Follow my journey building AI tools, Web3 games, and tech solutions. I
        share insights about machine learning, development tips, and
        behind-the-scenes of my projects.
      </p>
    </div>
    <div class="community-links">
      <a
        href="https://github.com/cmooredev"
        target="_blank"
        class="social-link github"
      >
        <i class="fab fa-github"></i>
        <div class="social-text">
          <h4>GitHub</h4>
          <p>Open source projects</p>
        </div>
      </a>
      <a
        href="https://twitter.com/cmoorelabs"
        target="_blank"
        class="social-link twitter"
      >
        <i class="fab fa-twitter"></i>
        <div class="social-text">
          <h4>Twitter</h4>
          <p>Dev updates & insights</p>
        </div>
      </a>
      <a
        href="https://www.linkedin.com/in/connor-moore-b821a017b/"
        target="_blank"
        class="social-link linkedin"
      >
        <i class="fab fa-linkedin"></i>
        <div class="social-text">
          <h4>LinkedIn</h4>
          <p>Professional network</p>
        </div>
      </a>
      <a
        href="https://cmoorelabs.substack.com"
        target="_blank"
        class="social-link blog"
      >
        <i class="fas fa-pen-fancy"></i>
        <div class="social-text">
          <h4>Blog</h4>
          <p>Tech writing & tutorials</p>
        </div>
      </a>
    </div>
  </div>
</section>

<style>
  #home {
    text-align: center;
    padding: 0;
    height: calc(100vh - 2rem);
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 0;
  }

  #home p {
    font-size: 1.25rem;
    color: #86868b;
  }

  .hero-content {
    margin-top: 0px;
    top: 0;
  }

  .hero-title {
    font-size: 4rem;
    margin-bottom: 0.5rem;
    color: #333;
  }

  .role {
    font-size: 2rem;
    font-weight: 600;
    color: #0071e3;
    margin-bottom: 2rem;
  }

  .intro p {
    max-width: 600px;
    margin: 0.5rem auto;
    color: #86868b;
  }

  #about,
  #auralocked,
  #community {
    position: relative;
    margin: 6rem 0;
    text-align: left;
    padding-top: 4rem;
  }

  #about::before,
  #auralocked::before,
  #community::before {
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

  h2 {
    font-size: 2rem;
    margin-bottom: 2.5rem;
    color: #333;
    text-align: center;
  }

  h3 {
    font-size: 1.5rem;
    margin: 1.5rem 0 1rem;
    color: #333;
  }

  .about-content,
  .auralocked-content {
    max-width: 800px;
    margin: 0 auto;
  }

  .about-content p,
  .auralocked-content p {
    margin-bottom: 1rem;
    line-height: 1.6;
    color: #444;
    font-size: 1.1rem;
  }

  .skills ul {
    list-style: none;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .skills li {
    background: #f5f5f7;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    font-size: 0.9rem;
    color: #666;
  }

  .features {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
    margin: 2rem 0;
  }

  .feature {
    background: #f5f5f7;
    padding: 2rem;
    border-radius: 12px;
    text-align: center;
    transition: transform 0.2s ease;
  }

  .feature:hover {
    transform: translateY(-5px);
  }

  .feature h4 {
    margin: 0 0 0.5rem 0;
    color: #333;
    font-size: 1.2rem;
  }

  .feature p {
    margin: 0;
    color: #666;
    font-size: 0.9rem;
  }

  .cta-buttons {
    display: flex;
    gap: 1rem;
    margin-top: 2rem;
    justify-content: center;
  }

  .cta-button {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border-radius: 25px;
    font-weight: 500;
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
    .hero-title {
      font-size: 2.5rem;
    }

    .role {
      font-size: 1.25rem;
    }

    .intro p {
      font-size: 0.9rem;
    }

    #home {
      max-height: -webkit-fill-available;
    }

    .features {
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .cta-buttons {
      flex-direction: column;
    }

    .value-prop h3 {
      font-size: 1.5rem;
    }
  }

  #community {
    margin: 4rem 0;
    text-align: left;
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

  .skills h3 {
    text-align: center;
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
