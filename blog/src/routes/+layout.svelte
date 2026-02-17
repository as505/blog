<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav>
	<div class="navBox">
		<a href="/">Home</a>
		<a href="/blog">Blog</a>
	</div>
</nav>

{@render children()}

<style>
	:global(html) {
		--col-bg: rgb(38, 38, 38);
		--col-highlight: rgb(226, 232, 206);
		--col-content: rgb(172, 191, 164);
		--col-header: rgb(255, 127, 17);
		--blog-margin: 15rem;
		--blog-text-width: 60vw;
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
		margin: 0px;
	}

	nav{
		position: absolute;
		top: 1rem;
		left: 1rem;
		z-index: 100000;
	}

	.navBox{
		--navBarRightPadding: 4rem;
		padding: 1rem;
		padding-right: var(--navBarRightPadding);
		background-color: var(--col-bg);
		border-radius: 1rem;
		z-index: 10000;
	}
</style>