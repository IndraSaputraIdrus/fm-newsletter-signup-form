<script lang="ts">
	import HeroImageInMobile from '$lib/images/illustration-sign-up-mobile.svg';
	import CheckmarkIcon from './checkmark-icon.svelte';
</script>

<div class="bg-white sm:max-w-md">
	<div>
		<img src={HeroImageInMobile} alt="hero" class="block w-full object-cover" />
	</div>
	<div class="text-neutral-grey-200 flex flex-col gap-6 px-6 py-11">
		<div class="space-y-5">
			<h1 class="text-[40px] leading-none font-bold">Stay updated!</h1>
			<p class="text-base text-balance">
				Join 60,000+ product managers receiving monthly updated on:
			</p>
		</div>

		<ul class="space-y-4">
			<li class="flex items-start gap-4">
				<CheckmarkIcon />
				<p class="-mt-1">Product discovery and building what matters</p>
			</li>
			<li class="flex items-start gap-4">
				<CheckmarkIcon />
				<p class="-mt-1">Measuring to ensure updates are a success</p>
			</li>
			<li class="flex items-start gap-4">
				<CheckmarkIcon />
				<p class="-mt-1">And much more!</p>
			</li>
		</ul>

		<form class="flex flex-col gap-6">
			<label class="flex flex-col gap-2">
				<span class="text-xs font-bold">Email address</span>
				<input
					class="placeholder:text-neutral-grey-100 border-neutral-grey-100 rounded-lg border px-4 py-3"
					type="text"
					placeholder="email@company.com"
				/>
			</label>
			<button class="font-bold text-sm bg-neutral-grey-300 rounded-lg px-4 py-3 text-center text-white"
				>Subscribe to monthly newsletter</button
			>
		</form>
	</div>
</div>
