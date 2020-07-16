<script>
    import Icon from 'fa-svelte';
    import { faComments } from '@fortawesome/free-solid-svg-icons/faComments';
    import { faCameraRetro } from '@fortawesome/free-solid-svg-icons/faCameraRetro';


let galleryIcon=faCameraRetro
let speachIcon=faComments
</script>

<nav class="navbar">
   <div class="logo-wrap"> <h1 class="temp">assetmio</h1></div>
    <ul>
        <li class="nav-item"><a href="#gallery">
            <Icon icon={galleryIcon}/>
            <span>gallery</span></a> 
        </li>

        <li class="nav-item">
            <a href="#contact">
            <Icon icon={speachIcon}/>
            <span>contact</span></a> 
         </li>
    </ul>
</nav>
<style>
    .temp{
        margin:0.5em 0;
    }
    .navbar{
    max-width:100%;  
    position: absolute;
    width: 100%;
    top: 0;
    display: flex;
    justify-content: space-between;
    z-index: 100;
    background: var(--sec-color)
    }
    .logo-wrap{
        margin-left: 2em;
        text-transform: uppercase;
    }
    .logo-wrap h1{
        font-weight: normal;
    }
    ul{
        list-style: none;
        display:flex;
        justify-content: flex-end;
        padding: 0 2em;
      
    }
    .nav-item{
        margin: 0 10px;
        display:flex;
    }
 
    .nav-item a:hover{
        color:var(--inv-main-text-color);
        text-decoration: none;
    }
    .nav-item a{
        transition:all 0.2s ease;
        margin: 0 10px;
        display:flex;
        align-items: center;
        color:var(--main-color); 
    }
    .nav-item span{
        margin-left:5px;
        text-transform: uppercase;
        font-size:0.9em; 
    }
    @media (max-width:500px){
        .logo-wrap{
        margin-left: 1em;
        text-transform: uppercase;
    }
    .logo-wrap h1{
        font-weight: normal;
        font-size: 1em;
    }
    ul{
        list-style: none;
        display:flex;
        justify-content: flex-end;
        padding: 0 1em;
      
    }
    .nav-item{
        margin: 0 5px;
        display:flex;
    }
 
  
    .nav-item a{
        margin: 0 5px;
    }
    .nav-item span{
        margin-left:5px;
        text-transform: uppercase;
        font-size:0.8em; 
    }

    }
    
</style>