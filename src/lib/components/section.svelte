<div class="container">
	<slot />
</div>

<style>
	.container {
		width: calc(100% - 20px);
		max-width: 960px;
		min-height: calc(100vh - 150px);
		margin: 2vh auto 0;
		padding: 20px;
		background: rgba(255, 255, 255, 0.5);
		border-radius: 10px;
		border: 3px inset #1f302c;
	}
</style>
