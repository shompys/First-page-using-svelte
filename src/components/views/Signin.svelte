<script>
import {Link} from 'svelte-routing';

import Separator from '../common/Separator.svelte';
import FormSignin from '../layout/FormSignin.svelte';
import Nav from '../layout/Nav.svelte';
</script>

<Nav />

<article>

    <FormSignin />

    <p>
        Para crear cuenta presiona
        <Link to="/signup">
            <span>aquí</span>
        </Link>
    </p>

    <Separator />

    
    
    
</article>

<style>

    article{
        display: grid;
        padding: 2em;
        justify-items: center;
        gap: 2em;
    }
    span{
        color: var(--color-twitch);
        font-weight: bold;
    }

</style>