<script>
  import NavBar from './components/NavBar.svelte';
  import Carousel from './components/Carousel.svelte';
  import About from './components/About.svelte';
  let src = 'assets/denverBanner.png';
  let desc = 'art-work';
</script>

<style>
  #banner-section {
    margin-top: 5rem;
  }

  #banner {
    width: 100%;
  }
</style>

<main>
  <NavBar />

  <section id="banner-section">
    <img id="banner" alt={desc} {src} />
  </section>

  <Carousel />

  <About />

</main>
