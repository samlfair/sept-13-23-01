<script>
	import { page } from '$app/stores';
</script>

<svelte:head>
	<title>{$page.data.title}</title>
	{#if $page.data.meta_description}
		<meta name="description" content={$page.data.meta_description} />
	{/if}
	{#if $page.data.meta_title}
		<meta name="og:title" content={$page.data.meta_title} />
	{/if}
	{#if $page.data.meta_image}
		<meta name="og:image" content={$page.data.meta_image.url} />
	{/if}
</svelte:head>
<main>
	<slot />
</main>

<style global>
	@import 'open-props/style';
	@import 'open-props/normalize';

	@font-face {
		font-family: 'Anton';
		font-style: normal;
		font-weight: 100 900;
		font-display: swap;
		src: local(''), url('/fonts/Anton.woff2') format('woff2');
		unicode-range: U+20-7E, U+E4, U+E5, U+F6;
	}

	@font-face {
		font-family: 'Overpass';
		font-style: normal;
		font-weight: 100 900;
		font-display: swap;
		src: local(''), url('/fonts/Overpass.woff2') format('woff2');
		unicode-range: U+20-7E, U+E4, U+E5, U+F6;
	}

	@font-face {
		font-family: 'Inter';
		font-style: normal;
		font-weight: 100 900;
		font-display: swap;
		src: local(''), url('/fonts/Inter.woff2') format('woff2');
		unicode-range: U+20-7E, U+E4, U+E5, U+F6;
	}

	main {
		--font-serif: 'Anton';
		--font-sans: 'Overpass';
		font-family: var(--font-sans);
	}

	:global(h2) {
		font-weight: var(--font-weight-5);
	}

	:global(h3) {
		font-weight: var(--font-weight-5);
		font-size: var(--font-size-4);
	}

	:global(h4) {
		font-weight: var(--font-weight-3);
		font-size: var(--font-size-3);
	}

	:global(section) {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: var(--size-10);
		padding: var(--size-11);
	}
</style>
