<script lang="ts">
	import Forms from '$lib/components/forms.svelte';
</script>

<div class={[
  "h-full w-full",
  "bg-neutral-grey-300",
]}>
	<Forms />
</div>

<style>
	:global(html, body) {
		width: 100%;
		height: 100dvh;
    background-color: var(--color-neutral-grey-300);
	}
</style>
