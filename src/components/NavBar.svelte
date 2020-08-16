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
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    list-style-type: none;
    width: 100%;
    height: 100%;
  }
  #route-links {
    width: 50%;
    display: flex;
    justify-content: space-around;
  }
  #title {
    text-decoration: underline;
    width: 100%;
    text-align: center;
  }
</style>

<nav id="nav-bar">
  <ul id="nav-items">
    <a id="title" href="/">Full stack web developer</a>
    <li id="route-links">
      <a href="/skills">SKILLS</a>
      <a href="/project">PROJECTS</a>
      <a href="/contact">CONTACT</a>
    </li>
  </ul>
</nav>
