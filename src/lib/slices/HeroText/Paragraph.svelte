<script>
	export let node;

	const words = node.text.replace(' ', '\n');
</script>

<p>{words}</p>

<style>
	p {
		color: black;
		white-space: pre;
		text-align: left;
		font-size: var(--size-7);
		font-weight: 200;
		font-family: var(--font-serif);
		color: var(--purple-11);
		font-size: var(--size-8);
		line-height: 120%;
	}
</style>
