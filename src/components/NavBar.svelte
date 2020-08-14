<script>
  import { Router, link } from "svelte-routing";
</script>

<style>
  #title {
    text-decoration: underline;
  }
  #nav-bar {
    background-color: #21367f;
    height: 50px;
    display: flex;
    align-items: center;
  }
  #nav-items {
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style-type: none;
    width: 100%;
  }
  #nav-links {
    width: 50%;
  }

  #route-links {
    display: flex;
    justify-content: space-evenly;
    width: 25%;
    font-size: 1rem;
  }
</style>

<nav id="nav-bar">
  <ul id="nav-items">
    <li id="nav-links">
      <a href="/">
        <h5 id="title">FULL STACK WEB DEVELOPER</h5>
      </a>
    </li>

    <li id="route-links">
      <a href="/skills">SKILLS</a>
      <a href="/project">PROJECTS</a>
      <a href="/contact">CONTACT</a>
    </li>
  </ul>
</nav>
