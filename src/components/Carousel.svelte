<script>
  import { fly, fade } from "svelte/transition";
  let src = "./assets/svg/royalblueHeader.svg";
  let project1 = "/assets/projects/jaems.png";
  let project2 = "/assets/projects/latte-site.jpg";
  let project3 = "/assets/projects/market.png";
  let previousSlide = "/assets/svg/back.svg";
  let nextSlide = "/assets/svg/next.svg";
  let name = "web-sites";

  const Projects = [project1, project2, project3];

  const projectSite = [
    { Jaemsound: "https://www.jaemsounds.com/" },
    { Latteluv: "https://latteluv.netlify.app/" },
    { MarketAve: "https://marketavenue.netlify.app/" },
  ];

  const git = [
    { Jaemsound: "https://github.com/LuisOcasio/Jaemsounds-Gatsby-WP-AWS" },
    { Latteluv: "https://github.com/LuisOcasio/latte-luv" },
    { MarketAve: "https://github.com/Lambda-School-Labs/quick-street-be" },
  ];

  const about = [
    {
      jaemsounds:
        "A Headless WordPress site created for a client in the music industry. This client wanted his music to be streamed and downloaded across various types of devices.   ",
    },
    {
      latteluv:
        "Single page application that gives its user a fast and snappy feel. This is possible because we are rendering our components and not having to retrieve data from a server.",
    },
    {
      marketavenue:
        "During an 8 week period I worked along 5 other developers and a UX designer to create 'Market Ave.'. An application that brings local vendors and locals closer.",
    },
  ];

  const tech = [
    { jaemsounds: ["Gatsby", "WordPress", "Graphql", "AWS amplify"] },
    { latteluv: ["React", "Sass"] },
    { marketavenue: ["React", "Express", "Node", "MongoDB"] },
  ];

  let index = 0;
  let slide = 0;

  $: view = Object.keys(projectSite[slide]);
  $: url = Object.values(projectSite[slide]);
  $: gits = Object.values(git[slide]);
  $: abouts = Object.values(about[slide]);
  $: techs = Object.values(tech[slide]);

  const next = () => {
    index = (index + 1) % Projects.length;
    slide = (slide + 1) % projectSite.length;
  };

  const previous = () => {
    if (index && slide) {
      index = (index - 1) % Projects.length;
      slide = (slide - 1) % projectSite.length;
    }
  };
</script>

<style>
  #carousel {
    height: 650px;
    display: flex;
    width: 100%;
    background-color: #15202b;
  }

  .slide {
    width: 50%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    height: 90%;
    padding: 1rem;
  }

  .slide_title {
    font-size: small;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }

  .carousel-image {
    width: 80%;
    height: 85%;
  }

  .previous_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 5%;
  }

  .previous {
    width: 60px;
    z-index: 1;
    padding: 0.5rem;
  }

  .next_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 5%;
  }

  .next {
    width: 60px;
    z-index: 1;
    padding: 0.5rem;
  }

  .project_buttons {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    margin-top: 2rem;
  }
  .code {
    background-color: #21367f;
    color: #fff;
    border: 2px solid #2dfafc;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  .view {
    color: #fff;
    border: 2px solid #2dfafc;
    background-color: #21367f;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  .text-wrapper {
    display: flex;
    justify-content: flex-end;
    width: 50%;
    border-left: 2px solid #d617bd;
  }
  .text-section {
    display: flex;
    flex-direction: column;
    padding: 1rem;
  }
  .section {
    height: 100%;
    display: flex;
    flex-direction: column;
    font-size: small;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    text-align: center;
    border-bottom: 2px solid #d617bd;
  }
  .section_paragraph {
    margin-bottom: 1rem;
  }
  .section_title {
    display: flex;
    align-items: center;
  }
  .tech_title {
    margin-top: 1rem;
  }
  .stack_list {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    font-size: small;
  }

  .stack_list_wrapper {
    height: 100%;
    width: 100%;
  }
</style>

<div id="carousel">
  <div class="previous_wrapper">
    <img
      class="previous"
      alt="go-back-arrow"
      src="{previousSlide}"
      on:click="{previous}"
    />
  </div>

  <div class="slide">
    <section class="slide_title">
      <h5>{view}</h5>
    </section>

    {#each [Projects[index]] as src (index)} <img class="carousel-image"
    alt={name} {src} in:fly={{ x: -50, duration: 2000 }} /> {/each}
  </div>

  <div class="text-wrapper">
    <div class="text-section">
      <section class="section">
        <h5 class="section_title">About this project</h5>
        <p class="section_paragraph">
          {abouts}
        </p>
      </section>

      <section class="section">
        <h5 class="tech_title">Tech Stack used</h5>
        <div class="stack_list_wrapper">
          <ul class="stack_list">
            <li>{techs}</li>
          </ul>
        </div>
      </section>

      <div class="project_buttons">
        <a href="{gits}">
          <button class="code">Code</button>
        </a>
        <a href="{url}">
          <button class="view">View</button>
        </a>
      </div>
    </div>
  </div>
  <div class="next_wrapper">
    <img class="next" alt="next-arrow" src="{nextSlide}" on:click="{next}" />
  </div>
</div>
