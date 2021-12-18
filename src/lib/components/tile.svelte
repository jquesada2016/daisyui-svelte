<script lang="ts">
  // Transitions
  import { scale } from "svelte/transition";

  // Icons
  import { NoImage32 } from "carbon-icons-svelte";

  // Props
  export let title: string;
  export let price: string | undefined = undefined;
  export let href: string | undefined = undefined;
  export let imageUrl = "";
</script>

<a in:scale class="card flex-none cursor-pointer rounded-2xl text-sm" {href}>
  {#if price}
    <div
      class="flex justify-end bg-accent px-2 py-1 text-accent-content font-bold rounded-t-2xl"
    >
      {price}
    </div>
  {/if}
  <figure>
    {#if imageUrl}
      <img src={imageUrl} alt="Product Image" />
    {:else}
      <NoImage32 style="widh: 128px; height: 128px; margin: 32px 0px;" />
    {/if}
  </figure>
  <div class="bg-accent px-2 py-1 text-accent-content rounded-b-2xl">
    {title}
  </div>
</a>
