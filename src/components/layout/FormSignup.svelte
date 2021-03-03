<script>
import Link from 'svelte-routing/src/Link.svelte';
import {fade, fly} from 'svelte/transition';
import Button from "../common/Button.svelte";
import ButtonBack from '../common/ButtonBack.svelte';

    let user = {
        name: "",
        lastname: "",
        username: "",
        email: "",
        password: "",
        receivePassword: "",
    };
    
    let steps = 1;

    const submitHandler = (e) => {
        console.log("ejecuto");
    };
    
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
    
    {#if steps === 1}
        <h3>Registro</h3>
        <p>El usuario será tu ingreso a la plataforma y debes tener acceso al email ya que recibirás un token de verificación.</p>

            <label>
                <span>Nombre</span>
                <input type="text"
                    bind:value={user.name}
                    autoComplete="off"
                    name="name"
                    on:focus={placeholderEffect} 
                    on:blur={placeholderEffectBack}
                />
            </label>
            
            <label>
                <span>Apellido</span>
                <input type="text" 
                    bind:value={user.lastname} 
                    autoComplete="off"
                    name="lastname"
                    on:focus={placeholderEffect} 
                    on:blur={placeholderEffectBack}
                />
            </label>
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
            <label >
                <span>Email</span>
                <input type="text" 
                    bind:value={user.email}
                    on:focus={placeholderEffect}
                    on:blur={placeholderEffectBack}
                    autoComplete="off"
                    name="email"
                />
            </label>
            
        <Button background={"var(--color-twitch)"} message={"Continuar"}  on:click={() => steps = 2}/>
            
    {:else}
        <!-- <div> -->
            <!-- <ButtonBack on:click={() => steps = 1}/> -->
        <h3>Registro</h3>
        <!-- </div> -->
        <p>La contraseña debe tener al menos 8 caracteres, intenta no repetir tu contraseña en otras plataformas.</p>
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
        <label>
            <span>Repita contraseña</span>
            <input type="password"
                bind:value={user.receivePassword} 
                autoComplete="off"
                name="receivePassword"
                on:focus={placeholderEffect}
                on:blur={placeholderEffectBack}
            />
        </label>
        
        <Button background={"var(--color-twitch)"} message={"Registrar"} type={"submit"} />
        <p class="term-service">Al hacer clic en Registrarse, indicas que has leído y aceptas los <Link to="/">Términos del servicio</Link> y el <Link to="/">Aviso de privacidad</Link>.</p>
        
    {/if}
    <p class="have-an-account">
        ¿Ya tienes una cuenta? presiona
    <Link to="/signin"><b class="aqui"> aquí</b></Link>
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
    p{
        text-align: center;
        width: 18rem;
        max-width: 25rem;  
    }
    .term-service{
        /* text-align: center; */
        font-size: .8em;
    }
    .aqui{
        color: var(--color-twitch);
        font-weight: bold;
    }
</style>
