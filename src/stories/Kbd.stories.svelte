<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Kbd } from "../lib/components";
</script>

<Meta title="Kbd" component={Kbd} />

<Template let:args>
  <Kbd key="CTRL" />
  +
  <Kbd key="C" />
</Template>

<Story
  name="Kbd"
  args={{
    keys: ["ctrl", "C"],
  }}
/>
