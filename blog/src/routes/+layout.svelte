<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav>
	<a href="/">Home</a>
	<a href="/blog">TestBlog</a>
</nav>

{@render children()}

<style>
	:global(html) {
		--col-bg: rgb(38, 38, 38);
		--col-highlight: rgb(226, 232, 206);
		--col-content: rgb(172, 191, 164);
		--col-header: rgb(255, 127, 17);
		background-color: var(--col-bg);
	}
	:global(h1) {
		color: var(--col-header);
	}

	:global(a) {
		color: var(--col-highlight);
	}

	:global(body) {
		color: var(--col-content);
	}
</style>