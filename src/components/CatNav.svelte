<script>
  import {createEventDispatcher} from 'svelte';
  import { fade } from "svelte/transition"
const dispatch = createEventDispatcher();
    let current="all";
    let cat
    function setCat(){
     cat=this.value
     dispatch('setCategory',{
			category: cat
		})
    }
</script>
<div class="categories-menu">
    <ul class="categories-menu_list">
        <li>
          <button transition:fade|local value="all" 
          	class:active="{current === 'all'}"
	        on:click="{() => current = 'all'}"
            on:click={setCat}
         >All</button></li>
        <li>
        <button transition:fade|local value="abstract" 
        	class:active="{current === 'abstract'}"
	        on:click="{() => current = 'abstract'}"
        on:click={setCat}>Abstract</button>
        </li>
        <li>
        <button transition:fade|local value="text" 
        	class:active="{current === 'text'}"
	        on:click="{() => current = 'text'}"
        on:click={setCat}>Text</button>
        </li>
        <li>
        <button transition:fade|local value="counters" 
        	class:active="{current === 'counters'}"
	        on:click="{() => current = 'counters'}"
        on:click={setCat}>Counters</button>
        </li>
         <li>
        <button transition:fade|local value="stream" 
        	class:active="{current === 'stream'}"
	        on:click="{() => current = 'stream'}"
        on:click={setCat}>Stream</button>
        </li>
    </ul>    
   
</div>

<style>

    .categories-menu{
        margin: auto;
        width:80vw;
        padding: 15px
       
    }
    .categories-menu_list{
        
        display: flex;
        justify-content: space-around;
        align-items: center;
        list-style: none;
        padding: 0;
    }
    .categories-menu_list li{
        display: flex;
        flex: 1;
        justify-content: center;
    }
    button{
        width:95%;
        cursor: pointer;
        letter-spacing: 1.5px;
        font-weight: 600;
        border-radius: 5px;
        border-color: var(--main-color);
    }
    button:hover{
         box-shadow:  0 0px 18px inset rgb(255, 255, 255)   
    }
    button:active{
        outline: none;
        border: none;
    }
   
     .active{
       background: var(--main-color);
       color: var(--main-text-color);
       border:none;
 }
 .active:hover{
     box-shadow:none;
     cursor: auto;
 }
 
</style>