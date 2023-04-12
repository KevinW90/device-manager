<script lang="ts">
  import Greeting from "./lib/Greeting.svelte";
  import DeviceList from "./lib/devices/DeviceList.svelte";
  import FileList from "./lib/cloud-repo/RepoList.svelte";
  import Menu from "./lib/menu/Menu.svelte";

</script>

<main>
  <Greeting />
  <DeviceList />
  <FileList />
  <Menu />
</main>

<style lang="scss">
  @use "./scss/variables" as vars;

  :global(html, body) {
    margin: 0;
    padding: 0;
    font-family: 'nunito', sans-serif;
  }

  :global(body) {
    overflow-y: scroll;
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
