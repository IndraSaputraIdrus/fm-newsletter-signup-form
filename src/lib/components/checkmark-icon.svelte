<script lang="ts">
	type Props = {
		size?: number;
	};

	const { size = 18 }: Props = $props();
</script>

<div
	style="--container-size: {size}px"
	class="bg-primary inline-flex size-(--container-size) items-center justify-center rounded-full p-1 leading-none"
>
	<svg
		style="--icon-size: {size - 4}px"
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 24 24"
		fill="none"
		stroke="currentColor"
		stroke-linecap="round"
		stroke-linejoin="round"
		class="size-(--icon-size) stroke-3 leading-none text-white"><path d="M20 6 9 17l-5-5" /></svg
	>
</div>
