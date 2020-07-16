<script>
import Card from "../components/Card.svelte";
import Nav from "../components/Nav.svelte";
import Modal from "../components/Modal.svelte";

let sources = [
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592046662/animated%20backgrounds/vox_alt-lamkos3_ljyueh.gif",
	title: "lamkos",
	descr: "4:055s 30fps mp4",
	downLink:
	  "//0-02-0a-c8340a9f1f248d970a7a0e56c76def88a0c08b47c35dc5164f2948746bc68ab5_30f1d7ee.mp4",
	  downloadFree:false
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592046306/animated%20backgrounds/electrons_dwsdtd.gif",
	title: "electrons",
	descr: "4:06s",
	downLink: "",
	downloadFree:false
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592045629/animated%20backgrounds/connect-poly_rnwmlj.gif",
	title: "connect1",
	descr: "4:06s",
	downLink: "",
	downloadFree:true
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592046098/animated%20backgrounds/jeskai-apng.00099_mlrlsg.png",
	title: "jeskai-ink",
	descr: "4:06s",
	downLink: "",
	downloadFree:false
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592223572/animated%20backgrounds/polyconnect_yjrjkb.gif",
	title: "connect2",
	descr: "4:06s",
	downLink: "",
	downloadFree:true
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592231375/animated%20backgrounds/psycSplash2-0d_qnz2g8.gif",
	title: "wavy-blobs",
	descr: "4:06s",
	downLink: "",
	downloadFree:true
  },
  {
	src:
	  "https://res.cloudinary.com/lamkos/image/upload/v1592073504/animated%20backgrounds/star-connect-apng_xr6pjy.png",
	title: "star-connect",
	descr: "4:06s",
	downLink: "",
	downloadFree:true
  },
];
let mail;
let valid = null;
let validate = true;
let email = null;
$: mail = email;

function initValidation() {
  valid = function emailValidator() {
	const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
	return re.test(String(mail).toLowerCase());
  };

  validate = valid();
}

$: console.log(mail);

$: console.log(validate);
// let style="opacity:0;display:none;"
let style
$: styled=style
function close(){
  styled="opacity:0;"
  setTimeout(()=>styled="opacity:0;display:none;",1000)
  console.log("fired")
}
function open(){
  styled="opacity:0;display:flex;"
  setTimeout(()=>styled="opacity:1;display:flex;",500)
  
  console.log("openfired")
}
</script>

<style>
:root {
  --main-color: rgb(0, 168, 112);
  --sec-color:#f4f4f4;
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
  margin: 0 0 50px;
  padding: 1em;
}
.section_desc {
  padding: 0 0 40px;
}
.hero {
  position:relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  /* background-image: url("//hoverletters3.png"); */
  background-size: contain;
  background-color: var(--main-color);
  /* background: url("//bg.mp4"); */
}
h1 {
  text-transform: uppercase;
  font-size: 4em;
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
@media (max-width:400px){
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
  margin: 6em 0 4em;
}

.form-wrap {
  display: flex;
  justify-content: center;
}
.contact-form {
  display: flex;
  flex-direction: column;
  text-align: left;
  flex-basis: 400px;
}
label {
  position: absolute;
  top: -5px;
  left: 0;
  width: 0;
  font-size: 0.8rem;
  transform: translate(10px, 10px);
  transition: all 0.4s ease-out;
  color: #808080;
}
.form_elem {
  margin: 15px 0;
  position: relative;
}

.form_elem > input,
textarea,
select,
/* button {
  width: 100%;
  margin: 2px 0;
  border-radius: 10px;
  transition: all 0.3s ease;
} 
 button:hover {
  cursor: pointer;
  box-shadow: 1px 1px 5px 0px rgb(145, 167, 117);
} */
.form_elem > *:focus {
  outline: none;
  border: var(--main-color) 1px solid;
  box-shadow: 1px 1px 5px 0px rgb(145, 167, 117) inset;
  transition: all 0.2s ease-out;
}
.form_elem > *:focus + label {
  transform: translate(0px, -20px) scale(1.1);
  color: var(--main-color);
  font-weight: bold;
}
input,
textarea,
select
{
  padding: 20px 50px 10px;
}
option,
select {
  text-transform: uppercase;
}
.select_head {
  text-align: center;
  text-transform: uppercase;
  background-color: var(--main-color);
  color: var(--main-text-color);
  font-weight: bold;
}
.form_btn {
  padding: 15px 10px;
  background-color: var(--main-color);
  color: var(--main-text-color);
  display: flex;
  justify-content: center;
  align-items: center;
}
.form_btn:focus {
  background-color: transparent;
  color: var(--main-color);
}
/* .form_btn > span {
  margin: 0 10px;
  font-size: 1.2em;
  font-weight: bold;
} */

span.danger {
  display: block;
  font-size: 0.7em;
  text-align: right;
  color: red;
}
span.safe {
  display: block;
  font-size: 0.7em;
  text-align: right;
  color: green;
}
hr {
  border: 1px solid #fff;
  margin: auto;
  margin-bottom: 20px;
}
.width-60 {
  width: 60%;
}
.width-30 {
  width: 30%;
}

.grid {
  margin: 2em 0;
  padding: 0em 0 4em;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(550px, 1fr));
  grid-gap: 20px;
  grid-row-gap: 40px;
}

