<script>
	export let min = 200;
</script>

<div class="cards" style:--min={min + 'px'}>
	<slot />
</div>

<style>
	.cards {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(var(--min), 1fr));
		gap: var(--size-8);
	}
</style>
