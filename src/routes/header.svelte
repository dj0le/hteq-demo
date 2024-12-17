<script lang="ts">
	import type { AvailableLanguageTag } from '$lib/paraglide/runtime';
	import { i18n } from '$lib/i18n';
	import { page } from '$app/stores';
	import { goto } from '$app/navigation';

	function switchToLanguage(newLanguage: AvailableLanguageTag) {
		const canonicalPath = i18n.route($page.url.pathname);
		const localisedPath = i18n.resolveRoute(canonicalPath, newLanguage);
		goto(localisedPath);
	}
</script>

<nav>
	<div><a href="/"><img src="./healhtequity.svg" alt="healthtequity" class="logo" /></a></div>
	<div class="lang">
		<button class="button" onclick={() => switchToLanguage('en')}>
			en <img src="./en-flag.png" alt="" /></button
		>
		<button class="button" onclick={() => switchToLanguage('de')}>
			de <img src="./de-flag.png" alt="" /></button
		>
		<button class="button" onclick={() => switchToLanguage('ba')}>
			ba <img src="./ba-flag.png" alt="" /></button
		>
	</div>
</nav>

<style>
	nav {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding-top: 24px;
	}
	.lang {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		justify-content: end;
		place-items: center;
		gap: 24px;
	}
</style>
