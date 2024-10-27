<script lang="ts">
  import type { Snippet } from "svelte";

  let {
    id,
    lines,
    noescape,
    children
  }: {
    id?: string | null;
    lines?: string | boolean | null;
    noescape?: boolean;
    children: Snippet;
  } = $props();
</script>

<pre data-id={id || null}>
  <code
    class="overflow-x-auto"
    data-trim
    data-line-numbers={lines || null}
    data-noescape={noescape || null}
  >
    {@render children()}
  </code>
</pre>