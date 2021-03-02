<script>
import {Link} from 'svelte-routing';

import Button from "../common/Button.svelte";

let user = {
    username: '',
    password: ''
}

    const submitHandler = () => {
        console.log('ejecuto')
    }

    const placeholderEffect = e => {
        const labelSt = e.target.parentElement.style;
        const spanSt = e.target.previousElementSibling.style;

        labelSt.boxShadow=" 0px 0px 1px 1px var(--color-twitch)";
        spanSt.color= 'var(--color-twitch)'
        spanSt.top='-9px';
        spanSt.left='3px';
        spanSt.fontSize='.8em';
        spanSt.backgroundColor='#fff';
        spanSt.padding= '0 5px';
        labelSt.transition = 'all .5s ease';
        spanSt.transition= 'all .5s ease';
    }

    const placeholderEffectBack = e => {
        if(e.target.value.trim().length === 0){

            e.target.value = e.target.value.trim();

            user = { ...user, [e.target.name] : e.target.value }

            const labelSt = e.target.parentElement.style;
            const spanSt = e.target.previousElementSibling.style;
            labelSt.boxShadow="none";
            spanSt.color='#A2A2A2';
            spanSt.top='15px';
            spanSt.left='15px';
            spanSt.fontSize='.9em';
            spanSt.backgroundColor= 'transparent';
            spanSt.padding= '0 0';
            labelSt.transition = 'all .5s ease';
            spanSt.transition= "all .5s ease";
        }
    }

</script>



<form on:submit|preventDefault={submitHandler}>
    <h3>Iniciar sesión</h3>
    <label>
        <span>Usuario</span>
        <input type="text" 
            bind:value={user.username}
            autoComplete="off"
            name="user"
            on:focus={placeholderEffect} 
            on:blur={placeholderEffectBack}
        />
    </label>
    <label>
        <span>Contraseña</span>
        <input type="password"
            bind:value={user.password} 
            autoComplete="off"
            name="password"
            on:focus={placeholderEffect}
            on:blur={placeholderEffectBack}
        />
    </label>
    
    <Button background={"var(--color-twitch)"} message={"Entrar"} type={'submit'}/>

    <p>
        Para crear cuenta presiona
        <Link to="/signup">
            <b class="aqui">aquí</b>
        </Link>
    </p>

</form>

<style>
    form {
        display: grid;
        justify-items: center;
        gap: 2em;
        
        
    }
    label{
        display:block;
        position:relative;
        border: 1px solid var(--color-twitch);
        width: 18rem;
        border-radius: 0.2rem;
    }
    input {
        display:block;
        border: none;
        width: 100%;
        font-size: .9em;
        padding: 15px;
        
    }
    span{
        position:absolute;
        top: 15px;
        left: 15px;
        color: #A2A2A2;
        font-size: .9em;
    }
    
    span:hover{
        cursor:text
    }
    .aqui{
        color: var(--color-twitch);
        font-weight: bold;
    }
</style>
