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
		max-width: 100%;
		min-height: 100dvh;
	}
</style>
