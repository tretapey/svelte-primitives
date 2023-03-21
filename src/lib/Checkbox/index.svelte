<!-- AccessibleCheckbox.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	export let label: string | null = null;
	export let checked = false;

	let checkboxId = `checkbox-${uuidv4()}`;
</script>

{#if label}
	<label for={checkboxId} class="accessible-checkbox-label">{label}</label>
{/if}
<input
	type="checkbox"
	id={checkboxId}
	bind:checked
	aria-checked={checked}
	aria-label={label || 'checkbox'}
	{...$$restProps}
/>

