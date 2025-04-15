<script>
  // No imports needed for Font Awesome
</script>

<section id="contact">
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
  #contact {
    position: relative;
    margin: 3rem 0;
    text-align: left;
    padding-top: 1rem;
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
</style>
