<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import { Dropdown, Button } from "../lib/components";

  const menuItems = ["Item 1", "Item 2", "Item 3", "Item 4"];
</script>

<Meta title="Form Components/Dropdown" component={Dropdown} />

<Template let:args>
  <div class="m-4 flex justify-center items-center">
    <Dropdown {...args}
      ><Button>Dropdown</Button>
      <svelte:fragment slot="menu-item" let:menuItem>{menuItem}</svelte:fragment
      >
    </Dropdown>
  </div>
</Template>

<Story
  name="Dropdown 1"
  args={{
    menuItems,
  }}
/>

<Story
  name="Dropdown End"
  args={{
    menuItems,
    end: true,
  }}
/>

<Story
  name="Dropdown Top"
  args={{
    menuItems,
    placement: "top",
  }}
/>

<Story
  name="Dropdown Left"
  args={{
    menuItems,
    placement: "left",
  }}
/>

<Story
  name="Dropdown right"
  args={{
    menuItems,
    placement: "right",
  }}
/>
