<script>
  import Carousel from "../components/Carousel.svelte";
  import About from "../components/About.svelte";
  import Footer from "../components/Footer.svelte";

  let src = "assets/denverBanner.png";
  let desc = "art-work";
</script>

<style>
  #banner-section {
    height: 650px;
  }
  #banner {
    width: 100%;
    height: 100%;
  }
  #intro_title {
    background-color: #15202b;
    border-bottom: 2px solid gray;
    height: 95px;
    display: flex;
    align-items: center;
    justify-content: space-around;
    font-size: small;
  }
</style>

<main id="banner-section">
  <img id="banner" alt={desc} {src} />
</main>

<section id="intro_title">
  <p>Javascript</p>
  <p>React</p>
  <p>Python</p>
</section>
<Carousel />
<About />
<Footer />
