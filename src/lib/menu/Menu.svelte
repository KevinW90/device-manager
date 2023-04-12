<script lang="ts">
  let items = [
    'archives',
    'add',
    'map'
  ]
</script>

<div id="menu">
  {#each items as item}
    <div class="item">
      <div class="item-icon"></div>
      <div class="item-label">
        {item}
      </div>
    </div>
  {/each}
</div>

<style lang="scss">
  #menu {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;

    padding: .5rem 0;
    background-color: #fff;
    box-shadow: 0 -2px 10px rgba(black, .3);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }

  .item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;

    &-icon {
      width: 24px;
      height: 24px;
      background-color: black;
      border-radius: 5px;
    }

    &-label {
      text-transform: capitalize;
    }
  }
</style>