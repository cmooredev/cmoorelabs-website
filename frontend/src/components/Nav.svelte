<script>
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

<nav>
  <div class="logo">cmoorelabs</div>
  <div class="nav-links">
    <a href="#home" on:click={scrollToSection}>Home</a>
    <a href="#auralocked" on:click={scrollToSection}>Auralocked</a>
    <a href="#contact" on:click={scrollToSection}>Contact</a>
  </div>
</nav>

<style>
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

  @media (max-width: 768px) {
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
  }
</style>
