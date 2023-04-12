<script lang="ts">
  import type { T_File } from "../../types";

  // import type { T_Device } from "../../types";

  let files: T_File[] = [
    {
      id: 1,
      type: 'pdf',
      name: 'Sample_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
      color: 'red'
    },
    {
      id: 2,
      type: 'png',
      name: 'Image_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
      color: 'blue'
    },
    {
      id: 3,
      type: 'zip',
      name: 'Compressed_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
      color: 'green'
    },
    {
      id: 4,
      type: 'wav',
      name: 'Audio_File',
      size: '1.2 MB',
      modified: 'Oct 2, 2019',
      color: 'yellow'
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
      <div class="file">
        <div class="file-icon" style="background-color: {file.color}">
        </div>
        <div class="file-info">
          <div class="file-name">
            {file.name}.{file.type}
          </div>
          <div class="file-meta">
            {file.size}
            <span class="dot">•</span>
            Modified {file.modified}
          </div>
        </div>
        <div class="more-actions-icon">
        </div>
      </div>
    {/each}
  </section>

</section>

<style lang="scss">
  .section-heading {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: white;
  }

  .see-all {
    text-align: right;
    color: white;
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

  .file {
    display: flex;
    // justify-content: space-between;
    gap: 1rem;
    align-items: center;
    padding: 1rem 1.5rem;
    border-radius: .5rem;
    background-color: white;

    &-icon {
      width: 2rem;
      height: 2.5rem;
      border-radius: .5rem;
      background-color: red;
    }

    &-info {
      flex: 1;
      display: flex;
      flex-direction: column;
      gap: .3rem;
    }

    &-meta {
      color: #BDBDBD;
    }
  }  

  .more-actions-icon {
    width: .3rem;
    height: .3rem;
    border-radius: 50%;
    background-color: #E5E5E5;

    position: relative;

    &::before, &::after {
      position: absolute;
      width: .3rem;
      height: .3rem;
      border-radius: 50%;
      background-color: #E5E5E5;
    }
    &::before {
      content: '';
      top: -150%;
      left: 0;
    }

    &::after {
      content: '';
      top: 150%;
      left: 0;
    }
  }
</style>