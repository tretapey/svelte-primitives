<!-- Textarea.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';
	import { createEventDispatcher } from 'svelte';

	export let id: string = uuidv4();
	export let label = '';
	export let value = '';
	export let placeholder = '';
	export let required = false;
	export let disabled = false;
	export let ariaDescribedBy: string | null = null;

	const dispatch = createEventDispatcher();

	function handleChange(event: Event) {
		const value = (event.target as HTMLTextAreaElement).value;
		dispatch('input', value);
	}
</script>

<label for={id}>
	<span>{label}</span>
	<textarea
		{id}
		{value}
		{placeholder}
		{required}
		{disabled}
		aria-describedby={ariaDescribedBy}
		on:input={handleChange}
		{...$$restProps}
	/>
</label>

