<script>
  import { Router, link } from 'svelte-routing';
</script>

<style>
  #nav-bar {
    width: 100%;
    margin-top: 2.5rem;
  }

  #nav-items {
    display: flex;
    justify-content: space-between;
    list-style-type: none;
  }
</style>

<main>
  <nav id="nav-bar">
    <ul id="nav-items">
      <li id="nav-links">
        <a href="/">
          <h1>FULL STACK WEB DEVELOPER</h1>
        </a>
      </li>

      <li>
        <a href="/skills">SKILLS</a>
        <a href="/project">PROJECTS</a>
        <a href="/contact">CONTACT</a>
      </li>
    </ul>
  </nav>
</main>
