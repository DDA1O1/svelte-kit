<script>
    import Button from "$lib/components/ui/button/button.svelte";

    import { useQuery } from 'convex-svelte';
	import { api } from '../convex/_generated/api.js';

	const query = useQuery(api.tasks.get, {});
</script>

<div class="min-h-screen flex items-center justify-center">
    <Button size="lg" class="text-xl px-8 py-4">Click me</Button>
</div>

{#if query.isLoading}
	Loading...
{:else if query.error}
	failed to load: {query.error.toString()}
{:else}
	<ul>
		{#each query.data as task}
			<li>
				{task.isCompleted ? '☑' : '☐'}
				<span>{task.text}</span>
				<span>assigned by {task.assigner}</span>
			</li>
		{/each}
	</ul>
{/if}
