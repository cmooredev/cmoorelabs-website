<script>
  // No imports needed for Font Awesome
</script>

<section id="contact">
  <h2>Contact</h2>
  <p>Feel free to reach out to me on any of these platforms:</p>
  <ul>
    <li>
      <a
        href="https://twitter.com/cmoorelabs"
        target="_blank"
        aria-label="Twitter"
      >
        <i class="fab fa-twitter"></i>
        <span>Twitter</span>
      </a>
    </li>
    <li>
      <a
        href="https://github.com/cmooredev"
        target="_blank"
        aria-label="GitHub"
      >
        <i class="fab fa-github"></i>
        <span>GitHub</span>
      </a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/connor-moore-b821a017b/"
        target="_blank"
        aria-label="LinkedIn"
      >
        <i class="fab fa-linkedin"></i>
        <span>LinkedIn</span>
      </a>
    </li>
    <li>
      <a href="mailto:connor@cmoorelabs.com" aria-label="Email">
        <i class="fas fa-envelope"></i>
        <span>Email</span>
      </a>
    </li>
  </ul>
</section>

<style>
  #contact {
    margin-top: 1rem;
    margin-bottom: 1rem;
    text-align: center;
    width: 100%;
  }

  h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
  }

  p {
    margin-bottom: 2rem;
    font-size: 1.1rem;
  }

  ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    justify-content: center;
    gap: 2rem;
    flex-wrap: wrap;
  }

  li {
    margin-bottom: 0.5rem;
  }

  a {
    color: #0071e3;
    text-decoration: none;
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    width: 50px;
    height: 50px;
    justify-content: center;
  }

  a:hover {
    color: #0077ed;
    background-color: #e5e5e7;
    transform: translateY(-3px);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  a span {
    margin-top: 0.5rem;
    font-size: 0.9rem;
  }

  i {
    font-size: 24px;
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    ul {
      gap: 1rem;
    }

    a {
      padding: 0.75rem;
      width: 50px;
      height: 50px;
    }
  }
</style>
