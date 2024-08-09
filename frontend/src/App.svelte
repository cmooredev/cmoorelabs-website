<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./components/Home.svelte";
  import Projects from "./components/Projects.svelte";
  import Experience from "./components/Experience.svelte";
  import Contact from "./components/Contact.svelte";
</script>

<main>
  <Nav />
  <Home />
  <hr />
  <Projects />
  <hr />
  <Contact />
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

  hr {
    border: 0;
    height: 5px;
    background-color: #e0e0e0;
    margin: 2rem 0;
  }

  @media (max-width: 768px) {
    main {
      padding: 0 1rem;
    }
  }
</style>
