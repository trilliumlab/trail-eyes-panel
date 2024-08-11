<script>
	import Package2 from 'lucide-svelte/icons/package-2';
	import UserMenu from '$lib/components/UserMenu.svelte';
	import { Button } from '$lib/components/ui/button/index';
	import Menu from 'lucide-svelte/icons/menu';
	import * as Sheet from '$lib/components/ui/sheet/index';
</script>

<header class="bg-background sticky top-0 flex h-16 items-center gap-4 border-b px-4 md:px-6">
	<nav
		class="hidden flex-col gap-6 text-lg font-medium md:flex md:flex-row md:items-center md:gap-5 md:text-sm lg:gap-6"
	>
		<a href="##" class="flex items-center gap-2 text-lg font-semibold md:text-base">
			<img src="/favicon.png" alt="TrailEyes Panel" class="h-8 w-8" />
			<span class="sr-only">TrailEyes Panel</span>
		</a>
		<a href="##" class="text-foreground hover:text-foreground transition-colors"> Dashboard </a>
		<a href="##" class="text-muted-foreground hover:text-foreground transition-colors"> Orders </a>
		<a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
			Products
		</a>
		<a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
			Customers
		</a>
		<a href="##" class="text-muted-foreground hover:text-foreground transition-colors">
			Analytics
		</a>
	</nav>
	<Sheet.Root>
		<Sheet.Trigger asChild let:builder>
			<Button variant="outline" size="icon" class="shrink-0 md:hidden" builders={[builder]}>
				<Menu class="h-5 w-5" />
				<span class="sr-only">Toggle navigation menu</span>
			</Button>
		</Sheet.Trigger>
		<Sheet.Content side="left">
			<nav class="grid gap-6 text-lg font-medium">
				<a href="##" class="flex items-center gap-2 text-lg font-semibold">
					<Package2 class="h-6 w-6" />
					<span class="sr-only">Acme Inc</span>
				</a>
				<a href="##" class="hover:text-foreground"> Dashboard </a>
				<a href="##" class="text-muted-foreground hover:text-foreground"> Orders </a>
				<a href="##" class="text-muted-foreground hover:text-foreground"> Products </a>
				<a href="##" class="text-muted-foreground hover:text-foreground"> Customers </a>
				<a href="##" class="text-muted-foreground hover:text-foreground"> Analytics </a>
			</nav>
		</Sheet.Content>
	</Sheet.Root>
	<div class="flex items-end gap-4 md:ml-auto md:gap-2 lg:gap-4">
		<UserMenu />
	</div>
</header>
