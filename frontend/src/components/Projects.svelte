<script>
  import { onMount } from "svelte";
  import logo from "/crackd1.png";
  import logo2 from "/crackd2.png";

  let projects = [
    {
      title: "100 Days of ML",
      url: "https://twitter.com/cmoorelabs/status/1821251020896530828",
      description: "Daily progress on machine learning concepts and projects.",
      tag: "personal",
      embedType: "twitter",
    },
    {
      title: "crackdTA - Intelligent Study Assistant",
      url: "https://crackdta.com",
      description:
        "Comprehensive study aid tool with features like note-taking, multimedia embedding, real-time collaboration, and AI-powered quizzes.",
      tag: "personal",
    },
    {
      title: "Github Repo Reader",
      url: "https://github.com/cmooredev/RepoReader",
      description: "NLP-powered code search and analysis tool",
      tag: "personal",
      embedType: "youtube",
      embedId: "gz9-QhpwYTs",
    },
    {
      title: "Multiplayer Browser Game",
      url: "https://www.youtube.com/playlist?list=PLx9e6Ldz3n4kXS5h-oM8wm1TVw1mn9S8n",
      description:
        "Series on creating a multiplayer browser game using Svelte, Express, Socket.IO, and MongoDB.",
      tag: "personal",
      embedType: "youtube",
      embedId: "videoseries?list=PLx9e6Ldz3n4kXS5h-oM8wm1TVw1mn9S8n",
      details: [
        "Features include multiplayer sessions, game rooms for 2 players, and auto-matching.",
        "Implements enemy waves, boss fights, weapon upgrades, and highscores.",
      ],
    },
  ];

  let currentImageIndex = 0;
  const images = [logo, logo2];

  function nextImage() {
    currentImageIndex = (currentImageIndex + 1) % images.length;
  }

  function prevImage() {
    currentImageIndex = (currentImageIndex - 1 + images.length) % images.length;
  }

  onMount(() => {
    const script = document.createElement("script");
    script.src = "https://platform.twitter.com/widgets.js";
    script.async = true;
    document.body.appendChild(script);
  });
</script>

<section id="projects">
  <h2>Projects</h2>
  <ul>
    {#each projects.filter((p) => p.tag === "current") as project}
      <li>
        <a class="project-link" href={project.url} target="_blank"
          >{project.title}</a
        >
        <br />
        <i>{project.description}</i>
      </li>
    {/each}
  </ul>
  <ul>
    {#each projects.filter((p) => p.tag === "personal") as project}
      <li>
        <a class="project-link" href={project.url} target="_blank"
          >{project.title}</a
        >
        <br />
        <i>{project.description}</i>

        {#if project.title === "crackdTA - Intelligent Study Assistant"}
          <div class="slideshow-container">
            <button
              on:click={prevImage}
              class="nav-button prev"
              aria-label="Previous image">&lt;</button
            >
            <div class="slideshow">
              <img src={images[currentImageIndex]} alt="crackdTA Feature" />
            </div>
            <button
              on:click={nextImage}
              class="nav-button next"
              aria-label="Next image">&gt;</button
            >
          </div>
        {/if}

        {#if project.embedType === "youtube"}
          <div class="youtube-embed-container">
            <iframe
              src="https://www.youtube.com/embed/{project.embedId}"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>
        {/if}

        {#if project.embedType === "twitter"}
          <div class="twitter-embed-container">
            <blockquote class="twitter-tweet">
              <a
                href="https://twitter.com/cmoorelabs/status/1821251020896530828"
              >
              </a>
            </blockquote>
          </div>
        {/if}
      </li>
    {/each}
  </ul>
</section>

<style>
  #projects {
    margin-top: 2rem;
  }

  .project-link {
    color: #0071e3;
    text-decoration: none;
    transition: color 0.2s ease;
    font-size: 1.5rem;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 2.5rem;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin-bottom: 1.5rem;
  }

  li {
    margin-bottom: 1.5rem;
    padding-bottom: 1.5rem;
    position: relative;
  }

  li:not(:last-child)::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 60%;
    height: 2px;
    background-color: rgba(0, 113, 227, 0.2);
  }

  a {
    color: #0071e3;
    text-decoration: none;
    transition: color 0.2s ease;
  }

  a:hover {
    color: #0077ed;
  }

  .twitter-embed-container {
    display: flex;
    justify-content: center;
    margin-top: 1rem;
  }

  .slideshow-container {
    display: flex;
    align-items: center;
    justify-content: center;
    max-width: 800px;
    margin: 2rem auto;
  }

  .slideshow {
    flex-grow: 1;
    margin: 0 1rem;
  }

  .slideshow img {
    width: 100%;
    height: auto;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .nav-button {
    background: none;
    border: none;
    font-size: 2rem;
    color: #0071e3;
    cursor: pointer;
    transition: color 0.2s ease;
    padding: 0.5rem;
  }

  .nav-button:hover {
    color: #0077ed;
  }

  .nav-button:focus {
    outline: none;
  }

  .youtube-embed-container {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 aspect ratio */
    height: 0;
    overflow: hidden;
    max-width: 100%;
    margin-top: 1rem;
  }

  .youtube-embed-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 2rem;
      margin-bottom: 1.5rem;
    }

    .slideshow-container {
      position: relative;
      display: block;
    }

    .slideshow {
      margin: 0;
    }

    .nav-button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0, 0, 0, 0.7);
      color: white;
      padding: 1rem;
      font-size: 1.8rem;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    }

    .prev {
      left: 10px;
    }
    .next {
      right: 10px;
    }
  }
</style>
