<!-- Button.svelte -->
<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let label = 'Submit';
	export let type: 'button' | 'submit' | 'reset' = 'button';
	export let disabled = false;
	export let ariaLabel: string | null = null;

	const dispatch = createEventDispatcher<{ click: MouseEvent }>();

	function handleClick(event: MouseEvent) {
		if (!disabled) {
			dispatch('click', event);
		}
	}
</script>

<button
	on:click={handleClick}
	{type}
	{disabled}
	aria-label={ariaLabel || label}
	aria-disabled={disabled ? 'true' : 'false'}
	style={disabled ? 'cursor: not-allowed;' : 'cursor: pointer;'}
	{...$$restProps}
>
	{label}
</button>
