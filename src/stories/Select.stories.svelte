<script lang="ts">
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Select } from "../lib/components";

  const label = "Select an option";
  const options = ["Option 1", "Option 2", "Option 3"];
</script>

<Meta title="Form Components/Select" component={Select} />

<Template let:args>
  <Select {...args} />
  <Select {...args}>item</Select>
</Template>

<Story name="Select 1" args={{ label, options }} />
