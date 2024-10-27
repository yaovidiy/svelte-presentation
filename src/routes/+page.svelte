<script lang="ts">
	import { browser } from '$app/environment';
	import * as m from '$lib/paraglide/messages.js';
	import Slides from '$lib/components/Slides.svelte';

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

<svelte:head>
	<title>
		{m.appTitle()}
	</title>
</svelte:head>

{#if browser}
	<div class="flex text-center md:text-left gap-5 fixed top-5 right-10 z-50 text-white">
		<a href="https://svelte.dev/docs/svelte/overview" target="_blank" rel="noreferrer">Svelte Docs</a>
		<a href="https://svelte.dev/playground/hello-world" class="mr-5" target="_blank" rel="noreferrer">Have fun in Svelte Playground!</a>
		<button onclick={() => switchToLanguage('en')}>en</button>
		<button onclick={() => switchToLanguage('uk')}>uk</button>
	</div>
	<Slides />
{:else}
	<p>Server-side rendering is not supported</p>
{/if}
