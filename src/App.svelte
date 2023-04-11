<script lang="ts">
  import Greeting from "./lib/Greeting.svelte";

</script>

<main>
  <Greeting />
</main>

<style lang="scss">
  $base: hsl(227, 42%, 33%);

  :global(html, body) {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
  }
  
  main {
    height: 100vh;
    background-color: $base;
  }
</style>
