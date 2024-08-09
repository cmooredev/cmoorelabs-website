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
      twitterEmbed: `<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Taking inspiration from <a href="https://twitter.com/wateriscoding?ref_src=twsrc%5Etfw">@wateriscoding</a> and starting my 100 day journey<br><br>day 1 of ml:<br> -basics of numpy<br> -used numpy to manipulate an image<br> -inversion, binary thresholding, rotations on sample image<br> -basic convolution function to perform edge detection with Sobel filters <a href="https://t.co/aTXQstsKG0">pic.twitter.com/aTXQstsKG0</a></p>&mdash; cmoorelabs (@cmoorelabs) <a href="https://twitter.com/cmoorelabs/status/1821251020896530828?ref_src=twsrc%5Etfw">August 7, 2024</a></blockquote>`,
    },
    {
      title: "crackdTA - Intelligent Study Assistant",
      url: "https://crackdta.com",
      description:
        "Developing a comprehensive study aid tool with features like note-taking, multimedia embedding, real-time collaboration, and AI-powered quizzes. Designed to enhance learning experiences and streamline study sessions.",
      tag: "personal",
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

        {#if project.twitterEmbed}
          <div class="twitter-embed-container">
            {@html project.twitterEmbed}
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
