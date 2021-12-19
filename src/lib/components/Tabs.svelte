<script lang="ts">
  // Svelte
  import { createEventDispatcher } from "svelte";

  // Props
  export let tabs: any[] = [];
  export let activeTab: number | undefined = undefined;
  export let bordered = false;
  export let boxed = false;
  export let lifted = false;
  export let size: "xs" | "sm" | "md" | "lg" | undefined = undefined;
  export let tabsContainerClasses: string = "";
  export let tabContainerClasses: string = "";
  export let tabsContainerRestProps: any = undefined;
  export let tabContainerRestProps: any = undefined;

  const dispatch = createEventDispatcher();
</script>

<div
  class={`tabs ${tabsContainerClasses}`}
  class:tabs-boxed={boxed}
  {...tabsContainerRestProps}
>
  {#each tabs as tab, i}
    <span
      class={`tab ${tabContainerClasses}`}
      class:tab-active={i == activeTab}
      class:tab-bordered={bordered}
      class:tab-lifted={lifted}
      class:tab-xs={size === "xs"}
      class:tab-sm={size === "sm"}
      class:tab-md={size === "md"}
      {...tabsContainerRestProps}
      class:tab-lg={size === "lg"}
      {...tabContainerRestProps}
      on:click={() => dispatch("tabChange", i)}><slot {tab} /></span
    >
  {/each}
</div>
