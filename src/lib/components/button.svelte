<script lang="ts">
	import type { Snippet } from 'svelte';
	import type { HTMLButtonAttributes } from 'svelte/elements';

	type Props = {
		children?: Snippet;
	} & HTMLButtonAttributes;

	const { children, ...prop }: Props = $props();
</script>

<button
	{...prop}
	class={[
		'text-sm font-bold',
		'text-center',
		'bg-neutral-grey-300 text-white',
		'rounded-lg',
		'px-4 py-3',
    "transition duration-200 ease-in-out",
		'hover:from-primary hover:bg-gradient-to-r hover:to-[#F59548]',
		'hover:shadow-primary/50 hover:shadow-lg',
    'active:scale-105'
	]}>{@render children?.()}</button
>
