<script lang="ts">
  import DeviceCard from "./DeviceCard.svelte";

  import type { T_Device } from "../../types";

  let devices: T_Device[] = [
    {
      id: 1,
      name: 'Blue Yubikey',
      registered: 'Oct 2, 2019',
      lastUsed: 'Nov 5, 2020',
      color: 'hsl(196, 74%, 38%)'
    },
    {
      id: 2,
      name: 'John\'s Pixel',
      registered: 'Oct 2, 2019',
      lastUsed: 'Nov 5, 2020',
      color: 'hsl(208, 82%, 39%)'
    },
    {
      id: 3,
      name: 'John\'s Laptop',
      registered: 'Oct 2, 2019',
      lastUsed: 'Nov 5, 2020',
      color: 'hsl(244, 41%, 48%)'
    }
  ]
</script>

<section id="devices">
  <div class="see-all">
    See All
  </div>
  <section id="device-list">
    {#each devices as device}
      <DeviceCard data={device} />
    {/each}
  </section>

</section>

<style lang="scss">
  .see-all {
    text-align: right;
    padding: 1rem;
    color: white;
  }

  #device-list {
    width: 100%;

    display: grid;
    
    grid-template-columns: 0 repeat(3, calc(50% - 2rem)) 0;
    grid-template-rows: auto;
    grid-gap: 1rem;

    overflow-x: auto;

    &::before,
    &::after {
      content: '';
    }
  }

  
</style>