<script lang="ts">
  import { fade } from "svelte/transition";

  let { data, children } = $props();
</script>

<a href="/test">Link that works</a>
<a href="/test" target="_self">Link that doesn't work</a>
{#key data.pathname}
  <main in:fade={{ duration: 100, delay: 200 }} out:fade={{ duration: 100 }}>
    {@render children()}
  </main>
{/key}
