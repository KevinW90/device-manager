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
  
  main {
    position: relative;
    z-index: 0;
    width: 100%;
    height: 100vh;
    background-color: vars.$base;

    display: flex;
    flex-direction: column;
    gap: 1rem;

    // allow scrolling because of fixed menu
    padding-bottom: 66px;
  }
</style>
