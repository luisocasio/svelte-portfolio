<script>
  import Carousel from '../components/Carousel.svelte';
  import About from '../components/About.svelte';
  import Footer from '../components/Footer.svelte';

  let src = 'assets/denverBanner.png';
  let desc = 'art-work';
</script>

<style>
  #banner-section {
    margin-top: 2.5rem;
  }

  #banner {
    width: 100%;
  }
</style>

<main>
  <section id="banner-section">
    <img id="banner" alt={desc} {src} />
  </section>

  <Carousel />
  <About />
  <Footer />
</main>
