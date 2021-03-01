<script>
    export let message= 'no-data', background= '', color= '#fff', type='button';
</script>

<!-- particularidad de svelte declarar un evento para utilizarlo en la declaracion del componente en otro scope -->

<button style={`background: ${background}; color: ${color}`} {type} on:click>
    {message}
</button>

<style>
    button{
        display: flex;
        justify-content: center;
        align-items: center;
        cursor:pointer;
        text-align: center;
        width: 15rem;
        height: 2.8rem;
        font-size: 1.1em;
        padding: .8rem 0 .8rem 0;
        border-radius: .3rem;
        text-shadow: 0 1px 0 rgba(255,255,255,.3);
        /* box-shadow: 0px 1px 2px 1px #2B2B2B; */
    }
    button:hover{
        background: rgba(255,255,255,.3);
        /* filter:brightness(.9) */
    }
</style>