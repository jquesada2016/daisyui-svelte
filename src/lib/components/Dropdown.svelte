<script lang="ts">
  // Svelte
  import { createEventDispatcher } from "svelte";

  // Props
  export let menuItems: any[] = [];
  export let placement: "top" | "left" | "right" | "bottom" = "bottom";
  export let end = false;

  const dispatch = createEventDispatcher();
</script>

<div
  class="dropdown"
  class:dropdown-end={end}
  class:dropdown-top={placement === "top"}
  class:dropdown-left={placement === "left"}
  class:dropdown-right={placement === "right"}
>
  <span tabindex="0"><slot /></span>
  <ul
    tabindex="0"
    class="p-2 shadow menu dropdown-content bg-base-100 rounded-box w-52"
  >
    {#each menuItems as menuItem}
      <li>
        <a><slot name="menu-item" {menuItem} /></a>
      </li>
    {/each}
  </ul>
</div>
