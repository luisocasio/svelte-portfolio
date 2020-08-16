<script>
  let src = "./assets/svg/royalblueHeader.svg";
</script>

<style>
  footer {
    bottom: 0;
    width: 100%;
    height: 550px;
    background-color: #00add8;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }
  input {
    height: 48px;
    width: 250px;
    border-radius: 5px;
  }
  button {
    width: 130px;
    height: 32.5px;
    border-radius: 38px;
    font-size: 1rem;
    background-color: #21367f;
    color: #fff;
  }
  #header_container {
    position: relative;
    text-align: center;
    color: white;
    background-color: #00add8;
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
    justify-content: center;
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
    <input type="name" placeholder="email" />
    <input type="name" placeholder="phone" />
  </form>

  <form id="main_form">
    <input id="main_input" type="main_input" placeholder="message" />
  </form>

  <button>
    <a href="/">SUBMIT</a>
  </button>

</footer>
