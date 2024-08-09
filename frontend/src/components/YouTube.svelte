<script>
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
</script>

<section id="youtube">
  <h2>Educational Content</h2>
  {#each youtubeProjects as project}
    <div class="youtube-project">
      <h3>{project.title}</h3>
      <div class="video-container">
        <iframe
          width="560"
          height="315"
          src="https://www.youtube.com/embed/videoseries?list={project.playlistId}"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
      <ul>
        {#each project.description as point}
          <li>{point}</li>
        {/each}
      </ul>
    </div>
  {/each}
</section>

<style>
  #youtube {
    margin-top: 2rem;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 2.5rem;
  }

  .youtube-project {
    margin-bottom: 2rem;
  }

  h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  .video-container {
    position: relative;
    padding-bottom: 56.25%;
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

  ul {
    list-style-type: disc;
    padding-left: 20px;
    margin-top: 1rem;
  }

  li {
    margin-bottom: 0.5rem;
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 2rem;
      margin-bottom: 1.5rem;
    }
  }
</style>
