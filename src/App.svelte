<script>
import { Router, Route, Link} from 'svelte-routing';


import Home from './components/views/Home.svelte';
import Signin from './components/views/Signin.svelte';
import Signup from './components/views/Signup.svelte';




</script>

<main>
	
	<Router>
		<Route path="/" component={Home} />
		<Route path="/home" component={Home} />
		<Route path="/signin" component={Signin} />
		<Route path="/signup" component={Signup} />
	</Router>
	
</main>

<style>
	main{
		min-height: 100%;
	}
	:global(:root){
		--color-twitch: rgb(145,71,255);
		--color-github: #24292e;
		--color-gris: #7e7e7e;
		--color-title: #575757;
		--color-text: #6c757d;
	}
	:global(p){
		font-size: .9em;
		color: var(--color-text);
	}
	:global(h3){
		color: var(--color-title);
	}
</style>

