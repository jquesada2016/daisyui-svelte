<script lang="ts">
  // WASM
  import { Backend } from "$wasm";
</script>

<footer class="mt-16 p-10 footer bg-neutral text-neutral-content">
  {#await Backend.getFooterData()}
    <div>
      <span class="footer-title">Loading...</span>
    </div>
  {:then data}
    {#each data.categories as category}
      <div>
        <span class="footer-title">{category.name}</span>
        {#each category.items as item}
          <a class="link link-hover" href="">{item.name}</a>
        {/each}
      </div>
    {/each}
  {/await}
</footer>
