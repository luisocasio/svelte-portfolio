<script>
  import { fly, fade } from 'svelte/transition';
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
    width: 75%;
    height: 550px;
    border-radius: 5px;
  }

  #previous {
    width: 50px;
    padding: 1rem;
    z-index: 1;
  }

  #next {
    width: 50px;
    padding: 1rem;
    z-index: 1;
  }

  #project_buttons {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    margin-top: 2.5rem;
  }
  #code {
    background-color: #21367f;
    color: #fff;
    border: 4px solid #2dfafc;
    width: 125px;
    height: 48px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1.5rem;
  }
  #view {
    color: #fff;
    border: 4px solid #2dfafc;
    background-color: #15202b;
    width: 125px;
    height: 48px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1.5rem;
  }
  #text-wrapper {
    display: flex;
  }
  #text-section {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    border-left: 2px solid #d617bd;
    width: 100%;
    text-align: center;
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
        <img
          id="carousel-slides"
          alt={name}
          {src}
          in:fly={{ x: -2000, duration: 2000 }} />
      {/each}
    </div>

    <img id="next" alt="next-arrow" src={nextSlide} on:click={next} />

    <div id="text-wrapper">

      <div id="text-section">
        <section>
          <p>
            The code button will redirect you to github where you can view all
            the code for a specific project
          </p>
        </section>

        <section>
          <p>
            The view button will redirect you to the deployed site of a specific
            project
          </p>
        </section>

        <div id="project_buttons">
          {#each [projectSite[index]] as src (index)}
            <button id="code">CODE</button>
            <button id="view">VIEW</button>
          {/each}
        </div>
      </div>
    </div>
  </div>

</main>
