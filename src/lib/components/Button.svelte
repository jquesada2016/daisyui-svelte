<script lang="ts">
  // Props
  export let size: "xs" | "sm" | "md" | "lg" = "md";
  export let kind:
    | "primary"
    | "secondary"
    | "accent"
    | "link"
    | "ghost"
    | "neutral"
    | "info"
    | "success"
    | "warning"
    | "error"
    | "glass" = "primary";
  export let outline = false;
  export let wide = false;
  export let block = false;
  export let shape: "square" | "circle" | undefined = undefined;
  export let active = false;
  export let loading = false;
  export let disabled = false;
  export let href: string | undefined = undefined;
  export let classes: string | undefined = undefined;

  let kindClass: string;
  switch (kind) {
    case "primary": {
      kindClass = "btn-primary";
      break;
    }
    case "secondary": {
      kindClass = "btn-secondary";
      break;
    }
    case "accent": {
      kindClass = "btn-primary";
      kindClass = "btn-accent";
      break;
    }
    case "link": {
      kindClass = "btn-link";
      break;
    }
    case "ghost": {
      kindClass = "btn-ghost";
      break;
    }
    case "neutral": {
      kindClass = "btn-neutral";
      break;
    }
    case "info": {
      kindClass = "btn-info";
      break;
    }
    case "success": {
      kindClass = "btn-success";
      break;
    }
    case "warning": {
      kindClass = "btn-warning";
      break;
    }
    case "error": {
      kindClass = "btn-error";
      break;
    }
    case "glass": {
      kindClass = "glass";
      break;
    }
  }

  let sizeClass: string;
  switch (size) {
    case "lg": {
      sizeClass = "btn-lg";
      break;
    }
    case "md": {
      sizeClass = "btn-md";
      break;
    }
    case "sm": {
      sizeClass = "btn-sm";
      break;
    }
    case "xs": {
      sizeClass = "btn-xs";
      break;
    }
  }

  let shapeClass: string;
  switch (shape) {
    case "circle": {
      shapeClass = "btn-circle";
      break;
    }
    case "square": {
      shapeClass = "btn-square";
      break;
    }
    default: {
      shapeClass = "";
    }
  }
</script>

{#if kind !== "link"}
  <button
    class={`btn ${sizeClass} ${kindClass} ${shapeClass} ${
      classes ? classes : ""
    }`}
    class:btn-outline={outline}
    class:btn-wide={wide}
    class:btn-block={block}
    class:btn-active={active}
    class:loading
    class:btn-disabled={disabled}
    on:click
    ><slot />
  </button>
{:else}
  <a
    class={`btn ${sizeClass} ${kindClass} ${shapeClass} ${
      classes ? classes : ""
    }`}
    class:btn-outline={outline}
    class:btn-wide={wide}
    class:btn-block={block}
    class:btn-active={active}
    class:loading
    class:btn-disabled={disabled}
    {href}
    role="button"
    on:click><slot /></a
  >
{/if}
