<script>
import Nav from '../layout/Nav.svelte';
import BoxTopic from '../layout/BoxTopic.svelte';
</script>

<Nav />
<article>
    <section class="content-algo">
    
    </section>
    <section class="content-topic">
        <BoxTopic background={'var(--color-twitch)'} svg={'fab fa-twitch'} topic={'Twitch'}/>
        <BoxTopic background={'#A7A7A7'} svg={'fas fa-book'} topic={'Foro'}/>
        <BoxTopic background={'#5CCCFD'} svg={'fas fa-comments'} topic={'chat'}/>
    </section>
</article>
<style>
    .content-topic{
        padding: 15px;
        display:grid;
        gap: 15px;
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        grid-auto-rows: minmax(150px, auto);
        
    }
</style>