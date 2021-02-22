<script>
    import { Router, Route, Link} from 'svelte-routing';

    import Home from './components/views/Home.svelte';
	
</script>
<main>
	
	<Router>
		<Route path="/home" component={Home} />
		<Route path="/" component={Home} />
	</Router>

</main>

<style>
	
	:global(:root){
		--color-twitch: rgb(145,71,255);
		--color-github: #24292e;
	}
</style>

