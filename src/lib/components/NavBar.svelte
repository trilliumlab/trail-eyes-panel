<script lang="ts">
	import { page } from '$app/stores';
	import { cn } from '$lib/utils.js';
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
</script>

<header
	class="border-border/40 bg-background/95 supports-[backdrop-filter]:bg-background/60 sticky top-0 z-50 w-full border-b backdrop-blur"
>
	<div class="container flex h-14 max-w-screen-2xl items-center">
		<div class="mr-4 hidden md:flex">
			<a href="/" class="mr-6 flex items-center space-x-2">
				<img src="/favicon.png" alt="TrailEyes Logo" class="h-6 w-6" />
				<span class="hidden font-bold sm:inline-block">TrailEyes Panel</span>
			</a>
			<nav class="flex items-center gap-6 text-sm">
				<a
					href="/docs"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname === '/docs' ? 'text-foreground' : 'text-foreground/60'
					)}
				>
					Docs
				</a>
				<a
					href="/docs/components"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname.startsWith('/docs/components')
							? 'text-foreground'
							: 'text-foreground/60'
					)}
				>
					Components
				</a>
				<a
					href="/themes"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname.startsWith('/themes') ? 'text-foreground' : 'text-foreground/60'
					)}
				>
					Themes
				</a>
				<a
					href="/examples"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname.startsWith('/examples') ? 'text-foreground' : 'text-foreground/60'
					)}
				>
					Examples
				</a>

				<a
					href="/blocks"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname.startsWith('/blocks') ? 'text-foreground' : 'text-foreground/60'
					)}
				>
					Blocks
				</a>
				<a
					href="/colors"
					class={cn(
						'hover:text-foreground/80 transition-colors',
						$page.url.pathname.startsWith('/colors') ? 'text-foreground' : 'text-foreground/60'
					)}
				>
					Colors
				</a>
			</nav>
		</div>
		<div class="flex flex-1 items-center justify-between space-x-2 md:justify-end">
			<nav class="flex items-center">
				<ThemeToggle />
			</nav>
		</div>
	</div>
</header>
