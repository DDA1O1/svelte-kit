<script>
    import { cn } from "$lib/utils";
    import Button from "$lib/components/ui/button/button.svelte";

    const something = true;
</script>

<h1 class={cn("text-red-500 text-5xl", something === true && "text-green-300")}>
    Welcome to SvelteKit
</h1>
<p>
    Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the
    documentation
</p>

<Button>Click me</Button>
