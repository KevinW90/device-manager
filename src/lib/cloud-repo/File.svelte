<script lang="ts">
  import type { T_File } from "../../types";
  export let file: T_File;

  const { type, name, size, modified } = file;

  const filetypeColorMap = {
    pdf: "red",
    png: "blue",
    zip: "green",
    wav: "yellow",
  };
</script>

<div class="file">
  <div class="file-icon" style="background-color: {filetypeColorMap[file.type]}">
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

<style lang="scss">
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
      content: '';
      position: absolute;
      width: .3rem;
      height: .3rem;
      border-radius: 50%;
      background-color: #E5E5E5;
      left: 0;
    }
    
    &::before {
      top: -150%;
    }

    &::after {
      top: 150%;
    }
  }
</style>