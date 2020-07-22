<script>
import {createEventDispatcher} from 'svelte';
const dispatch = createEventDispatcher();
function closeModal(){
 dispatch('close')
}
export let style
</script>

<div class="modal-wrap"  style="{style}transition:all 0.5sec ease;">
    <div class="modal">
        <div class="close" on:click|stopPropagation="{closeModal}">
            <div class="bar bar-left"></div>
            <div class="bar bar-right"></div>
        </div>
        <img src="/icecream.svg" alt="icecream-icon" id="icecream">
        <h4 class="script-text">would you buy me an icecream?</h4>

        <form  action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
            <input type="hidden" name="cmd" value="_s-xclick" />
            <input type="hidden" name="hosted_button_id" value="C4AVRMJ4P6JAN" />
            <input id="paypal-btn" type="image" src="/paypal-donate-btn.png" border="0" name="submit" title="PayPal - The safer, easier way to pay online!" alt="Donate with PayPal button" />
            <img alt="" border="0" src="https://www.paypal.com/en_GR/i/scr/pixel.gif" width="1" height="1" />
            <!-- https://www.paypal.com/donate/buttons/ -->
         </form>
       
    </div>
</div>

<style>
 
    .modal-wrap{
        width:100%;
        transition:all 0.5s ease;
        height:100vh;
        display:flex;
        justify-content: center;
        align-items: center;
        position:fixed;
        z-index:1000;
        background:rgba(4, 4, 4, 0.4)
    }
    .modal{
        max-width:100%;
        position:relative;
        border-radius:15px;
        width:400px;
        height:240px;
        background-image: url(/osclinear.png);
        background-position: 50% 60%;
        background-repeat: repeat-x;
        background-color: var(--sec-color);
        flex-direction: column;
        display:flex;
        justify-content: center;
        align-items: center;
        z-index:1100;
        box-shadow: 1px 1px 25px 0px rgb(61, 61, 61)
    }
    @media (max-width:500px){
        .modal{
        width:300px;
        height:60vh;
        text-align: center;
     }
    }
    #icecream{
        width:50px;
        transform:rotate(25deg) translateY(-25px);
        transform-origin: center;
        
    }
    .close{
        display: flex;
        justify-content: center;
        align-items: center;
        position:absolute;
        top:10px;
        right:10px;     
        width:35px;
        height:35px;
        cursor:pointer;
        padding:5px;
        transition: transform ease-out 0.15s;
        transition: background-color ease 0.4s;
        background-color: transparent;
        border-radius: 25px;
        
       
        }
        .close:hover{
        background-color: rgba(168, 168, 168, 0.159);

        }
        .close:active{
        transform-origin: center;
        transform:scale(1.2) rotate(180deg);
    }
    .bar{
        position: absolute;
        width:35px;
        height:2px;
        background-color: var(--main-color);
       
    }
   
    .bar-left{
        transform-origin: center;
        transform:rotate(45deg);
    }
    .bar-right{
        transform-origin: center;

        transform:rotate(-45deg);
    }
  
    #paypal-btn{
        margin :20px  0;
        border:none !important;
        max-width:150px;
    }
    h4{
    margin: 0 0 50px;
    font-size:1.7em;
    font-weight: 700;
	font-variation-settings: 'wght' 400,700;
    }
  
  
</style>