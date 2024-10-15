<script>
	import { Button } from '$lib/components/ui/button';
	import * as Tooltip from '$lib/components/ui/tooltip';
	import { Github } from 'lucide-svelte';
</script>

<nav class="max-w-6xl mx-auto px-4">
	<div class="flex flex-row-reverse justify-items-end items-center md:justify-center h-16">
		<div class="hidden md:flex items-center space-x-4">
			<a href="https://github.com" class="text-black hover:text-red-500 px-3 py-2 text-lg font-medium border-b-2 border-transparent transition duration-150 ease-in-out underline">Github</a>
			<Tooltip.Root openDelay={0} closeDelay={0}>
				<Tooltip.Trigger>
					<a href="/" class="text-black hover:text-red-500 px-3 py-2 text-lg font-medium border-b-2 border-transparent transition duration-150 ease-in-out underline">Docs</a>
				</Tooltip.Trigger>
				<Tooltip.Content class="bg-white border border-black text-black p-2 rounded-md shadow-md">
					<p>Chill, You don't need any of this!</p>
				</Tooltip.Content>
			</Tooltip.Root>
		</div>
		<div class="md:hidden">
			<Button variant="outline" href="https://github.com" class="flex items-center space-x-2">
				<Github class="h-5 w-5" />
				<span>Github</span>
			</Button>
		</div>
	</div>
</nav>
