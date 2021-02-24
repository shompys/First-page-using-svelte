<script>
    import {fade, fly} from 'svelte/transition';

    import Button from "../common/Button.svelte";

    let user = {
        name: "",
        lastname: "",
        username: "",
        email: "",
        password: "",
        receivePassword: "",
    };

    let isFirstStep = true;
    
    const placeholderEffect = e => {
        const label = e.target.previousElementSibling;
        const st = label.style;
        st.top= "0";
        st.left= "5px";
        st.fontSize= ".8em";
        st.background= '#fff';
        st.padding= '0 5px 0 5px';
        st.color= 'var(--color-twitch)';
        st.transition= "all .2s ease";
        
    }
    const placeholderEffectBack = e => {
        if(e.target.value === ''){
            const label = e.target.previousElementSibling;
            const st = label.style;
            st.top= '50%';
            st.left= "16px";
            st.fontSize= '.9em';
            st.background= 'none';
            st.padding= '0 0 0 0';
            st.color= '#A2A2A2';
            st.transition= "all .2s .5s ease";
        } 
    }

    const submitHandler = (e) => {
        console.log("ejecuto");
    };



</script>

<form on:submit|preventDefault={submitHandler}>
    {#if isFirstStep}
        <div class="content-block" in:fade out:fly|local={{x:-200 }}>

            <div class="content-labelAndInput">
                <label for="name">Nombre</label>
                <input type="text" bind:value={user.name} id="name" autoComplete="off"  on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>    
            <div class="content-labelAndInput">
                <label for="lastname">Apellido</label>
                <input type="text" bind:value={user.lastname} id="lastname" autoComplete="off" on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>
            <div class="content-labelAndInput">
                <label for="user">Usuario</label>
                <input type="text" bind:value={user.username} id="user" autoComplete="off" on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>
            <div class="content-labelAndInput">
                <label for="email">Email</label>
                <input type="text" bind:value={user.email} id="email" autoComplete="off" on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>

        </div><!--end .content-block-->

        <Button background={"var(--color-twitch)"} message={"Continuar"}  on:click={() => isFirstStep = !isFirstStep}/>
    {:else}
        <div class="content-block" in:fly={{x: 200, delay: 1000}}>

            <div class="content-labelAndInput">
                <label for="password">Contraseña</label>
                <input type="password" bind:value={user.password} id="password" autoComplete="off" on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>
            <div class="content-labelAndInput">
                <label for="receivepassword">Repita contraseña</label>
                <input type="password" bind:value={user.receivePassword} id="receivepassword" autoComplete="off" on:click={placeholderEffect} on:keydown={placeholderEffect} on:mouseleave={placeholderEffectBack} on:keyup={placeholderEffectBack}/>
            </div>

        </div><!--end .content-block-->
        <Button background={"var(--color-twitch)"} message={"Registrar"} type={"submit"} />
    {/if}
    
</form>

<style>
    form {
        display: grid;
        justify-items: center;
        gap: .5em;
        
    }
    .content-block{
        display:grid;
        gap: .5em;
        
    }
    .content-labelAndInput{
        display:grid;
        position:relative;
    }
    label{
        font-size: .9em;
        position: absolute;
        color: #A2A2A2;
        top: 50%;
        transform: translateY(-50%);
        left: 16px;
    }
    
    input {
        border: 1px solid var(--color-twitch);
        padding: 15px;
        width: 18rem;
        border-radius: 0.2rem;
        font-size: 1em;
    }
    input:focus {
        box-shadow: 0px 0px 1px 1px var(--color-twitch);
    }
</style>
