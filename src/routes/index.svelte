<script context="module" lang="ts">
	export const prerender = true;

	export const load = async ({ page, fetch, session, context }) => {
		console.log('--load---')
		console.log(page)
		console.log(page.query.get('code'))

		return {
			status: 200
		}
	}

</script>

<script lang="ts">
	import Counter from '$lib/Counter/index.svelte';
	import { page } from '$app/stores';

	console.log('--stores---')
	console.log($page)
	console.log($page.query.get('code'))
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<div class="welcome">
			<picture>
				<source srcset="svelte-welcome.webp" type="image/webp">
				<img src="svelte-welcome.png" alt="Welcome"/>
			</picture>
		</div>

		to your new<br />SvelteKit app
	</h1>

	<h2>
		try editing <strong>src/routes/index.svelte</strong>
	</h2>

	<Counter />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
