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
          <button transition:fade value="all" 
          	class:active="{current === 'all'}"
	        on:click="{() => current = 'all'}"
            on:click={setCat}
         >All</button></li>
        <li>
        <button transition:fade value="abstract" 
        	class:active="{current === 'abstract'}"
	        on:click="{() => current = 'abstract'}"
        on:click={setCat}>Abstract</button>
        </li>
        <li>
        <button transition:fade value="text" 
        	class:active="{current === 'text'}"
	        on:click="{() => current = 'text'}"
        on:click={setCat}>Text</button>
        </li>
        <li>
        <button transition:fade value="counters" 
        	class:active="{current === 'counters'}"
	        on:click="{() => current = 'counters'}"
        on:click={setCat}>Counters</button>
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
        width:100%;
        cursor: pointer;
    }
    button:hover{
         box-shadow:  0 0px 08px inset rgb(153, 153, 153)   
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
 
</style>