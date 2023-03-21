<!-- AccessibleInput.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	export let type = 'text';
	export let label: string | null = null;
	export let placeholder: string | null = null;
	export let required = false;
	export let value: string | null = null;

	let inputId = `input-${uuidv4()}`;
	let describedById = label ? `describedBy-${uuidv4()}` : null;
</script>

{#if label}
	<label for={inputId} class="accessible-input-label">{label}</label>
{/if}
<input
	{type}
	id={inputId}
	{placeholder}
	{required}
	{value}
	aria-required={required}
	aria-label={label}
	aria-describedby={describedById}
	{...$$restProps}
/>
{#if describedById}
	<span id={describedById} class="sr-only">{label}</span>
{/if}
