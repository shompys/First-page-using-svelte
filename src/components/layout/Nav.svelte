<script>
import {Router,Link} from 'svelte-routing';

import logo from '../assets/images/index';
import ButtonLink from '../common/ButtonLink.svelte';
export let user = false;

$: grid = user && 'grid-template-columns: repeat(1, 1fr);'
</script>

<nav>
    <div class="nav__part-one">
        <Link to="/home"><img src={logo.logo} alt="logo"></Link>
    </div>
    <div class="nav__part-two" style={grid}>
        {#if user}
            <ButtonLink to={'/cambiaresto'} message={'Cerrar sesion'} background={'var(--color-twitch)'} />
        {:else}
            <ButtonLink to={'/signin'} message={'Iniciar sesión'} background={'#7e7e7e'} />
            <ButtonLink to={'/signup'} message={'Registrarse'} background={'var(--color-twitch)'} />
        {/if}
            
    </div>
</nav>

<style>
     nav{
        
        background-color: var(--color-github);
        display:flex;
        justify-content: space-between;
        padding: .5rem;
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
            grid-template-columns: repeat(2, 1fr);
            gap: .5rem;
            align-items: center;
    }
    
    @media screen and (min-width: 768px){
        
        
    }
   
    
</style>