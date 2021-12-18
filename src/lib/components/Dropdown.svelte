<script lang="ts">
  // Svelte
  import { createEventDispatcher } from "svelte";

  // Props
  export let placement: "bottom" | "top" | "left" | "right" = "bottom";
  export let hover = false;
  export let end = false;
  export let items: any[] = [];

  const dispatch = createEventDispatcher();
</script>

<div
  class="dropdown text-base-content"
  class:dropdown-end={end}
  class:dropdown-top={placement === "top"}
  class:dropdown-left={placement === "left"}
  class:dropdown-right={placement === "right"}
>
  <slot />
  <ul
    tabindex="0"
    class="p-2 shadow menu dropdown-content bg-base-100 rounded-box w-52 max-h-96 overflow-y-auto"
  >
    {#each items as item, i}
      <li on:click={() => dispatch("click", { index: i, item })}>
        <a><slot name="item" {item} /></a>
      </li>
    {/each}
  </ul>
</div>
