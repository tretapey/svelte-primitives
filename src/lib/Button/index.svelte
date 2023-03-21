<!-- AccessibleButton.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	export let label: string | null = null;
	export let content: string | HTMLElement = 'Button';

	let buttonId = `button-${uuidv4()}`;
</script>

{#if label}
	<button id={buttonId} aria-label={label} {...$$restProps}>
		<slot>{content}</slot>
	</button>
{:else}
	<button id={buttonId} {...$$restProps}>
		<slot>{content}</slot>
	</button>
{/if}

