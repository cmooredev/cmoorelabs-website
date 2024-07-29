<script>
  let projects = [
    {
      title: "Merlyn Labs - Knights of the Ether",
      url: "https://mint.knightsoftheether.com",
      description:
        "Lead Front End Engineer. Latest project: Web3 trading card game with blockchain integration", // Updated description
      tag: "current",
    },
    {
      title: "Github Repo Reader",
      url: "https://github.com/cmooredev/RepoReader",
      description: "NLP-powered code search and analysis tool",
      tag: "personal",
    },
    {
      title: "Discord Translation Bot",
      url: "https://github.com/cmooredev/Translator",
      description: "Multilingual communication facilitator",
      tag: "personal",
    },
  ];

  function scrollToSection(event) {
    event.preventDefault();
    const target = event.target.getAttribute("href");
    if (target === "#home") {
      window.scrollTo({ top: 0, behavior: "smooth" });
    } else {
      document.querySelector(target).scrollIntoView({ behavior: "smooth" });
    }
  }
</script>

<main>
  <nav>
    <div class="logo">cmoorelabs</div>
    <div class="nav-links">
      <a href="#home" on:click={scrollToSection}>Home</a>
      <a href="#projects" on:click={scrollToSection}>Projects</a>
      <a href="#contact" on:click={scrollToSection}>Contact</a>
    </div>
  </nav>

  <section id="home">
    <div class="hero-content">
      <h1>Connor Moore</h1>
      <p class="role">Full Stack Developer</p>
    </div>
    <div class="intro">
      <p>Building web solutions that work.</p>
      <p>Expertise: React, Node.js, TypeScript, GraphQL, AWS</p>
    </div>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <h3>Current Work</h3>
    <ul>
      {#each projects.filter((p) => p.tag === "current") as project}
        <li>
          <a href={project.url} target="_blank">{project.title}</a>
          <br />
          <i>{project.description}</i>
        </li>
      {/each}
    </ul>
    <h3>Personal Projects</h3>
    <ul>
      {#each projects.filter((p) => p.tag === "personal") as project}
        <li>
          <a href={project.url} target="_blank">{project.title}</a>
          <br />
          <i>{project.description}</i>
        </li>
      {/each}
    </ul>
  </section>

  <section id="contact">
    <h2>Contact</h2>
    <p><a href="mailto:cmoorelabs@gmail.com">cmoorelabs@gmail.com</a></p>
    <p>
      <a href="https://github.com/cmooredev" target="_blank">GitHub</a>
      <a href="https://www.youtube.com/@cmoorelabs" target="_blank">YouTube</a>
    </p>
  </section>
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    background-color: #ffffff;
    color: #1d1d1f;
    line-height: 1.5;
  }

  main {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 2rem;
  }

  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 0;
    position: sticky;
    top: 0;
    background: rgba(255, 255, 255, 0.8);
    backdrop-filter: blur(20px);
    z-index: 1000;
  }

  .logo {
    font-size: 1.25rem;
    font-weight: 600;
  }

  .nav-links a {
    color: #1d1d1f;
    text-decoration: none;
    margin-left: 2rem;
    font-weight: 400;
    transition: color 0.2s ease;
  }

  .nav-links a:hover {
    color: #0071e3;
  }

  section {
    margin: 6rem 0;
  }

  h1 {
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

  h2 {
    font-size: 2rem;
    font-weight: 600;
    margin-bottom: 2rem;
  }

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

  .intro p {
    max-width: 600px;
    margin: 0.5rem auto;
    color: #86868b;
  }

  #projects {
    margin-top: 2rem;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin-bottom: 1.5rem;
  }

  a {
    color: #0071e3;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  a:hover {
    color: #0077ed;
  }

  #contact p {
    margin-bottom: 0.5rem;
  }

  #contact a {
    margin-right: 1rem;
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 3rem;
    }

    .role {
      font-size: 1.5rem;
    }

    .intro p {
      font-size: 1rem;
    }
  }
</style>
