<script>
    export let sources;
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
</script>

<style>
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
  select {
    width: 100%;
    margin: 2px 0;
    border-radius: 10px;
    transition: all 0.3s ease;
  }

  .form_elem > *:focus {
    outline: none;
    border: var(--main-color) 1px solid;
    /* box-shadow: 1px 1px 5px 0px rgb(145, 167, 117) inset; */
    transition: all 0.3s ease-out;
  }
  .form_elem > *:focus + label {
    transform: translate(0px, -20px) scale(1.1);
    color: var(--main-color);
    font-weight: bold;
  }
  input,
  textarea,
  select {
    padding: 20px 50px 10px;
    background-color: rgba(253, 253, 253, 0.753);
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
    font-weight: 700;
    font-size: 1.2em;
    letter-spacing: 1.5px;
  }
  .form_btn:hover {
    background-color: transparent;
    color: var(--main-color);
    cursor:pointer;
    border:1px solid var(--main-color);
  }
  .form_btn:active {
    background-color: var(--main-color);
    color: var(--main-text-color);
    
  }


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
</style>

<div class="form-wrap">
  <form
  action="/success"
    netlify-honeypot="hid-field"
    class="contact-form"
    name="contact"
    method="POST"
    netlify>
    <input type="hidden" name="form-name" value="contact" />

    <input name="hid-field" hidden />
    <div class="form_elem">
      <input name="name" id="name" type="text" placeholder="" required />
      <label for="name">Name</label>
    </div>
    <div class="form_elem" >
      <input
      style="{ !validate? "border:1px solid red":""}"
        name="email"
        id="email"
        type="email"
        placeholder=""
        bind:value={email}
        on:change={initValidation}
        required />
      <!-- <span>{email}</span> -->
      <label for="email" style="{ !validate? "color:red":""}">Email</label>
      {#if !validate}
        <span class="danger">please insert a valid email</span>
      {:else if validate && valid}
        <span class="safe">email is valid</span>
      {/if}
    </div>
    <div class="form_elem">
      <textarea id="message" name="message" rows="10" cols="30" />
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
      <input type="submit" value="SUBMIT" class="form_btn" name="submit" />
      <!-- <input class="form_btn" type="submit"  <img src="//icon-send.svg" width="20" alt="send"/> -->
      <!-- <span>SUBMIT</span> /> -->

    </div>
    <!-- <div  data-netlify-recaptcha="true"  class="form_elem"></div> -->
  </form>
</div>
