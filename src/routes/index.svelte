<script>
  import Card from "../components/Card.svelte";
  import Modal from "../components/Modal.svelte";
  import Form from "../components/Form.svelte";
  import { sources } from "../sources.js";
  import CatNav from "../components/CatNav.svelte";
  import { fade } from "svelte/transition";
  

  let style = "opacity:0;display:none;";
  
  $: styled = style;
  function close() {
    styled = "opacity:0;";
    setTimeout(() => (styled = "opacity:0;display:none;"), 1000);
  }
  function open() {
    styled = "opacity:0;display:flex;";
    setTimeout(() => (styled = "opacity:1;display:flex;"), 500);
  }
  let filter = "all";
  $: filtered = filter;
  function setFilter(event) {
    filtered = event.detail.category;
    console.log(filtered);
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
    --sec-text-color: rgb(236, 236, 236);
  }
  main {
    /* overflow: hidden; */
    text-align: center;
    padding: 0em 0;
    /* margin: 0 auto; */
  }
  section {
    position: relative;
    margin: 0;
    padding: 1em;
    background: #f4f4f4;
  }
  .section_desc {
    padding: 0 15px 40px;
  }
  .hero {
    overflow: hidden;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 95vh;
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
    margin-bottom: 10vw;
  }
  .main__color {
    color: var(--main-text-color);
  }
  .ivert__color {
    color: var(--inv-main-text-color);
  }
  .max-char {
    max-width: 55ch;
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
    max-width: 1600px;
    position: relative;
    margin: 2em auto;
    padding: 0em 06em 4em;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    grid-gap: 20px;
    /* grid-row-gap: 40px; */
  }

  @media (max-width: 640px) {
    .grid {
      grid-template-columns: 1fr;
      padding: 0em 0.5em 1em;
    }
  }
  .totop {
    
    padding:2px;
    transition: all 0.2s;
    display: grid;
    font-size: 1.2em;
    place-items: center;
    position: -webkit-sticky;
    position: sticky;
    top:800px;
    left:20px;
    width: 40px;
    height: auto;
    /* right: 0px; */
    background: var(--main-dark-color);
    color: var(--main-text-color);

    box-shadow: 0 0 5px rgba(163, 163, 163, 0);
    z-index:1000;
    border-radius: 50%;
  }
  .totop>svg{width: 40px}

  .totop:hover {
    box-shadow: 0 0 10px rgba(163, 163, 163, 1);
  }
  @media (max-width: 740px) {
    .totop {
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
  #contact {
    position: relative;
  }
  .decorativ {
    position: absolute;
  }
  .plane {
    width: 60px;
    bottom: 84px;
    right: 40%;
  }
  .service {
    top: 30%;
    left: 250px;
  }
  .mails {
    top: 45%;
    right: 250px;
  }
  .bottle {
    width: 120px;
    top: 70%;
    left: 250px;
  }
  /* WAVES STYLING */
  .wave {
    position: absolute;
    bottom: -5%;
    left: 0;
    right: 0;
  }
  .wave:nth-of-type(1) {
    --speed: 120;
    --opacity: 0.5;
    --height: 12;
    --width: 320;
    --lightness: 90;
    --rise: 20;
  }
  .wave:nth-of-type(2) {
    --speed: 80;
    --opacity: 0.6;
    --height: 10;
    --width: 200;
    --lightness: 95;
    --rise: 5;
  }
  .wave:nth-of-type(3) {
    --speed: 20;
    --opacity: 1;
    --height: 7;
    --width: 120;
    --lightness: 100;
    --rise: 0;
  }
  .wave {
    height: calc(var(--height, 0) * 1.5vh);
    width: calc(var(--width, 0) * 1vw);
    -webkit-animation: rise calc(var(--speed, 0) * 1.5s) infinite linear;
    animation: rise calc(var(--speed, 0) * 1.5s) infinite linear;
    opacity: var(--opacity);
  }
  @media (max-width: 480px) {
    .wave {
      height: calc(var(--height, 0) * 0.75vh);
    }
  }
  .wave path {
    /* fill: hsl(0, 0%, calc(var(--lightness, 0) * 1%)); */
    -webkit-animation: wave calc(var(--speed, 0) * 1s) infinite linear;
    animation: wave calc(var(--speed, 0) * 1s) infinite linear;
  }
  @-webkit-keyframes wave {
    to {
      -webkit-transform: translate(-761px, 0);
      transform: translate(-761px, 0);
    }
  }
  @keyframes wave {
    to {
      -webkit-transform: translate(-761px, 0);
      transform: translate(-761px, 0);
    }
  }
  @-webkit-keyframes rise {
    50% {
      -webkit-transform: translate(0, calc(var(--rise) * -1%));
      transform: translate(0, calc(var(--rise) * -1%));
    }
  }
  @keyframes rise {
    50% {
      -webkit-transform: translate(0, calc(var(--rise) * -1%));
      transform: translate(0, calc(var(--rise) * -1%));
    }
  }
</style>

<svelte:head>
  <!-- Quantcast Choice. Consent Manager Tag v2.0 (for TCF 2.0) -->
  <script type="text/javascript" async="true">
    (function() {
      var host = window.location.hostname;
      var element = document.createElement("script");
      var firstScript = document.getElementsByTagName("script")[0];
      var url = "https://quantcast.mgr.consensu.org".concat(
        "/choice/",
        "2Sm5GWREywCqZ",
        "/",
        host,
        "/choice.js"
      );
      var uspTries = 0;
      var uspTriesLimit = 3;
      element.async = true;
      element.type = "text/javascript";
      element.src = url;

      firstScript.parentNode.insertBefore(element, firstScript);

      function makeStub() {
        var TCF_LOCATOR_NAME = "__tcfapiLocator";
        var queue = [];
        var win = window;
        var cmpFrame;

        function addFrame() {
          var doc = win.document;
          var otherCMP = !!win.frames[TCF_LOCATOR_NAME];

          if (!otherCMP) {
            if (doc.body) {
              var iframe = doc.createElement("iframe");

              iframe.style.cssText = "display:none";
              iframe.name = TCF_LOCATOR_NAME;
              doc.body.appendChild(iframe);
            } else {
              setTimeout(addFrame, 5);
            }
          }
          return !otherCMP;
        }

        function tcfAPIHandler() {
          var gdprApplies;
          var args = arguments;

          if (!args.length) {
            return queue;
          } else if (args[0] === "setGdprApplies") {
            if (
              args.length > 3 &&
              args[2] === 2 &&
              typeof args[3] === "boolean"
            ) {
              gdprApplies = args[3];
              if (typeof args[2] === "function") {
                args[2]("set", true);
              }
            }
          } else if (args[0] === "ping") {
            var retr = {
              gdprApplies: gdprApplies,
              cmpLoaded: false,
              cmpStatus: "stub"
            };

            if (typeof args[2] === "function") {
              args[2](retr);
            }
          } else {
            queue.push(args);
          }
        }

        function postMessageEventHandler(event) {
          var msgIsString = typeof event.data === "string";
          var json = {};

          try {
            if (msgIsString) {
              json = JSON.parse(event.data);
            } else {
              json = event.data;
            }
          } catch (ignore) {}

          var payload = json.__tcfapiCall;

          if (payload) {
            window.__tcfapi(
              payload.command,
              payload.version,
              function(retValue, success) {
                var returnMsg = {
                  __tcfapiReturn: {
                    returnValue: retValue,
                    success: success,
                    callId: payload.callId
                  }
                };
                if (msgIsString) {
                  returnMsg = JSON.stringify(returnMsg);
                }
                event.source.postMessage(returnMsg, "*");
              },
              payload.parameter
            );
          }
        }

        while (win) {
          try {
            if (win.frames[TCF_LOCATOR_NAME]) {
              cmpFrame = win;
              break;
            }
          } catch (ignore) {}

          if (win === window.top) {
            break;
          }
          win = win.parent;
        }
        if (!cmpFrame) {
          addFrame();
          win.__tcfapi = tcfAPIHandler;
          win.addEventListener("message", postMessageEventHandler, false);
        }
      }

      makeStub();

      var uspStubFunction = function() {
        var arg = arguments;
        if (typeof window.__uspapi !== uspStubFunction) {
          setTimeout(function() {
            if (typeof window.__uspapi !== "undefined") {
              window.__uspapi.apply(window.__uspapi, arg);
            }
          }, 500);
        }
      };

      var checkIfUspIsReady = function() {
        uspTries++;
        if (window.__uspapi === uspStubFunction && uspTries < uspTriesLimit) {
          console.warn("USP is not accessible");
        } else {
          clearInterval(uspInterval);
        }
      };

      if (typeof window.__uspapi === "undefined") {
        window.__uspapi = uspStubFunction;
        var uspInterval = setInterval(checkIfUspIsReady, 6000);
      }
    })();
  </script>
  <!-- End Quantcast Choice. Consent Manager Tag v2.0 (for TCF 2.0) -->
  <!-- Primary Meta Tags -->
  <title>openR - animated visuals, free video openers resources</title>
  <!-- META -->
  <meta
    name="title"
    content="openR - VIDEO OPENERS, free video openers resources" />
  <meta
    name="description"
    content="Videos for content creators.Download free video openers in full-HD
    with seamless pattern loops for your youtube, twitch or other content
    creator platform!" />

  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://metatags.io/" />
  <meta
    property="og:title"
    content="openR - VIDEO OPENERS, free video openers resources" />
  <meta
    property="og:description"
    content="Videos for content creators.Download free video openers in full-HD
    with seamless pattern loops for your youtube, twich or other content creator
    platform!" />
  <meta property="og:image" content="/openR - Animated Visuals.png" />

  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image" />
  <meta property="twitter:url" content="https://metatags.io/" />
  <meta
    property="twitter:title"
    content="openR - VIDEO OPENERS, free video openers resources" />
  <meta
    property="twitter:description"
    content="Videos for content creators. Download free video openers in full-HD
    with seamless pattern loops for your youtube, twich or other content creator
    platform!" />
  <meta property="twitter:image" content="/openR - Animated Visuals.png" />

</svelte:head>

<Modal on:close={close} style={styled} />
<main>

  <section class="hero" id="hero">

    <h1 class="main__color">VIDEO OPENERS</h1>
    <h2 class="main__color">
      INTRO GRAPHICS
      <br />
      for content creators, designers, developers.
    </h2>

    <h3 class="main__color">
      download free video openers in full-HD with seamless pattern loops for
      your youtube, twich or other content creator platform!
    </h3>

    <div class="waves-wrap">
      <svg
        class="wave"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 762 52.917"
        preserveAspectRatio="none">
        <defs>
          <path
            id="wave"
            d="M0 0c22.863 0 40.637 25.93 63.5 25.93S104.137 0 127 0s40.637
            25.93 63.5 25.93S231.137 0 254 0s40.637 25.93 63.5 25.93S358.137 0
            381 0s40.637 25.93 63.5 25.93S485.137 0 508 0s40.637 25.93 63.5
            25.93S612.137 0 635 0s40.637 25.93 63.5 25.93S739.137 0 762
            0v52.917H0z"
            fill="var(--main-dark-color)" />
        </defs>
        <g>
          <use href="#wave" />
        </g>
        <g transform="translate(761 0)">
          <use href="#wave" />
        </g>
      </svg>
      <svg
        class="wave"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 762 52.917"
        preserveAspectRatio="none">
        <defs>
          <path
            id="wave2"
            d="M0 0c22.863 0 40.637 25.93 63.5 25.93S104.137 0 127 0s40.637
            25.93 63.5 25.93S231.137 0 254 0s40.637 25.93 63.5 25.93S358.137 0
            381 0s40.637 25.93 63.5 25.93S485.137 0 508 0s40.637 25.93 63.5
            25.93S612.137 0 635 0s40.637 25.93 63.5 25.93S739.137 0 762
            0v52.917H0z"
            fill="var(--sec-color)" />
        </defs>
        <g>
          <use href="#wave2" />
        </g>
        <g transform="translate(761 0)">
          <use href="#wave2" />
        </g>
      </svg>
      <svg
        class="wave"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 762 52.917"
        preserveAspectRatio="none">
        <defs>
          <path
            id="wave3"
            d="M0 0c22.863 0 40.637 25.93 63.5 25.93S104.137 0 127 0s40.637
            25.93 63.5 25.93S231.137 0 254 0s40.637 25.93 63.5 25.93S358.137 0
            381 0s40.637 25.93 63.5 25.93S485.137 0 508 0s40.637 25.93 63.5
            25.93S612.137 0 635 0s40.637 25.93 63.5 25.93S739.137 0 762
            0v52.917H0z"
            fill="var(--sec-color)" />
        </defs>
        <g>
          <use href="#wave3" />
        </g>
        <g transform="translate(761 0)">
          <use href="#wave3" />
        </g>
      </svg>
    </div>

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

    <CatNav on:setCategory={setFilter} />
    <a class="totop" title="go to top!" href="#gallery">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 20 20"
        fill="currentColor">
        <path
          fill-rule="evenodd"
          d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-8.707l-3-3a1 1 0 00-1.414
          0l-3 3a1 1 0 001.414 1.414L9 9.414V13a1 1 0 102 0V9.414l1.293 1.293a1
          1 0 001.414-1.414z"
          clip-rule="evenodd" />
      </svg>
    </a>
    <div class="grid">
    
      {#each sources as source}
        {#if source.category.find(e => e == filtered) == filtered || filtered === 'all'}
          <Card
            on:open={open}
            seamless={source.seamless}
            free={source.downloadFree}
            downLink={source.downLink}
            title={source.title}
            description={source.descr}
            videoPreview={source.videoPreview} />
        {/if}
      {/each}

    </div>
    
    <hr class="width-60" />

  </section>

  <!-- CONTACT FORM -->

  <section id="contact">
    <img
      src="/paper-plane140x140.png"
      alt="paper plane"
      class="decorativ plane" />
    <img
      src="/sbottled-letter140x140.png"
      alt="bottled message"
      class="decorativ bottle" />
    <img
      src="/fast-email@140x140.png"
      alt="letters flying"
      class="decorativ mails" />
    <img
      src="/customer-service140x140.png"
      alt="customer service"
      class="decorativ service" />
    <img src="/contact.png" alt="contact" />
    <div class="section_desc">
      <h2 class="ivert__color">Contact us</h2>
      <h3 class="ivert__color max-char">
        Ask for a custom solution that we can provide, for example add your
        brand name to an existing visualisation. We will get back to you ASAP! <br>
        Also send us your ideas about what other type of graphics or content you would like openR to have!
      </h3>
    </div>

    <Form {sources} />
  </section>

</main>
