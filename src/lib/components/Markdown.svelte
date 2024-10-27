<script lang="ts">
	import type { Snippet } from 'svelte';

	let {
		name,
		external,
		children
	}: {
		name: string;
		external: boolean;
		children: Snippet;
	} = $props();
</script>

{#if external}
	<section data-markdown={name}></section>
{:else}
	<section data-markdown>
		<div data-template>
			{@render children()}
		</div>
	</section>
{/if}
