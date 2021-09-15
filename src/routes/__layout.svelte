<script>
	import '$lib/css/reset.css';
	import '$lib/css/style.css';
	import Nav from '$lib/components/nav.svelte';
</script>

<main class="container">
	<header>
		<p>Colonial Studies</p>
		<Nav />
	</header>
	<slot />
</main>

<style>
	header {
		width: 100%;
		text-align: center;
		padding: 20px 10px;
		background: rgba(255, 255, 255, 0.5);
	}
	header p {
		font-size: clamp(32px, 5vw, 50px);
		font-weight: 800;
		margin: 0;
	}
</style>
