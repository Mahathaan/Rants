<script>
	import { Button } from '$lib/components/ui/button';
	import * as Tooltip from '$lib/components/ui/tooltip';
	import { Github } from 'lucide-svelte';
</script>

<nav class="mx-auto max-w-6xl px-4">
	<div class="flex h-16 flex-row-reverse items-center justify-items-end md:justify-center">
		<div class="hidden items-center space-x-4 md:flex">
			<a
				href="https://github.com/Mahathaan/Rants.git"
				class="border-b-2 border-transparent px-3 py-2 text-lg font-medium text-black underline transition duration-150 ease-in-out hover:text-red-500"
				>Github</a
			>
			<Tooltip.Root openDelay={0} closeDelay={0}>
				<Tooltip.Trigger>
					<a
						href="/"
						class="border-b-2 border-transparent px-3 py-2 text-lg font-medium text-black underline transition duration-150 ease-in-out hover:text-red-500"
						>Docs</a
					>
				</Tooltip.Trigger>
				<Tooltip.Content class="rounded-md border border-black bg-white p-2 text-black shadow-md">
					<p>Chill, You don't need any of this!</p>
				</Tooltip.Content>
			</Tooltip.Root>
		</div>
		<div class="md:hidden">
			<Button
				variant="outline"
				href="https://github.com/Mahathaan/Rants.git"
				class="flex items-center space-x-2"
			>
				<Github class="h-5 w-5" />
				<span>Github</span>
			</Button>
		</div>
	</div>
</nav>
