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

  let index = 0;
  let slide = 0;

  $: view = Object.keys(projectSite[slide]);
  $: url = Object.values(projectSite[slide]);
  $: gits = Object.values(git[slide]);

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
  #project-title {
    text-align: center;
    color: #000;
  }
  #carousel-wrapper {
    height: 650px;
    display: flex;
    width: 100%;
    background-color: #2dfafc;
  }
  #carousel {
    width: 100%;
    display: flex;
    justify-content: space-evenly;

    align-items: center;
  }
  #carousel-slides {
    width: 50%;
    height: 450px;
    padding: 0.5rem;
    border-radius: 5px;
  }

  #previous {
    width: 50px;
    padding: 3rem;
    z-index: 1;
  }

  #next {
    width: 50px;
    padding: 3rem;
    z-index: 1;
  }

  #project_buttons {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 50%;
    height: 15%;
    margin-top: 0.5rem;
  }
  #code {
    background-color: #21367f;
    color: #fff;
    border: 4px solid #2dfafc;
    width: 90px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1rem;
  }
  #view {
    color: #fff;
    border: 4px solid #2dfafc;
    background-color: #15202b;
    width: 90px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1rem;
  }
  #text-wrapper {
    display: flex;
    justify-content: flex-end;
  }
  #text-section {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    border-left: 2px solid #d617bd;
    padding: 1.5rem;
    color: #000;
    align-items: center;
    text-align: center;
    margin-top: 1rem;
    margin-bottom: 1rem;
  }
  #section1 {
    border-bottom: 2px solid #d617bd;
    height: 50%;
    display: flex;
    align-items: center;
  }
  #section2 {
    border-bottom: 2px solid #d617bd;
    height: 50%;
    display: flex;
    align-items: center;
  }
</style>

<section id="project-title">
  <img id="header" {src} alt="blue-header" />
</section>

<div id="carousel-wrapper">
  <div id="carousel">
    <img
      id="previous"
      alt="go-back-arrow"
      src={previousSlide}
      on:click={previous} />
    {#each [Projects[index]] as src (index)}
      <img
        id="carousel-slides"
        alt={name}
        {src}
        in:fly={{ x: -2000, duration: 2000 }} />
    {/each}
    <img id="next" alt="next-arrow" src={nextSlide} on:click={next} />
  </div>

  <div id="text-wrapper">
    <div id="text-section">
      <h3>{view}</h3>
      <section id="section1">
        <p>
          The code button will redirect you to github where you can view all the
          code for a specific project
        </p>
      </section>
      <section id="section2">
        <p>
          The view button will redirect you to the deployed site of a specific
          project
        </p>
      </section>

      <div id="project_buttons">
        <button id="code">
          <a href={gits}>CODE</a>
        </button>
        <button id="view">
          <a href={url}>VIEW</a>
        </button>
      </div>
    </div>
  </div>
</div>
