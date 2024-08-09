<script>
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
    <p class="role">Full Stack Developer</p>
  </div>
  <div class="intro">
    <p>Specializing in web and mobile applications.</p>
    <p>Currently: Lead Front End Developer at Merlyn Labs</p>
    <a href="#projects" class="cta-button" on:click={scrollToSection}
      >See My Projects</a
    >
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

  .cta-button {
    display: inline-block;
    padding: 0.75rem 1.2rem;
    border-radius: 25px;
    margin-top: 1rem;
    color: #0071e3;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  .cta-button:hover {
    color: #0077ed;
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
  }
</style>
