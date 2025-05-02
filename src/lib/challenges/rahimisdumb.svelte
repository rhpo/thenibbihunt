<script>
	import img from '$lib/rahim.jpg';
	import { onMount } from 'svelte';

	onMount(() => {
		// invert the color of the body each 1s
		setInterval(() => {
			document.documentElement.style.filter =
				document.documentElement.style.filter === 'invert(1)' ? 'invert(0)' : 'invert(1)';
		}, 400);
	});
</script>

<h2>Challenge 4 - Remember how rahim is dumb?</h2>

<p>In fact, he was lost in this devshroom hackathon, (RIGHT NOW)</p>
<p>there is a bag in one of the ESST's backyard's garbage cans</p>
<p>
	find Rahim first (more important), you could go ask him about his favorite color, maybe that could
	help you finding the <i>hint?</i>
</p>

<i>Rahim:</i>
<br />

<img src={img} alt="Rahim" width="100" />

<br />
<br />

<style>
	:global(body) {
		background-color: white;
		color: black;
	}
</style>
