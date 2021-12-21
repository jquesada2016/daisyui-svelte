<script lang="ts">
  // Props
  export let label = "";
  export let value: string | undefined = undefined;
  export let options: any[] = [];
  export let kind:
    | "primary"
    | "secondary"
    | "accent"
    | "info"
    | "success"
    | "warning"
    | "error"
    | undefined = undefined;
  export let size: "xs" | "sm" | "md" | "lg" | undefined = undefined;
  export let values: string[] | undefined = undefined;

  // we have to account for the label
  if (values) {
    values = [undefined, ...values];
  }
</script>

<select
  class="select select-bordered w-full max-w-xs"
  class:select-xs={size === "xs"}
  class:select-sm={size === "sm"}
  class:select-md={size === "md"}
  class:select-lg={size === "lg"}
  class:select-primary={kind === "primary"}
  class:select-secondary={kind === "secondary"}
  class:select-accent={kind === "accent"}
  class:select-info={kind === "info"}
  class:select-success={kind === "success"}
  class:select-warning={kind === "warning"}
  class:select-error={kind === "error"}
  bind:value
  on:change
  on:focus
  on:blur
>
  <option disabled selected>{label}</option>
  {#each options as option, i}
    <option value={values?.[i] || i}>
      {#if !$$slots.default}
        {option}
      {:else}
        <slot {i} {option} />
      {/if}
    </option>
  {/each}
</select>
