<!-- Checkbox.svelte -->
<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import { v4 as uuidv4 } from 'uuid';

	export let id = uuidv4();
	export let label = '';
	export let checked = false;
	export let required = false;
	export let disabled = false;
	export let ariaDescribedBy: string | null = null;

	const dispatch = createEventDispatcher<{ change: Event }>();

	function handleChange(event: Event) {
		dispatch('change', event);
	}
</script>

<label for={id}>
	<input
		{id}
		type="checkbox"
		{checked}
		{required}
		{disabled}
		aria-describedby={ariaDescribedBy}
		on:change={handleChange}
		{...$$restProps}
	/>
	{label}
</label>
