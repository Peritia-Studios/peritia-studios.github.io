<script lang="ts">
	import '../app.css';
	import { i18n } from '$lib/i18n';
	import { ParaglideJS } from '@inlang/paraglide-sveltekit';
	import NavLinks from './NavLinks.svelte';
	let { children } = $props();
</script>

<ParaglideJS {i18n}>
	<div class="min-h-screen">
		<header
			class="border-surface-500/20 bg-surface-50/90 dark:bg-surface-950/90 sticky top-0 z-50 flex h-[70px] w-full items-center border-b-[1px] backdrop-blur-sm"
		>
			<div
				class="grid w-full grid-cols-[auto_1fr_auto] items-center gap-4 px-4 md:grid-cols-[1fr_auto_1fr] md:px-10"
			>
				<NavLinks />
			</div>
		</header>

		<div class="w-full">
			{@render children?.()}
		</div>
	</div>
</ParaglideJS>
