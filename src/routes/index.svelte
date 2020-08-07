<script>
  import Card from "../components/Card.svelte";
  import Modal from "../components/Modal.svelte";
  import Form from "../components/Form.svelte";
  import {sources} from "../sources.js";
  import CatNav from "../components/CatNav.svelte";
  import { fade } from 'svelte/transition';
  
  let style = "opacity:0;display:none;";
  // let style
  $: styled = style;
  function close() {
    styled = "opacity:0;";
    setTimeout(() => (styled = "opacity:0;display:none;"), 1000);
    // console.log("fired")
  }
  function open() {
    styled = "opacity:0;display:flex;";
    setTimeout(() => (styled = "opacity:1;display:flex;"), 500);

    // console.log("openfired")
  }
  let filter="all";
  $:filtered=filter;
  function setFilter(event){
    filtered=event.detail.category;
    console.log(filtered)
  }
</script>

<style>
  :root {
    /* --main-color: rgb(0, 168, 112); */
    --main-color: rgb(0, 168, 112);
    --main-dark-color: rgb(0, 134, 90);

    --sec-color: #f4f4f4;
    --main-text-color: #fff;
    --inv-main-text-color: rgb(63, 63, 63);
    --sec-text-color: rgb(207, 207, 207);
   
  }
  main {
    overflow: hidden;
    text-align: center;
    padding: 0em 0;
    margin: 0 auto;
  }
  section {
    position: relative;
    margin:0;
    padding: 1em;
   background:  #f4f4f4;
  }
  .section_desc {
    padding: 0 15px 40px;
  }
  .hero {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    /* background-image: url("/herobg-lines.png"); */
    background-size: contain;
    background: transparent;
    /* background-color: var(--main-color); */

  }
  h1 {
    text-transform: uppercase;
    font-size: 3.5em;
    font-weight: 400;
    margin: 0 0 50px;
  }
  h2 {
    font-size: 2em;
    font-weight: 100;
    text-transform: uppercase;
    margin: 0 0 10px;
  }
  h3 {
    font-weight: 100;
  }
  @media (max-width: 400px) {
    h1 {
      text-transform: uppercase;
      font-size: 3em;
      margin: 0 0 30px;
    }
    h2 {
      font-size: 1.5em;
      font-weight: 100;

      margin: 0 0 10px;
    }
    h3 {
      font-weight: 100;
    }
  }
  figure {
    position: absolute;
    left: calc(50% - 64px);
    bottom: 0;
    margin-bottom: 20px;
  }
  .main__color {
    color: var(--main-text-color);
  }
  .ivert__color {
    color: var(--inv-main-text-color);
  }
  .max-char {
    max-width: 60ch;
    margin: auto;
    line-height: 2rem;
  }
  .gallery {
    
    padding: 6em 0 4em;
  }
  hr {
    border: 1px solid #fff;
    margin: auto;
    margin-bottom: 20px;
  }
  .width-60 {
    width: 60%;
  }
  /* .width-30 {
    width: 30%;
  } */

  .grid {
    position: relative;
    margin: 2em 0;
    padding: 0em 02em 4em;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
    grid-gap: 20px;
    /* grid-row-gap: 40px; */
  }

  @media (max-width: 640px) {
    .grid {
      
      grid-template-columns: 1fr;
      padding: 0em 0.5em 1em;
    }
  }
  .totop{
    display: grid;
    font-size: 1.5em;
    place-items: center;
    position: absolute;
    width: 40px;
    height: 40px;
    bottom: 90px;
    right: 40px;
    background: var(--main-dark-color);
    color: var(--main-text-color);
    border-radius: 50%;
}

.totop:hover{
  box-shadow: 0 0 10px gray;
}
@media (max-width:740px){
  .totop{
    display: grid;
    font-size: 1.5em;
    place-items: center;
    position: absolute;
    width: 40px;
    height: 40px;
    bottom: 50px;
    right: 10px;
    background: var(--main-dark-color);
    color: var(--main-text-color);
    border-radius: 50%;
}
}
  /* //svg styling// */
  .line-mouse1 {
    animation: line-mouse1-scroll 2s infinite;
  }
  @keyframes line-mouse1-scroll {
    0% {
      transform: translate3d(0, 0, 0);
    }
    50% {
      transform: translate3d(0, 5px, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }
  @media (prefers-reduced-motion: reduce) {
    .line-mouse1 {
      animation: none;
    }
  }
  #contact{
    position:relative;
  }
  .decorativ{
    position:absolute;
  }
  .plane{
    width:60px;
    bottom:84px;
    right:38%;
  }
  .service{
    top:30%;
    left:250px;
  }
  .mails{
    top:45%;
    right:250px;
  }
  .bottle{
    width:120px;
    top:70%;
    left:250px;
  }

</style>

<svelte:head>
	<title>openR | Animated Visuals</title>
</svelte:head>

<Modal on:close={close} style={styled} />
<main>

  <section class="hero" id="hero">
 

    <h1 class="main__color">Animated Visuals</h1>

    <h2 class="main__color">
      video resources
      <br />
      for content creators, designers, developers.
    </h2>

    <h3 class="main__color">
      download free video openers in full-HD with seamless pattern loops for your youtube,
      twich or other content creator platform!
    </h3>
    <figure>
      <svg
        width="100"
        height="100"
        viewBox="0 -6 50 100"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        style="width: 64px; height: 64px;">

        <rect
          x="1"
          y="1"
          width="40"
          height="60"
          rx="18"
          fill=""
          stroke="#fff"
          stroke-width="2.0px" />
        <line
          class="line-mouse1"
          x1="21"
          y1="11"
          x2="21"
          y2="26"
          stroke="#fff"
          stroke-width="2px"
          style="animation-duration: 0.8s;" />
      </svg>
    </figure>
  </section>

  <section class="gallery ivert__color" id="gallery">
    <div class="section_desc">
      <h2 class="ivert__color">Take a look at the Gallery</h2>
      <h3 class="ivert__color max-char">
        Download video-intros in mp4 format, or
        <mark>
          <a href="#contact">contact</a>
        </mark>
        us if you would like us to create a tailor-made solution for your visual
        of choice.
      </h3>
    </div>

    <CatNav on:setCategory="{setFilter}"/>

    <div class="grid">
      {#each sources as source}
        {#if source.category==filtered || filtered==="all"}<Card
         
          on:open={open}
          seamless={source.seamless}
          free={source.downloadFree}
          downLink={source.downLink}
          title={source.title}
          description={source.descr}
          videoPreview={source.videoPreview}
         
           />{/if}
      {/each}
    
    </div>
       <a class="totop" href="#gallery"><span>&#x2B06</span></a>
    <hr class="width-60" />
  

  </section>

  <!-- CONTACT FORM -->

  <section id="contact">
    <img src="/paper-plane140x140.png" alt="paper plane" class="decorativ plane">
    <img src="/sbottled-letter140x140.png" alt="bottled message" class="decorativ bottle">
    <img src="/fast-email@140x140.png" alt="letters flying" class="decorativ mails">
    <img src="/customer-service140x140.png" alt="customer service" class="decorativ service">
    <img src="/contact.png" alt="contact" />
    <div class="section_desc">
      <h2 class="ivert__color">Contact us</h2>
      <h3 class="ivert__color max-char">
        Ask for a custom solution that we can provide, for example add your
        brand name to an existing visualisation. We 'll get back at you ASAP!'
      </h3>
    </div>

    <Form {sources} />
  </section>

</main>
