<script lang="ts">
  // Props
  export let tip: string;
  export let open = false;
  export let placement: "top" | "bottom" | "left" | "right" = "top";
  export let kind:
    | "primary"
    | "secondary"
    | "accent"
    | "info"
    | "success"
    | "warning"
    | "error"
    | undefined = undefined;
  export let classes = "";
</script>

<div
  data-tip={tip}
  class={`tooltip ${classes}`}
  class:tooltip-left={placement === "left"}
  class:tooltip-right={placement === "right"}
  class:tooltip-bottom={placement === "bottom"}
  class:tooltip-primary={kind === "primary"}
  class:tooltip-secondary={kind === "secondary"}
  class:tooltip-accent={kind === "accent"}
  class:tooltip-info={kind === "info"}
  class:tooltip-success={kind === "success"}
  class:tooltip-warning={kind === "warning"}
  class:tooltip-error={kind === "error"}
  {...$$restProps}
>
  <slot />
</div>
