<!-- Input.svelte -->
<script lang="ts">
	export let id = 'input';
	export let label = '';
	export let type = 'text';
	export let value = '';
	export let placeholder = '';
	export let required = false;
	export let disabled = false;
	export let ariaDescribedBy: string | null = null;

	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher<{ input: Event }>();

	function handleInput(event: Event) {
		dispatch('input', event);
	}
</script>

{#if label}
	<label for={id}>{label}</label>
{/if}
<input
	{id}
	{type}
	{value}
	{placeholder}
	{required}
	{disabled}
	on:input={handleInput}
	aria-describedby={ariaDescribedBy}
	{...$$restProps}
/>