@media (max-width: 640px) {
  .grid {
	grid-template-columns: 1fr;
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
	transform: translate3d(0, 10px, 0);
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
</style>



<Modal on:close="{close}"  style={styled}/>
<main>

<Nav/>
<section class="hero">
  <h1 class="main__color">Video animations</h1>

  <h2 class="main__color">
	resources
	<br />
	for content creators, designers, developpers.
  </h2>

  <h3 class="main__color">
	download free video openers with seamless pattern loops for your youtube, twich or other content
	creator platform! 
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
		fill="rgb(0, 168, 112)"
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

  <div class="grid">
	{#each sources as source}
	<Card
	  on:open={open}
	  free={source.downloadFree}
	  downLink={source.downLink}
	  title={source.title}
	  src={source.src}
	  description={source.descr} />
	  {/each}
  </div>
  <hr class="width-60" />
  <hr class="width-30" />

</section>

		   <!-- CONTACT FORM -->

<section id="contact">
  <img src="/contact.png" alt="contact" />
  <div class="section_desc">
	<h2 class="ivert__color">Contact us</h2>
	<h3 class="ivert__color max-char">
	  Ask for a custom solution that we can provide, for example add your
	  brand name to an existing visualisation. We 'll get back at you ASAP!'
	</h3>
  </div>

  <div class="form-wrap">
	<form
	  netlify-honeypot="hid-field"
	  class="contact-form"
	  name="contact"
	  method="POST"
	  netlify
    data-netlify-recaptcha="true">
	<input type="hidden" name="form-name" value="contact"/>
    
	  <input name="hid-field" hidden />
	  <div class="form_elem">
		<input name="name" id="name" type="text" placeholder="" required />
		<label for="name">Name</label>
	  </div>
	  <div class="form_elem">
	  <input
		  name="email"
		  id="email"
		  type="email"
		  placeholder=""
		  bind:value={email}
		  on:change={initValidation}
		  required />
		<!-- <span>{email}</span> -->
		<label for="email">Email</label>
		{#if !validate}
		  <span class="danger">please insert a valid email</span>
		{:else if validate && valid}
		  <span class="safe">email is valid</span>
		{/if}
	  </div>
	  <div class="form_elem">
		<textarea id="message" name="message" rows="10" cols="30"  
		/>
		<label for="message">Message</label>
	  </div>
	  <div class="form_elem">
		<select id="select" name="select">
		  <option class="select_head" value="">-visual of choice-</option>
		  {#each sources as source}
			<option value={source.title}>{source.title}</option>
		  {/each}
		</select>
		<label for="select">select</label>
	  </div>
	  <div class="form_elem">
		<input type="submit" value="Submit" class="form_btn" 
		name="submit">
		<!-- <input class="form_btn" type="submit"  <img src="//icon-send.svg" width="20" alt="send"/> -->
		<!-- <span>SUBMIT</span> /> -->
		 
	  </div>
	  <div  data-netlify-recaptcha="true"  class="form_elem"></div>
	</form>
  </div>
</section>

</main>
