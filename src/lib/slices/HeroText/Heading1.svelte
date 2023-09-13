<script>
	export let node;

	const words = node.text.replace(' ', '\n');
</script>

<h1>{words}</h1>

<style>
	h1 {
		font-family: var(--font-serif);
		color: var(--red-5);
		white-space: pre;
		text-align: right;
		font-size: var(--size-11);
		line-height: var(--size-11);
	}
</style>
