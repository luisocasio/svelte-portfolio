<script>
  import Carousel from "../components/Carousel.svelte";
  import About from "../components/About.svelte";
  import Footer from "../components/Footer.svelte";

  let src = "assets/denverBanner.png";
  let desc = "art-work";
</script>

<style>
  li {
    list-style-type: none;
  }
  #banner-section {
    height: 650px;
  }
  #banner {
    width: 100%;
    height: 100%;
  }
  #tech-icons {
    background-color: #15202b;
    border-bottom: 2px solid gray;
    height: 95px;
    display: flex;
    align-items: center;
    justify-content: space-around;
    font-size: small;
  }
  #icon-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>

<main id="banner-section">
  <img id="banner" alt={desc} {src} />
</main>

<section id="intro_title">
  <div id="tech-icons">
    <section id="icon-container">
      <img
        src="https://img.icons8.com/color/48/000000/javascript.png"
        alt="javascript-logo" />
      <li>JavaScript</li>
    </section>
    <section id="icon-container">
      <img
        src="https://img.icons8.com/color/48/000000/react-native.png"
        alt="react-logo" />
      <li>React</li>
    </section>
    <section id="icon-container">
      <img
        src="https://img.icons8.com/doodle/48/000000/svetle.png"
        alt="svelte-log" />
      <li>Svelte</li>
    </section>
    <section id="icon-container">
      <img
        src="https://img.icons8.com/color/48/000000/graphql.png"
        alt="graphql-logo" />
      <li>graphql</li>
    </section>
    <section id="icon-container">
      <img
        src="https://img.icons8.com/color/48/000000/python.png"
        alt="python-logo" />
      <li>Python</li>
    </section>
  </div>
</section>
<Carousel />
<About />
<Footer />
