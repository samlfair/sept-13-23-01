<script>
	import { PrismicRichText } from '@prismicio/svelte';

	import Heading1 from './Heading1.svelte';
	import Paragraph from './Paragraph.svelte';

	/** @type {import("@prismicio/client").Content.HeroTextSlice} */
	export let slice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<PrismicRichText
		field={slice.primary.text}
		components={{
			heading1: Heading1,
			paragraph: Paragraph
		}}
	/>
</section>

<style>
	section {
		background-image: var(--gradient-30), var(--noise-5);
		filter: var(--noise-filter-1);
		background-size: cover;
		text-transform: uppercase;
		flex-direction: row;
		align-items: flex-start;
		justify-content: center;
		gap: var(--size-4);
		padding: var(--size-14) 0 var(--size-13);
	}
</style>
