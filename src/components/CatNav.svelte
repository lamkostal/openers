<script>
  import {createEventDispatcher} from 'svelte';
  import { fade } from "svelte/transition";
const dispatch = createEventDispatcher();
    let current="featured";
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
          <button transition:fade|local value="featured" 
          	class:active="{current === 'featured'}"
	        on:click="{() => current = 'featured'}"
            on:click={setCat}
         >Featured</button></li>
        
       
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
        <li>
        <button transition:fade|local value="particles" 
        	class:active="{current === 'particles'}"
	        on:click="{() => current = 'particles'}"
        on:click={setCat}>Particles</button>
        </li>
        <li>
        <button transition:fade|local value="transitions" 
        	class:active="{current === 'transitions'}"
	        on:click="{() => current = 'transitions'}"
        on:click={setCat}>Transitions</button>
        </li>
         <li>
          <button transition:fade|local value="all" 
          	class:active="{current === 'all'}"
	        on:click="{() => current = 'all'}"
            on:click={setCat}
         >view <mark>All</mark></button></li>
    </ul>    
   
</div>

<style>

    .categories-menu{
        margin: auto;
        width:60vw;
        padding: 0 15px;
       
    }
    @media (max-width:740px){
        .categories-menu{
        width:50vw;
        }
        .categories-menu_list li{
        display: flex;
        flex:1 0 100%;
        justify-content: center;
    }
       
    }
    .categories-menu_list{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        flex-wrap: wrap;
        list-style: none;
        padding: 0;
    }
    .categories-menu_list li{
        display: flex;
        flex:0 1 140px;
        justify-content: center;
       
    }
    button{
        width:95%;
        padding:  0.5em 1em;
        cursor: pointer;
        letter-spacing: 1.5px;
        font-weight: 600;
        border-radius: 5px;
        border-color: var(--main-color);
    }
    button:hover{
         box-shadow:  0 0px  3px 1px  rgb(255, 201, 54)   
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