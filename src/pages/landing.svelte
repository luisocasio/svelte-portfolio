<script>
  import Carousel from "../components/Carousel.svelte";
  import About from "../components/About.svelte";
  import Footer from "../components/Footer.svelte";

  let src = "assets/denverBanner.png";
  let desc = "art-work";
</script>

<style>
  #banner-section {
    width: 100%;
    height: 500px;
  }
  #banner {
    width: 100%;
    height: 100%;
  }
</style>

<main id="banner-section">
  <img id="banner" alt={desc} {src} />
</main>

<Carousel />
<About />
<Footer />
