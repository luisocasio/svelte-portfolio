<script>
  let src = "./assets/svg/royalblueHeader.svg";
</script>

<style>
  #wrapper {
    height: 650px;
    width: 100%;
    background-color: #15202b;
    display: flex;
    align-items: center;
    border-bottom: 2px solid gray;
  }

  #about_content {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  #section1 {
    width: 50%;
  }
  #section2 {
    width: 50%;
  }

  #header_container {
    position: relative;
    text-align: center;
    color: white;
    background-color: #15202b;
  }

  #about_title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  #resume_button {
    position: absolute;
    top: 50%;
    right: 16px;
    transform: translate(-50%, -50%);
    background-color: #00add8;
    color: #fff;
    width: 130px;
    height: 32.5px;
    text-decoration: none;
    border-radius: 35px;
    font-size: 1rem;
  }
</style>

<div id="header_container">
  <img id="header" {src} alt="blue-header" />
  <h1 id="about_title">About Me</h1>

  <button id="resume_button">
    <a href="https://resume.creddle.io/resume/63v349pbnj3">Resume</a>
  </button>

</div>
<div id="wrapper">

  <div id="about_content">
    <div id="section1">
      <h1>SOME CONETENT</h1>

      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam
        rem porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi.
        Doloribus neque totam doloremque quam voluptatem repudiandae, debitis
        rerum.
      </p>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam
        rem porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi.
        Doloribus neque totam doloremque quam voluptatem repudiandae, debitis
        rerum.
      </p>
    </div>

    <div id="section2">
      <h1>A LITTLE MORE ABOUT ME</h1>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam
        rem porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi.
        Doloribus neque totam doloremque quam voluptatem repudiandae, debitis
        rerum.
      </p>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque ipsam
        rem porro fugiat nemo! In fuga maxime nobis magni tenetur excepturi.
        Doloribus neque totam doloremque quam voluptatem repudiandae, debitis
        rerum.
      </p>
    </div>
  </div>

</div>
