<script lang="ts">
  export let anchor: string = "";
  export let name: string = "";
  export let style: string = "";
</script>

<a href={`#${anchor}`} style={style}>{name}</a>

<style>
  a {
    font-size: 0.8em;
    text-decoration: none;
    color: white;
    transition: color 0.25s ease-in-out;
  }
  a:hover {
    color: var(--primary);
  }
</style>
