<script>
    export let title,description,src,downLink,free
    import Icon from 'fa-svelte'
    import { faDownload } from '@fortawesome/free-solid-svg-icons/faDownload'
    import { faComments } from '@fortawesome/free-solid-svg-icons/faComments'
    
    let downIcon=faDownload
    let speachIcon=faComments
    
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
                {#if free}<span><a href="{downLink}" download target="_blank" rel="noopener" on:click|stopPropagation="{openModal}">
                    <Icon class="my-icon" icon={downIcon}></Icon> 
                </a>Download video file</span>{/if}
                <span><a href="#contact">
                    <Icon class="my-icon"  icon={speachIcon} scale="3"></Icon>
                </a> Contact for custom solution</span>
             
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
    .buttons_wrap{
        display:flex;
        justify-content: center;
    }
    .buttons_wrap>*{
        margin:15px;
    }
    a :global(.my-icon){
        width:30px;
        height:20px;
        margin: 0 0px 0 5px ;
        text-decoration: none;
    }
    a:hover{
        text-decoration: none;
    }
    
    
    </style>