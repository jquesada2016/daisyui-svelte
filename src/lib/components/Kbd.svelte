<script lang="ts">
  // Props
  export let key = "";
  export let size: "xs" | "sm" | "md" | "lg" | undefined = undefined;
</script>

<kbd
  class="kbd"
  class:kbd-xs={size === "xs"}
  class:kbd-sm={size === "sm"}
  class:kbd-md={size === "md"}
  class:kbd-lg={size === "lg"}>{key}</kbd
>
