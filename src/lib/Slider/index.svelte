<!-- AccessibleSlider.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	export let min = 0;
	export let max = 100;
	export let step = 1;
	export let value = 50;
	export let label: string | null = null;

	let sliderId = `slider-${uuidv4()}`;
</script>

{#if label}
	<label for={sliderId} class="accessible-slider-label">{label}</label>
{/if}
<input
	type="range"
	id={sliderId}
	{min}
	{max}
	{step}
	{value}
	aria-valuemin={min}
	aria-valuemax={max}
	aria-valuenow={value}
	aria-valuetext={label || 'slider'}
	{...$$restProps}
/>

<style>
	.accessible-slider-label {
		display: block;
		margin-bottom: 0.5rem;
	}
</style>
