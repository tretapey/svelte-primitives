<!-- AccessiblePopover.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	export let popoverContent: string | HTMLElement = 'Popover';
	export let popoverLabel: string | null = null;
	export let arrow = true;
	export let position: 'top' | 'bottom' | 'left' | 'right' = 'top';
	export let backgroundColor = '#fff';
	export let borderColor = '#ccc';
	export let arrowColor = '#fff';

	let popoverId = `popover-${uuidv4()}`;
	let popoverTriggerId = `popover-trigger-${uuidv4()}`;
	let showPopover = false;
</script>

<button
	id={popoverTriggerId}
	aria-controls={popoverId}
	aria-haspopup="true"
	aria-expanded={showPopover}
	on:click={() => (showPopover = !showPopover)}
	{...$$restProps}
>
	HOLA
	<slot />
</button>
{#if showPopover}
	<div
		class="accessible-popover"
		id={popoverId}
		role="dialog"
		aria-modal="true"
		aria-labelledby={popoverLabel || popoverTriggerId}
		style="--popover-bg: {backgroundColor}; --popover-border-color: {borderColor};"
	>
		{#if arrow}
			<div class="accessible-popover-arrow {position}" style="--arrow-color: {arrowColor};" />
		{/if}
		{@html popoverContent}
	</div>
{/if}

<style>
	.accessible-popover {
		background-color: var(--popover-bg);
		border: 1px solid var(--popover-border-color);
		border-radius: 4px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
		padding: 1rem;
		z-index: 100;
		width: max-content;
		position: absolute;
	}

	.accessible-popover-arrow {
		position: absolute;
		width: 0;
		height: 0;
		border-style: solid;
	}

	.accessible-popover-arrow.top {
		border-width: 0 5px 10px 5px;
		border-color: transparent transparent var(--arrow-color) transparent;
		bottom: 100%;
		left: 50%;
		transform: translateX(-50%);
	}

	.accessible-popover-arrow.bottom {
		border-width: 10px 5px 0 5px;
		border-color: var(--arrow-color) transparent transparent transparent;
		top: 100%;
		left: 50%;
		transform: translateX(-50%);
	}
	.accessible-popover-arrow.left {
		border-width: 5px 0 5px 10px;
		border-color: transparent transparent transparent var(--arrow-color);
		right: 100%;
		top: 50%;
		transform: translateY(-50%);
	}

	.accessible-popover-arrow.right {
		border-width: 5px 10px 5px 0;
		border-color: transparent var(--arrow-color) transparent transparent;
		left: 100%;
		top: 50%;
		transform: translateY(-50%);
	}
</style>
