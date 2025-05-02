<script>
	//@ts-nocheck

	import { onMount } from 'svelte';
	import Ilovenibbi from '$lib/challenges/ilovenibbi.svelte';
	import Rahimisdumb from '$lib/challenges/rahimisdumb.svelte';
	import Garbagecollector from '$lib/challenges/garbagecollector.svelte';
	import Areyoucurious from '$lib/challenges/areyoucurious.svelte';
	import Welcomehunter from '$lib/challenges/welcomehunter.svelte';

	var key;
	var page;

	onMount(async () => {
		// get the GET parameters
		const params = new URLSearchParams(window.location.search);

		key = params.get('key');

		switch (key) {
			case 'ilovenibbi':
				page = Ilovenibbi;
				break;
			case 'garbagecollector':
				page = Garbagecollector;
				break;
			case 'rahimisdumb':
				page = Rahimisdumb;
				break;
			case 'areyoucurious':
				page = Areyoucurious;
				break;
			case 'welcomehunter':
			case 'WelcomeHunter':
			case 'Welcomehunter':
			case 'WELCOMEHUNTER':
				page = Welcomehunter;
				break;
			default:
				page = null;
				break;
		}
	});
</script>

{#if key}
	{#if page}
		<svelte:component this={page} />
	{:else}
		<h1>Incorrect key !</h1>
	{/if}
{:else}
	<h1>Please enter a valid key in the page! (ex. /goto?key=hahaha)</h1>
{/if}
