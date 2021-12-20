<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Kbd } from "../lib/components";
</script>

<Meta title="Kbd" component={Kbd} />

<Template let:args>
  <Kbd key="CTRL" {...args} />
  +
  <Kbd key="C" {...args} />
</Template>

<Story name="Kbd" />
