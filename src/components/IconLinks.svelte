<script>
  import { onMount } from "svelte";

  export let iconURL;
  export let targetURL = '';

  let isHovered = false;

  function handleClick() {
    if (targetURL) {
      window.open(targetURL, '_blank');
    }
  }
  let svgContent = '';
  onMount(async () => {
    const response = await fetch(iconURL);
    svgContent = await response.text();
  });
</script>

<style>
  :global(svg path) {
    fill: white;
    transition: fill 0.25s ease-in-out;
  }
  :global(svg:hover path) {
    fill: var(--primary);
  }
  a {
    
    margin-right: 0.25em;
  }
</style>

<!-- svelte-ignore a11y-missing-attribute -->
<a href={targetURL} target="_blank">
 {@html svgContent}
</a>