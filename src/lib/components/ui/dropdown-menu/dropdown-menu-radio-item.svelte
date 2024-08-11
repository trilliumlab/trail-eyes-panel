<script lang="ts">
  import { DropdownMenu as DropdownMenuPrimitive } from 'bits-ui';
  import Circle from 'lucide-svelte/icons/circle';
  import Check from 'lucide-svelte/icons/check';
  import { cn } from '$lib/utils.js';

  type $$Props = DropdownMenuPrimitive.RadioItemProps & { indicator?: 'circle' | 'checkmark' };
  type $$Events = DropdownMenuPrimitive.RadioItemEvents;

  export let indicator: $$Props['indicator'] = 'circle';

  let className: $$Props['class'] = undefined;
  export let value: $$Props['value'];
  export { className as class };
</script>

<DropdownMenuPrimitive.RadioItem
  class={cn(
    'data-[highlighted]:bg-accent data-[highlighted]:text-accent-foreground relative flex cursor-default select-none items-center rounded-sm py-1.5 pl-8 pr-2 text-sm outline-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50',
    className
  )}
  {value}
  {...$$restProps}
  on:click
  on:keydown
  on:focusin
  on:focusout
  on:pointerdown
  on:pointerleave
  on:pointermove
>
  <span class="absolute left-2 flex h-3.5 w-3.5 items-center justify-center">
    <DropdownMenuPrimitive.RadioIndicator>
      {#if indicator === 'circle'}
        <Circle class="h-2 w-2 fill-current" />
      {:else if indicator === 'checkmark'}
        <Check class="h-4 w-4" />
      {/if}
    </DropdownMenuPrimitive.RadioIndicator>
  </span>
  <slot />
</DropdownMenuPrimitive.RadioItem>
