<script>
import {Router,Link} from 'svelte-routing';

import logo from '../assets/images/index';
import ButtonLink from '../common/ButtonLink.svelte';
export let user = false;

</script>

<nav>
    <div class="nav__part-one">
        <Link to="/home"><img src={logo.logo} alt="logo"></Link>
    </div>
    <div class="nav__part-two">
        {#if user}
            <ButtonLink to={'/cambiaresto'} message={'Cerrar sesion'} background={'var(--color-twitch)'} />
        {:else}
            
            <ButtonLink to={'/signin'} message={'Iniciar sesión'} background={'var(--color-twitch)'} svg={"fas fa-sign-in-alt"} />
        {/if}
            
    </div>
</nav>

<style>
     nav{
        
        background-color: var(--color-github);
        display:flex;
        justify-content: space-between;
        padding: .5rem 1rem .5rem .5rem;
    }
    img{
       
        width: 3.7rem;
    }
    img:hover{
        transform: rotateZ(1440deg);
        transition: all 5s ease;
    }
    .nav__part-two{
            display: grid;
            grid-template-columns: repeat(1, 1fr);
            align-items: center;
    }
    
    @media screen and (min-width: 768px){
        
        
    }
   
    
</style>