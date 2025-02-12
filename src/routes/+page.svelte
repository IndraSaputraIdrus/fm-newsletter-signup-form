<script lang="ts">
	import Forms from '$lib/components/forms.svelte';
	import SubcribeMessage from '$lib/components/subcribe-message.svelte';
	import { appStore } from '$lib/store.svelte';
	import { fade, scale } from 'svelte/transition';
</script>

<div class={['h-full w-full', 'bg-neutral-grey-300', 'md:flex md:items-center md:justify-center']}>
	{#if appStore.status === 'default'}
		<div class="h-full md:h-auto" in:fade={{ duration: 400 }}>
			<Forms />
		</div>
	{/if}

	{#if appStore.status === 'success'}
		<div
			class="h-full w-full md:flex md:items-center md:justify-center"
			in:scale={{ duration: 400 }}
		>
			<SubcribeMessage />
		</div>
	{/if}
</div>

<style>
	:global(html, body) {
		width: 100%;
		height: 100dvh;
		background-color: var(--color-neutral-grey-300);
	}
</style>
