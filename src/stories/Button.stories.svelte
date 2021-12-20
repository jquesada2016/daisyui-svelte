<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Button } from "../lib/components";
</script>

<Meta title="Button" component={Button} />

<Template let:args>
  <Button {...args}>
    {args.label}
  </Button>
</Template>

<Story
  name="Primary"
  args={{
    kind: "primary",
    label: "Button",
  }}
/>
