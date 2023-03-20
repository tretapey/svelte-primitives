<!-- Select.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';
	import { createEventDispatcher } from 'svelte';

	type Option = {
		label: string;
		value: string;
	};

	export let id: string = uuidv4();
	export let label = '';
	export let options: Option[] = [];
	export let value: string | null = null;
	export let required = false;
	export let disabled = false;
	export let ariaDescribedBy: string | null = null;

	const dispatch = createEventDispatcher();

	function handleChange(event: Event) {
		const value = (event.target as HTMLSelectElement).value;
		dispatch('input', value);
	}
</script>

<label for={id}>
	<span>{label}</span>
	<select
		{id}
		value={value || ''}
		{required}
		{disabled}
		aria-describedby={ariaDescribedBy}
		on:change={handleChange}
		{...$$restProps}
	>
		{#if !value}
			<option value="" disabled>-- Select an option --</option>
		{/if}
		{#each options as option}
			<option value={option.value}>{option.label}</option>
		{/each}
	</select>
</label>
