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
  #carousel-wrapper {
    height: 650px;
    display: flex;
    width: 100%;
    background-color: #15202b;
  }
  #carousel {
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }

  #carousel-slides {
    width: 80%;
    border-radius: 5px;
    height: 85%;
  }

  #previous_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 10rem;
  }

  #previous {
    width: 48px;
    z-index: 1;
  }

  #next_wrapper {
    background-color: #21367f;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 10rem;
  }

  #next {
    width: 48px;
    z-index: 1;
  }

  #project_buttons {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    margin-top: 1.5rem;
  }
  #code {
    background-color: #21367f;
    color: #fff;
    border: 2px solid #2dfafc;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  #view {
    color: #fff;
    border: 2px solid #2dfafc;
    background-color: #21367f;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: small;
  }
  #text-wrapper {
    display: flex;
    justify-content: flex-end;
    width: 100%;
    border-left: 2px solid #d617bd;
  }
  #text-section {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    text-align: center;
    margin: 1rem 1rem 1rem 1rem;
  }
  #section1 {
    border-bottom: 2px solid #d617bd;
    height: 50%;
    display: flex;
    flex-direction: column;
    font-size: small;
    align-items: center;
    justify-content: space-evenly;
    width: 100%;
  }
  #section2 {
    border-bottom: 2px solid #d617bd;
    height: 50%;
    display: flex;
    flex-direction: column;
    font-size: small;
    justify-content: space-evenly;
    width: 100%;
  }
  #stack_list {
    text-align: left;
    height: 50%;
    font-size: small;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
</style>

<div id="carousel-wrapper">
  <div id="previous_wrapper">
    <img
      id="previous"
      alt="go-back-arrow"
      src={previousSlide}
      on:click={previous} />
  </div>

  <div id="carousel">
    <h5 id="slide_title">{view}</h5>

    {#each [Projects[index]] as src (index)}
      <img
        id="carousel-slides"
        alt={name}
        {src}
        in:fly={{ x: -50, duration: 2000 }} />
    {/each}
  </div>

  <div id="text-wrapper">
    <div id="text-section">
      <section id="section1">
        <h5>About this project</h5>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maxime
          soluta quis impedit itaque nisi a est. Quaerat, quia libero vitae ex
          rerum, voluptas dignissimos nam sapiente, eveniet inventore aspernatur
          ipsam.
        </p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Maxime
          soluta quis impedit itaque nisi a est. Quaerat, quia libero vitae ex
          rerum, voluptas dignissimos nam sapiente, eveniet inventore aspernatur
          ipsam.
        </p>
      </section>
      <section id="section2">
        <h5>Tech Stack used</h5>
        <ul id="stack_list">
          <li>Gatsby</li>
          <li>AWS Services</li>
          <li>Node</li>
          <li>GraphQl</li>
        </ul>
      </section>

      <div id="project_buttons">
        <button id="code">
          <a href={gits}>Code</a>
        </button>
        <button id="view">
          <a href={url}>View</a>
        </button>
      </div>
    </div>
  </div>
  <div id="next_wrapper">
    <img id="next" alt="next-arrow" src={nextSlide} on:click={next} />
  </div>
</div>
