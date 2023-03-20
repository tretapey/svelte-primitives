<!-- Image.svelte -->
<script lang="ts">
	export let src: string;
	export let alt = '';

	let imgSrc = '';

	$: imgSrc = src || '';

	function handleLoad(event: Event) {
		const imgElement = event.currentTarget as HTMLElement;
		imgElement.removeAttribute('aria-hidden');
	}

	function handleError(event: Event) {
		const imgElement = event.currentTarget as HTMLElement;
		imgElement.setAttribute('aria-hidden', 'true');
	}
</script>

<img
	src={imgSrc}
	{alt}
	aria-hidden={imgSrc ? 'false' : 'true'}
	on:load={handleLoad}
	on:error={handleError}
	{...$$restProps}
/>
