<script lang="ts">
	import * as m from '$lib/paraglide/messages.js';
	import Header from './header.svelte';
	import Footer from './footer.svelte';

	let name = $state('visitor');
</script>

<div class="layout">
	<Header></Header>
	<div>
		<h1 class="title">{m.hero_title()}</h1>
		<div class="content-grid">
			<div class="hero">
				<div class="hero-bg">
					<img
						src="./genericimage1.jpg"
						class="hero-img"
						alt="nurse and patient viewing a tablet"
					/>
				</div>
				<div class="hero-content"><h2>{m.hero_text()}</h2></div>
			</div>
			<div class="card-content">
				<div class="card-left">
					<p>{m.user_name()}</p>
					<input type="text" bind:value={name} />
				</div>
				<div class="card-right">
					<h2>{m.hello_world({ name })}</h2>

					<p>{m.card_text()}</p>
				</div>
			</div>
		</div>
	</div>

	<Footer></Footer>
</div>

<style>
	.layout {
		height: 100%;
		min-height: 100vh;
		display: grid;
		grid-template-rows: auto 1fr auto;
		align-items: center;
		align-content: space-between;
		margin-inline: auto;
		padding-inline: 2rem;
	}
	.content-grid {
		display: grid;
		grid-template-columns: 1fr;
		justify-items: center;
		align-content: space-between;
	}
	.title {
		width: 100%;
	}
	.hero {
		display: grid;
		grid-template-areas: 'overlay';
	}
	.hero-bg {
		grid-area: overlay;
	}
	.hero-img {
		max-width: 1200px;
		border-radius: 16px;
	}

	.hero-content {
		grid-area: overlay;
		color: var(--surface-2);
		max-width: 50ch;
		align-self: center;
		padding-left: 24px;
	}
	.card-content {
		margin-block: 32px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 24px;
		justify-items: center;
	}
</style>
