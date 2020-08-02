<script>
  import { Router, link } from 'svelte-routing';
</script>

<style>
  #title {
    text-decoration: underline;
  }
  #nav-bar {
    width: 100%;
    margin-top: 2.5rem;
  }
  #nav-items {
    display: flex;
    justify-content: space-between;
    list-style-type: none;
  }
  #route-links {
    display: flex;
    justify-content: space-evenly;
    width: 50%;
    font-size: 1.5rem;
  }
</style>

<main>
  <nav id="nav-bar">
    <ul id="nav-items">
      <li id="nav-links">
        <a href="/">
          <h1 id="title">FULL STACK WEB DEVELOPER</h1>
        </a>
        <p>Currently seeking employment</p>
      </li>

      <li id="route-links">
        <a href="/skills">SKILLS</a>
        <a href="/project">PROJECTS</a>
        <a href="/contact">CONTACT</a>
      </li>
    </ul>
  </nav>
</main>
