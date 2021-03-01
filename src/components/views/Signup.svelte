<script>
    import Nav from '../layout/Nav.svelte';
    import ButtonBack from '../common/ButtonBack.svelte';
    import FormSignup from '../layout/FormSignup.svelte';

    
</script>

<Nav />
<ButtonBack />
<article>
    
<FormSignup/>
<p>¿Ya tienes una cuenta?</p>
</article>


<style>

article{
    display: grid;
    padding: 2em;
    justify-items: center;
    gap: 2em;
}


</style>