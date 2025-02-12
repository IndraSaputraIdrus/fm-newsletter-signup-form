<script lang="ts">
	import HeroImageInMobile from '$lib/images/illustration-sign-up-mobile.svg';
	import { appStore } from '$lib/store.svelte';
	import Button from './button.svelte';
	import CheckmarkIcon from './checkmark-icon.svelte';
	import { z } from 'zod';

  const validateForm = (value: string) => {
		error.email = undefined;
		const form = formSchema.safeParse({ email: value });
		if (!form.success) {
			const errors = form.error.flatten().fieldErrors;
			error.email = errors.email?.[0];
		}
		appStore.email = value;
    return form.success
  }

	const formSchema = z.object({
		email: z
			.string()
			.trim()
			.min(1, { message: 'Email is required' })
			.email({ message: 'Valid email required' })
	});

	let error: Record<string, string | undefined> = $state({});

	const handleSubmit = (e: SubmitEvent) => {
		e.preventDefault();
    const target = e.target as HTMLFormElement
    const formData = new FormData(target)
    const success = validateForm(formData.get("email")! as string)

    if(success) {
      appStore.status = "success"
    } else {
      appStore.status = "default"
    }
	};

	const getEmail = () => appStore.email;

	const setEmail = (value: string) => {
    validateForm(value)
	};
</script>

<div class="min-h-full bg-white sm:max-w-md">
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

		<form onsubmit={handleSubmit} class="flex flex-col gap-6">
			<label class="flex flex-col gap-2">
				<div class="flex items-center justify-between text-xs font-bold">
					<span>Email address</span>
					{#if error.email}
						<span class="text-primary">{error.email}</span>
					{/if}
				</div>
				<input
					bind:value={getEmail, setEmail}
          name="email"
					class={[
						'rounded-lg border px-4 py-3',
            error.email ? 'bg-red-200' : 'bg-white',
						error.email ? 'placeholder:text-red-500' : 'placeholder:text-neutral-grey-100',
						error.email ? 'border-red-500' : 'border-neutral-grey-100'
					]}
					type="text"
					placeholder="email@company.com"
				/>
			</label>
			<Button>Subscribe to monthly newsletter</Button>
		</form>
	</div>
</div>
