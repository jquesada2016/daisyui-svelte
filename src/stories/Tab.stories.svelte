<script lang="ts">
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Tabs } from "../lib/components";

  const tabs = ["Tab 1", "Tab 2", "Tab 3"];
  const activeTab = 1;
</script>

<Meta title="Tabs" component={Tabs} />

<Template let:args>
  <Tabs {...args} let:tab>{tab}</Tabs>
</Template>

<Story name="Tabs" args={{ tabs, activeTab }} />

<Story name="Tabs Bordered" args={{ tabs, activeTab, bordered: true }} />

<Story
  name="Tabs Boxed"
  args={{
    tabs,
    activeTab,
    boxed: true,
  }}
/>

<Story
  name="Tabs Lifted"
  args={{
    tabs,
    activeTab,
    lifted: true,
  }}
/>
