<script>
  import { Router, link } from "svelte-routing";
</script>

<style>
  #nav-bar {
    background-color: #15202b;
    height: 95px;
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
  #route-links {
    display: flex;
    justify-content: space-around;
    width: 100%;
  }
  #title {
    text-decoration: underline;
  }
</style>

<nav id="nav-bar">
  <ul id="nav-items">
    <li id="route-links">
      <h5 id="title">
        <a href="/">Full stack web developer</a>
      </h5>

      <h5>
        <a href="/skills">SKILLS</a>
      </h5>

      <h5>
        <a href="/project">PROJECTS</a>
      </h5>

      <h5>
        <a href="/contact">CONTACT</a>
      </h5>
    </li>
  </ul>
</nav>
