<script lang="ts">
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';

	import Reveal from 'reveal.js';
	import Hightlight from 'reveal.js/plugin/highlight/highlight';
	import Markdown from 'reveal.js/plugin/markdown/markdown';
	import Notes from 'reveal.js/plugin/notes/notes';

	import 'reveal.js/dist/reveal.css';
	import 'reveal.js/dist/theme/black.css';
	import 'reveal.js/plugin/highlight/monokai.css';

	import Presentation from '$lib/components/Presentation.svelte';

	onMount(() => {
		const deck = new Reveal({
			plugins: [Markdown, Hightlight, Notes],
			autoAnimateEasing: 'ease',
			autoAnimateDuration: 1,
			hash: true
			// controls: false,
			// progress: false
		});

		deck.initialize();
	});
</script>

<div class="reveal">
	<div class="slides">
		<Presentation />
	</div>
</div>
