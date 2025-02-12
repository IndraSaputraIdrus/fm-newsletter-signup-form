<script lang="ts">
	import Forms from '$lib/components/forms.svelte';
	import SubcribeMessage from '$lib/components/subcribe-message.svelte';
	import { appStore } from '$lib/store.svelte';
	import { scale } from 'svelte/transition';
</script>

<div class={['h-full w-full', 'bg-neutral-grey-300']}>
	{#if appStore.status === 'default'}
			<Forms />
	{/if}

	{#if appStore.status === 'success'}
		<div class="h-full w-full" in:scale={{ duration: 400 }} >
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
