<!-- Input.svelte -->
<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import { v4 as uuidv4 } from 'uuid';

	export let id = uuidv4();
	export let label = '';
	export let type = 'text';
	export let value = '';
	export let placeholder = '';
	export let required = false;
	export let disabled = false;
	export let ariaDescribedBy: string | null = null;

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
