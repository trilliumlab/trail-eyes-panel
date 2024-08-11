<script lang="ts">
  import CircleUser from 'lucide-svelte/icons/circle-user';
  import { Button } from '$lib/components/ui/button/index.js';
  import * as DropdownMenu from '$lib/components/ui/dropdown-menu/index.js';
  import { userPrefersMode } from 'mode-watcher';
</script>

<DropdownMenu.Root>
  <DropdownMenu.Trigger asChild let:builder>
    <Button builders={[builder]} variant="ghost" size="icon" class="rounded-full">
      <CircleUser class="h-5 w-5" />
      <span class="sr-only">Toggle user menu</span>
    </Button>
  </DropdownMenu.Trigger>
  <DropdownMenu.Content align="end">
    <DropdownMenu.Label>My Account</DropdownMenu.Label>
    <DropdownMenu.Separator />
    <DropdownMenu.Item>Settings</DropdownMenu.Item>
    <DropdownMenu.Sub>
      <DropdownMenu.SubTrigger>Color Theme</DropdownMenu.SubTrigger>
      <DropdownMenu.SubContent
        transitionConfig={{
          x: 10,
          y: 0,
        }}
      >
        <DropdownMenu.RadioGroup bind:value={$userPrefersMode}>
          <DropdownMenu.RadioItem indicator="checkmark" value="light">Light</DropdownMenu.RadioItem>
          <DropdownMenu.RadioItem indicator="checkmark" value="dark">Dark</DropdownMenu.RadioItem>
          <DropdownMenu.RadioItem indicator="checkmark" value="system"
            >System</DropdownMenu.RadioItem
          >
        </DropdownMenu.RadioGroup>
      </DropdownMenu.SubContent>
    </DropdownMenu.Sub>
    <DropdownMenu.Separator />
    <DropdownMenu.Item>Logout</DropdownMenu.Item>
  </DropdownMenu.Content>
</DropdownMenu.Root>
