<script>
	import Card from '$lib/components/Card.svelte';
	import Cards from '$lib/components/Cards.svelte';
	import { PrismicImage, PrismicRichText } from '@prismicio/svelte';

	/** @type {import("@prismicio/client").Content.EmceeListSlice} */
	export let slice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<PrismicRichText field={slice.primary.heading} />
	<Cards min={200}>
		{#each slice.items as emcee}
			<Card>
				<PrismicImage field={emcee.photo} />
				<PrismicRichText field={emcee.name} />
				<PrismicRichText field={emcee.bio} />
			</Card>
		{/each}
	</Cards>
</section>

<style>
	section {
		background: var(--blue-9);
	}

	section :global(img) {
		width: 100px;
		height: 100px;
		object-fit: cover;
		transition: border-radius 1s;
		align-self: center;
		margin-bottom: var(--size-2);
	}

	section :global(article):nth-child(1n):hover :global(img) {
		border-radius: var(--radius-blob-5);
	}

	section :global(article):nth-child(5n + 1) :global(img) {
		border-radius: var(--radius-blob-1);
	}

	section :global(article):nth-child(5n + 2) :global(img) {
		border-radius: var(--radius-blob-2);
	}

	section :global(article):nth-child(5n + 3) :global(img) {
		border-radius: var(--radius-blob-3);
	}

	section :global(article):nth-child(5n + 4) :global(img) {
		border-radius: var(--radius-blob-4);
	}

	section :global(article):nth-child(5n + 5) :global(img) {
		border-radius: var(--radius-blob-5);
	}
</style>
