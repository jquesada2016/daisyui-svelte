<script lang="ts">
  // Props
  export let heading: string | undefined = undefined;
  export let p: string | undefined = undefined;
  export let imageUrl: string;
</script>

<div class="hero min-h-[50vh]" style={`background-image: url("${imageUrl}");`}>
  <div class:hero-overlay={heading || p} class:bg-opacity-40={heading || p} />
  <div class="text-center hero-content text-neutral-content">
    <div class="max-w-md">
      {#if heading}
        <h1 class="mb-5 text-5xl">{heading}</h1>
      {/if}
      {#if p}
        <p class="mb-5">
          {p}
        </p>
      {/if}
    </div>
  </div>
</div>
