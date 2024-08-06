<script>
  let projects = [
    {
      title: "Merlyn Labs - Knights of the Ether",
      url: "https://mint.knightsoftheether.com",
      description:
        "Led front-end development of a Web3 trading card game. Implemented React components for game UI, integrated blockchain functionality, and optimized performance.",
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

  let youtubeProjects = [
    {
      title:
        "Building a Simple JavaScript Multiplayer Browser Game with Svelte and Socket.IO",
      playlistId: "PLx9e6Ldz3n4kXS5h-oM8wm1TVw1mn9S8n",
      description: [
        "Series on creating a multiplayer browser game using Svelte for the frontend, Express and Socket.IO for real-time multiplayer, and MongoDB for data persistence.",
        "Features include multiplayer sessions, game rooms for 2 players, and auto-matching.",
        "Implements enemy waves, boss fights, weapon upgrades, and highscores.",
      ],
    },
  ];

  function scrollToSection(event) {
    event.preventDefault();
    const target = event.target.getAttribute("href");

    const remValue =
      4 * parseFloat(getComputedStyle(document.documentElement).fontSize);

    if (target === "#home") {
      window.scrollTo({ top: 0, behavior: "smooth" });
    } else {
      const targetElement = document.querySelector(target);
      const offsetPosition =
        targetElement.getBoundingClientRect().top + window.scrollY - remValue;
      window.scrollTo({ top: offsetPosition, behavior: "smooth" });
    }
  }
</script>

<main>
  <nav>
    <div class="logo">cmoorelabs</div>
    <div class="nav-links">
      <a href="#home" on:click={scrollToSection}>Home</a>
      <a href="#experience" on:click={scrollToSection}>Experience</a>
      <a href="#projects" on:click={scrollToSection}>Projects</a>
      <a href="#contact" on:click={scrollToSection}>Contact</a>
    </div>
  </nav>

  <section id="home">
    <div class="hero-content">
      <h1 class="hero-title">Connor Moore</h1>
      <p class="role">Full Stack Developer</p>
    </div>
    <div class="intro">
      <p>Specializing in web and mobile applications.</p>
      <p>Currently: Lead Front End Developer at Merlyn Labs</p>
      <a href="#youtube" class="cta-button" on:click={scrollToSection}
        >Watch My Latest Video</a
      >
    </div>
  </section>

  <section id="experience">
    <h2>Experience</h2>
    <div class="job">
      <h3>Merlyn Labs - Lead Front End Developer</h3>
      <p class="date">July 2023 -- Present</p>
      <ul>
        <li>
          Designed and maintained front end of an online trading card game using
          React.
        </li>
        <li>Managed AWS infrastructure setup and maintenance.</li>
        <li>Improved automated workflows and testing.</li>
      </ul>
    </div>
    <div class="job">
      <h3>Stealth Startup - Full Stack Engineer</h3>
      <p class="date">June 2024 -- Present</p>
      <ul>
        <li>
          Led development of a mobile application using React Native and
          TypeScript.
        </li>
        <li>
          Engineered backend systems in Python, incorporating advanced data
          processing techniques.
        </li>
      </ul>
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

  <section id="youtube">
    <h2>Educational Content</h2>
    {#each youtubeProjects as project}
      <div class="video-container">
        <h3>{project.title}</h3>
        <iframe
          width="560"
          height="315"
          src="https://www.youtube.com/embed/videoseries?list={project.playlistId}"
          title={project.title}
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
        <ul>
          {#each project.description as point}
            <li>{point}</li>
          {/each}
        </ul>
      </div>
    {/each}
  </section>

  <section id="contact">
    <h2>Contact</h2>
    <p><a href="mailto:cmoorelabs@gmail.com">cmoorelabs@gmail.com</a></p>
    <p>
      <a href="https://github.com/cmooredev" target="_blank">GitHub</a>
      <a href="https://www.youtube.com/@cmoorelabs" target="_blank">YouTube</a>
      <a
        href="https://www.linkedin.com/in/connor-moore-b821a017b/"
        target="_blank">LinkedIn</a
      >
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
    background: rgba(255, 255, 255, 0.9);
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
    margin: 0;
    padding-bottom: 2rem;
    border-bottom: 1px solid #e0e0e0;
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
    font-size: 2.5rem;
    margin-bottom: 2.5rem;
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

  .hero-content {
    margin-top:0px;
    top: 0;
  }

  .intro p {
    max-width: 600px;
    margin: 0.5rem auto;
    color: #86868b;
  }

  #experience ul {
    list-style-type: disc;
    padding-left: 20px;
  }

  #experience li {
    margin-bottom: 0.5rem;
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

  #youtube ul {
    list-style-type: disc;
    padding-left: 20px;
  }

  #youtube li {
    margin-bottom: 0.5rem;
  }

  .cta-button {
  display: inline-block;
  background-color: #0071e3;
  color: white;
  padding: 0.75rem 1.2rem;
  border-radius: 25px;
  margin-top: 1rem;
  transition: background-color 0.2s ease;
}

  .cta-button:hover {
    background-color: #2c8dee;
    color: white;
  }

  .video-container {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 aspect ratio */
    height: 0;
    overflow: hidden;
    max-width: 100%;
  }

  .video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  @media (max-width: 768px) {

    main {
      padding: 0 1rem;
    }

    h1 {
      font-size: 2.5rem;
    }

    .role {
      font-size: 1.25rem;
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 1.5rem;
    }

    .intro p {
      font-size: 0.9rem;
    }

    .logo {
      display: none;
    }

    nav {
      justify-content: center;
    }

    .nav-links a {
      margin: 0.25rem;
      font-size: 1rem;
    }

    iframe {
      width: 100%;
    }

    #home {
      max-height: -webkit-fill-available;
    }
  }

</style>
