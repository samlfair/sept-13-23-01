<article>
	<slot />
</article>

<style>
	article {
		background: rgba(0, 0, 0, 0.2);
		border: 1px solid rgba(0, 0, 0, 0.6);
		border-radius: var(--radius-3);
		padding: var(--size-4);
		box-shadow: var(--shadow-2);

		display: flex;
		flex-direction: column;
		align-items: left;
		gap: var(--size-3);
	}

	@media (prefers-color-scheme: light) {
		article {
			border: 1px solid rgba(0, 0, 0, 0.2);
			background: rgba(255, 255, 255, 0.2);
		}
	}
</style>
