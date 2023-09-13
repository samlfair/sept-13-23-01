<script>
	import { PrismicText } from '@prismicio/svelte';

	export let slices;

	function getHeadings(slices) {
		const headings = [];

		slices.forEach((slice) => {
			if (slice.primary.heading) {
				headings.push({
					text: slice.primary.heading,
					id: slice.id
				});
			}
		});

		return headings;
	}

	const headings = getHeadings(slices);
</script>

<nav>
	<ul>
		{#each headings as heading}
			<li><a href="#{heading.id}"><PrismicText field={heading.text} /></a></li>
		{/each}
	</ul>
</nav>

<style>
	nav {
		position: fixed;
		background: var(--purple-12);
		z-index: 1;
		width: 100%;
		font-weight: bold;
		padding: var(--size-4);
	}

	ul {
		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		justify-content: center;
		gap: var(--size-8);
		font-size: var(--font-size-3);
	}

	a {
		color: white;
	}

	a:hover {
		text-decoration: none;
		color: var(--red-6);
	}
</style>
