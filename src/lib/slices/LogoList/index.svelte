<script>
	import { PrismicImage, PrismicLink, PrismicRichText } from '@prismicio/svelte';

	/** @type {import("@prismicio/client").Content.LogoListSlice} */
	export let slice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<PrismicRichText field={slice.primary.heading} />
	<div class="logos">
		{#each slice.items as item}
			<div class="logo">
				<PrismicImage field={item.logo} />
			</div>
		{/each}
	</div>
	<PrismicLink class="cta" field={slice.primary.button_link}>
		{slice.primary.button_text}
	</PrismicLink>
</section>

<style>
	section {
		background: var(--choco-2);
	}

	section .logos {
		display: grid;
		width: 100%;
		max-width: var(--size-content-3);
		grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
		gap: var(--size-8);
		flex-wrap: wrap;
	}

	.logo {
		background: var(--choco-1);
		width: 100%;
		aspect-ratio: 1;
		padding: 20%;
		border-radius: var(--radius-round);
		display: flex;
		align-items: center;
	}

	section :global(img) {
		height: auto;
		max-width: 100%;
		max-height: 100%;
		object-fit: contain;
	}

	section :global(a.cta) {
		font-size: var(--font-size-fluid-1);
		font-weight: var(--font-weight-5);

		padding-inline: var(--size-6);
		padding-block: var(--size-7);
		line-height: 0;

		color: var(--gray-2);
		border: var(--border-size-2) solid var(--purple-12);
		background-color: var(--purple-10);
		border-radius: var(--radius-2);
	}

	section :global(a.cta:hover) {
		text-decoration: none;
		background-color: var(--purple-2);
		color: var(--gray-10);
	}
</style>
