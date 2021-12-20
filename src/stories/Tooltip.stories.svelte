<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Tooltip, Button } from "../lib/components";
</script>

<Meta title="Tooltip" component={Tooltip} />

<Template let:args>
  <div class="m-4 flex justify-center items-center">
    <Tooltip {...args}>
      <Button>I am a button</Button>
    </Tooltip>
  </div>
</Template>

<Story
  name="Top"
  args={{
    tip: "I am a tooltip",
  }}
/>

<Story
  name="Bottom"
  args={{
    tip: "I am a tooltip",
    placement: "bottom",
  }}
/>

<Story
  name="Left"
  args={{
    tip: "I am a tooltip",
    placement: "left",
  }}
/>

<Story
  name="Right"
  args={{
    tip: "I am a tooltip",
    placement: "right",
  }}
/>
