<script>
	import Fa from 'svelte-fa/src/fa.svelte';
	import { faBars, faLink, faTimes } from '@fortawesome/free-solid-svg-icons';
	import { fly, fade } from 'svelte/transition';

	const delayInterval = 50;

	export let isOpen = false;
</script>

<button on:click={() => (isOpen = !isOpen)} class={isOpen ? 'navButton close' : 'navButton'}>
	<div class="faIcon">
		{#if isOpen}
			<Fa icon={faTimes} />
		{:else}
			<Fa icon={faBars} class="faIcon" />
		{/if}
	</div>
</button>
{#if isOpen}
	<div class="navOverlay" transition:fade on:click={() => (isOpen = false)} />
	<div id="navContainer" transition:fly={{ x: 300, duration: 500 }}>
		<nav on:click={() => (isOpen = false)}>
			<ul>
				<li transition:fly={{ x: 300, y: 200, duration: 250, delay: delayInterval }}>
					<a href="/">Home</a>
				</li>
				<li transition:fly={{ x: 300, y: 200, duration: 250, delay: delayInterval * 2 }}>
					<a href="/new-england">New England Colonies</a>
				</li>
				<li transition:fly={{ x: 300, y: 200, duration: 250, delay: delayInterval * 3 }}>
					<a href="/middle">Middle Colonies</a>
				</li>
				<li transition:fly={{ x: 300, y: 200, duration: 250, delay: delayInterval * 4 }}>
					<a href="/southern">Southern Colonies</a>
				</li>
			</ul>
		</nav>
	</div>
{/if}

<style>
	.navOverlay {
		position: fixed;
		width: 100vw;
		height: 100vh;
		inset: 0;
		background: rgba(0, 0, 0, 0.5);
	}
	#navContainer {
		position: absolute;
		top: 0;
		right: 0;
		width: 100%;
		max-width: 325px;
		background: #fff;
		height: 100vh;
		padding: 85px 0 0 30px;
	}
	#navContainer a {
		color: #000;
		text-decoration: none;
	}
	.navButton {
		background: #fff;
		color: #000;
		border-radius: 50%;
		border: none;
		font-size: 42px;
		padding: 0;
		width: 60px;
		height: 60px;
		position: absolute;
		top: 10px;
		right: 10px;
		outline: none;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: center;
		z-index: 50;
		transition: all 0.33s ease-in-out;
	}
	.navButton.close {
		right: 260px;
		width: 50px;
		height: 50px;
		border: 2px solid #fff;
		border-radius: 50%;
	}
	.faIcon {
		margin: 0;
		padding: 0;
		font-size: 32px;
	}

	ul {
		list-style: none;
		margin-left: 0;
		text-align: left;
		padding: 0;
	}
	li {
		text-decoration: none;
	}
	nav {
		width: 100%;
		height: 100%;
		overflow: scroll;
	}
</style>
