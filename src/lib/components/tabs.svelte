<script lang="ts">
  // Props
  export let tabs: any[];
  export let size: "xs" | "sm" | "md" | "lg" | undefined = undefined;
  export let activeTab: number | undefined = undefined;
</script>

<div
  class="tabs"
  class:tab-xs={size === "xs"}
  class:tab-sm={size === "sm"}
  class:tab-md={size === "md"}
  class:tab-lg={size === "lg"}
>
  {#each tabs as tab, i}
    <a
      href={`/${tab !== tabs[0] ? tab : ""}`}
      class="tab tab-bordered"
      class:tab-active={i === activeTab}>{tab}</a
    >
  {/each}
</div>
