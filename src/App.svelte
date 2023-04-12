<script lang="ts">
  import Greeting from "./lib/Greeting.svelte";
  import DeviceList from "./lib/device-list/DeviceList.svelte";

</script>

<main>
  <Greeting />
  <DeviceList />
</main>

<style lang="scss">
  @use "./scss/variables" as vars;

  :global(html, body) {
    margin: 0;
    padding: 0;
    font-family: 'nunito', sans-serif;
  }
  
  main {
    height: 100vh;
    background-color: vars.$base;
    overflow: hidden;

    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
</style>
