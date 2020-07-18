<script>
    export let title,description,src,downLink,free
   
    
    import {createEventDispatcher} from 'svelte';
    const dispatch = createEventDispatcher();
    function openModal(){
     dispatch('open')
     console.log("dispatched from component")
    }
    </script>
    
    <div class="card">
        {#if free}<div class="ribbon script-text">free</div>{/if}
        <div class="thumb">
            <img src="{src}" alt="{title}" loading="lazy">
        </div>
        <div class="text">
         <div class="title">{title}</div>
            <div class="description">
             <span>{description}</span>
    
            <div class="buttons_wrap" >
                {#if free}
                <span class="card-text-block">
                    <span>Download video file</span>
                    <a href="{downLink}" download target="_blank" rel="noopener" on:click|stopPropagation="{openModal}">
                        <svg xmlns="http://www.w3.org/2000/svg" class="my-icon icon icon--download" width="28" height="28" viewBox="0 0 24 24" stroke-width="2" stroke="#00a870" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z"/>
                        <path d="M4 17v2a2 2 0 0 0 2 2h12a2 2 0 0 0 2 -2v-2" />
                        <polyline points="7 11 12 16 17 11" />
                        <line x1="12" y1="4" x2="12" y2="16" />
                        </svg>
                    <!-- <Icon class="my-icon" icon={downIcon}></Icon>  -->
                    </a>
                    
                </span>
                {/if}
                <span class="card-text-block" >
                    <span>Contact for customisation </span>
                    <a href="#contact">
                    <svg xmlns="http://www.w3.org/2000/svg" class="my-icon icon icon--contact" width="28" height="28" viewBox="0 0 24 24" stroke-width="2" stroke="#00a870" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z"/>
                        <path d="M3 20l1.3 -3.9a9 8 0 1 1 3.4 2.9l-4.7 1" />
                        <line x1="12" y1="12" x2="12" y2="12.01" />
                        <line x1="8" y1="12" x2="8" y2="12.01" />
                        <line x1="16" y1="12" x2="16" y2="12.01" />
                      </svg>
                    <!-- <Icon class="my-icon"  icon={speachIcon} scale="3"></Icon> -->
                </a> 
                </span>
             
            </div>
         </div>
            
        </div>
    </div>
    
    <style>
    .ribbon{
        font-size: 1.2em;
        /* text-transform: uppercase; */
        text-align:center;
        position: absolute;
        font-weight:600;
        top:30px;
        left:-50px;
        transform: rotate(-45deg);
        transform-origin: 50%;
        background:var(--main-color);
        padding:5px 80px 5px ;
        color:#fff;
    }
    .card{
        overflow: hidden;
        position:relative;
        padding:1.5rem 2rem 0.5rem;
        background-color: #fff;
        display:flex;
        flex-direction:column;
        border-radius:5px;
    }
    .card a{
        color:var(--main-color);
    }
    .card-text-block{
        display:flex;
        align-items: center;
    }
    .buttons_wrap{
        display:flex;
        justify-content: center;
    }
    @media (max-width:740px){
        .card-text-block{
        flex-direction: column;
        flex-flow: column-reverse;
    }
    .buttons_wrap{
        flex-direction: column;
    }

    }
    .thumb img{
        max-width:100%;
    }
    .title{
        font-weight:bold;
        /* text-transform: uppercase; */
        font-size:1.25em;
    }
    .description{
        display:flex;
        flex-direction: column;
        font-size: 1em;
    }
    .text{
        display:flex;
        flex-direction: column;
        justify-content: center;
    }
    .description>*{
        margin:10px;
    }
   
    .buttons_wrap>*{
        margin:15px;
    }
    a :global(.my-icon){
        width:25px;
        height:25px;
        margin: 0 15px 0 5px ;
        text-decoration: none;
    }
    a:hover{
        text-decoration: none;
    }
    
    
    </style>