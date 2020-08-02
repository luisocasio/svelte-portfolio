<script>
  import { scale } from 'svelte/transition';
  import { each } from 'svelte/internal';
  let project1 = '/assets/projects/jaems.png';
  let project2 = '/assets/projects/latte-site.jpg';
  let project3 = '/assets/projects/market.png';
  let previousSlide = '/assets/svg/back.svg';
  let nextSlide = '/assets/svg/next.svg';
  let name = 'web-sites';

  const Projects = [project1, project2, project3];
  const projectSite = [
    'https://www.jaemsounds.com/',
    'https://latteluv.netlify.app/',
    'https://marketavenue.netlify.app/',
  ];

  let index = 0;

  const next = () => {
    index = (index + 1) % Projects.length;
  };

  const previous = () => {
    index = (index - 1) % Projects.length;
  };

  const code = () => {};

  const view = () => {};
</script>

<style>
  #carousel-wrapper {
    margin-top: 2.5rem;
    display: flex;
  }
  #carousel {
    width: 100%;
    display: flex;
    justify-content: center;
  }

  #carousel-slides {
    width: 325px;
    height: 450px;
  }

  #previous {
    width: 150px;
    padding: 1rem;
  }

  #next {
    width: 150px;
    padding: 1rem;
  }

  #project_buttons {
    display: flex;
    justify-content: space-around;
    width: 100%;
    margin-top: 2.5rem;
  }
  #code {
    background-color: #21367f;
    color: #fff;
    border: 4px solid #2dfafc;
    width: 250px;
    height: 48px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1.5rem;
  }
  #view {
    color: #fff;
    background-color: #2dfafc;
    width: 250px;
    height: 48px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1.5rem;
  }
</style>

<main>

  <div id="carousel-wrapper">
    <img
      id="previous"
      alt="go-back-arrow"
      src={previousSlide}
      on:click={previous} />
    <div id="carousel">
      {#each [Projects[index]] as src (index)}
        <img id="carousel-slides" transition:scale alt={name} {src} />
      {/each}
    </div>

    <img id="next" alt="next-arrow" src={nextSlide} on:click={next} />

  </div>

  <div id="project_buttons">

    {#each [projectSite[index]] as src (index)}
      <button id="code">CODE</button>
      <button id="view">VIEW</button>
    {/each}
  </div>

</main>
