<script lang="ts">
  import type { T_File } from "../../types";
  import File from "./File.svelte";

  // import type { T_Device } from "../../types";

  let files: T_File[] = [
    {
      id: 1,
      type: 'pdf',
      name: 'Sample_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
    },
    {
      id: 2,
      type: 'png',
      name: 'Image_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
    },
    {
      id: 3,
      type: 'zip',
      name: 'Compressed_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
    },
    {
      id: 4,
      type: 'wav',
      name: 'Audio_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
    }
  ]
</script>

<section id="files">
  <div class="section-heading">
    <p>Cloud Repository</p>
    <div class="see-all">
      See All
    </div>
  </div>
  <section id="file-list">
    {#each files as file}
      <File {file} />
    {/each}
  </section>

</section>

<style lang="scss">
  .section-heading {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  #files {
    padding: 1rem;
  }

  #file-list {
    width: 100%;

    display: grid;
    
    grid-template-columns: 1fr;
    grid-template-rows: auto;
    grid-gap: .5rem;
  }
</style>