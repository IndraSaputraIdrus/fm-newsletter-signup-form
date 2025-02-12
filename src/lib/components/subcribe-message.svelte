<script>
	import { appStore } from '$lib/store.svelte';
	import Button from './button.svelte';
	import CheckmarkIcon from './checkmark-icon.svelte';
</script>

<div class="flex h-full w-full flex-col bg-white p-6 md:h-auto md:max-w-md md:gap-6 md:rounded-2xl md:p-10">
	<div class="flex grow-1 flex-col justify-center">
		<div class="block md:hidden">
			<CheckmarkIcon size={50} />
		</div>
		<div class="hidden md:block">
			<CheckmarkIcon size={60} />
		</div>
		<h1 class="text-neutral-grey-300 mt-6 text-4xl font-bold text-pretty md:text-5xl">
			Thanks for subscribing!
		</h1>
		<p class="text-neutral-grey-300 mt-6">
			A confirmation email has been sent to <span class="font-bold text-balance"
				>{appStore.email}</span
			>. Please open it and click the button inside to confirm your subscription.
		</p>
	</div>

	<Button
		onclick={() => {
			appStore.status = 'default';
			appStore.email = '';
		}}>Dismiss message</Button
	>
</div>
