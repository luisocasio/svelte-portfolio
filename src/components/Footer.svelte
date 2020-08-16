<script>
  let src = "./assets/svg/royalblueHeader.svg";
</script>

<style>
  footer {
    bottom: 0;
    width: 100%;
    height: 550px;
    background-color: #15202b;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }
  input {
    height: 48px;
    width: 250px;
    border-radius: 5px;
    text-align: center;
  }
  button {
    width: 130px;
    height: 32.5px;
    border-radius: 5px;
    font-size: small;
    background-color: #21367f;
    color: #fff;
  }
  #header_container {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
  }
  #header_title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  #contact_form {
    width: 100%;
    display: flex;
    justify-content: space-around;
  }
  #main_form {
    width: 100%;
    display: flex;
    justify-content: space-around;
  }
  #main_input {
    height: 250px;
    width: 50%;
  }
</style>

<div id="header_container">
  <img id="header" {src} alt="blue-header" />
  <h1 id="header_title">Lets Keep In Touch</h1>
</div>

<footer>
  <form id="contact_form">
    <input type="name" placeholder="name" />
    <input type="email" placeholder="email" />
    <input type="phone" placeholder="phone" />
  </form>

  <form id="main_form">
    <input id="main_input" type="main_input" placeholder="message" />

  </form>
  <button>
    <a href="/">Submit</a>
  </button>
  Follow me across these social media platforms.
  <div id="social-media-icons">
    <a href="https://www.instagram.com/fullstack_og/" alt="social-media-icon">
      <img
        src="https://img.icons8.com/fluent/48/000000/instagram-new.png"
        alt="instagram-logo" />
    </a>
    <a href="https://twitter.com/FullstackOg" alt="social-media-icon">
      <img
        src="https://img.icons8.com/fluent/48/000000/twitter.png"
        alt="twitter-logo" />
    </a>
    <a href="https://www.linkedin.com/in/ocasio-perez/" alt="social-media-icon">
      <img
        src="https://img.icons8.com/office/48/000000/linkedin.png"
        alt="linkedin-logo" />
    </a>
  </div>
  <a href="https://fullstackog.com/" alt="blog-site">
    <p>🚧Checkout My Blog Site🚧</p>

  </a>
</footer>
