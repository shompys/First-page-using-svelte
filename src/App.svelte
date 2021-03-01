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
	
	:global(:root){
		--color-twitch: rgb(145,71,255);
		--color-github: #24292e;
		--color-gris: #7e7e7e;
		
	}
	:global(p){
		font-size: .9em;
		color: #6c757d;
	}
</style>

