<script lang="ts">
	import { videoTime } from '$lib';
	import * as m from '$lib/paraglide/messages';

	let loaded = $state(false);
	let loading = $state(false);
</script>

<svelte:head>
	<title>Plebis Online</title>
	<meta name="description" content={m.example()} />
</svelte:head>

<div class={loaded && !loading ? '' : 'placeholder animate-pulse rounded-none'}>
	<video
		bind:currentTime={$videoTime}
		class="aspect-21/9 w-full object-cover transition-opacity duration-300
		{loaded ? 'opacity-100' : 'opacity-0'}"
		ontimeupdate={() => (loaded = true)}
		onwaiting={() => (loading = true)}
		oncanplay={() => {
			loading = false;
			loaded = true;
		}}
		playsinline
		disablepictureinpicture
		autoplay
		loop
		muted
	>
		<track kind="captions" />
		<source src="banner.mp4" type="video/mp4" />
		Your browser does not support the video tag.
	</video>
</div>

<div class="content">
	<h2 class="h2"><span class="text-glowing">{m.example()}</span></h2>
	<p>Danke fürs Banner Video, Ole (Huan)!</p>
</div>
