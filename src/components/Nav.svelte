<script>
  


</script>

<nav class="navbar">
   <div class="logo-wrap"> <img class="logo" src="/openr_logo.svg" alt="openr logo"></div>
    <ul>
        <li class="nav-item"><a href="#gallery" title="gallery">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon  icon--photo" width="25" height="25" viewBox="0 0 24 24" stroke-width="1.5" stroke="" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z"/>
                <line x1="15" y1="8" x2="15.01" y2="8" />
                <rect x="4" y="4" width="16" height="16" rx="3" />
                <path d="M4 15l4 -4a3 5 0 0 1 3 0l 5 5" />
                <path d="M14 14l1 -1a3 5 0 0 1 3 0l 2 2" />
              </svg>
          
            <span>gallery</span></a> 
        </li>

        <li class="nav-item">
            <a href="#contact" title="contact">
                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon--contact " width="25" height="25" viewBox="0 0 24 24" stroke-width="1.5" stroke="" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <path d="M3 20l1.3 -3.9a9 8 0 1 1 3.4 2.9l-4.7 1" />
                    <line x1="12" y1="12" x2="12" y2="12.01" />
                    <line x1="8" y1="12" x2="8" y2="12.01" />
                    <line x1="16" y1="12" x2="16" y2="12.01" />
                  </svg>
          
            <span>contact</span></a> 
         </li>
    </ul>
</nav>
<style>
    .logo{
        width:120px;
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
        display: flex;
        align-items: center;
        margin-left: 2em;
        /* text-transform: uppercase; */
    }
   
    ul{
        list-style: none;
        display:flex;
        justify-content: flex-end;
        padding: 0 2em;
      
    }
    .nav-item {
        margin: 0 10px;
        display:flex;
        /* stroke:var(--inv-main-text-color); */

    }
    /* .nav-item:hover{
        
    } */
 
    .nav-item a:hover{
        color:var(--main-dark-color);
        text-decoration: none;
        stroke:var(--main-dark-color);
    }
    .nav-item a{
        transition:all 0.2s ease;
        margin: 0 10px;
        display:flex;
        align-items: center;
        color:var(--main-color); 
        color:var(--inv-main-text-color);
        stroke:var(--inv-main-text-color);

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