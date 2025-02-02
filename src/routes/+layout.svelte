<script lang="ts">
	//import Kalam from '$lib/fonts/kalam-latin-400-normal.woff2?url';

	import '../app.css';
	import type { Snippet } from 'svelte';

	type Props = {
		children?: Snippet<[]>;
	};

	const { children }: Props = $props();
</script>

{@render children?.()}
