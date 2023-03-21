<!-- AccessibleDropdown.svelte -->
<script lang="ts">
	import { v4 as uuidv4 } from 'uuid';

	type Option = {
		value?: string;
		label: string;
		children?: Array<{ value: string; label: string }>;
	};

	export let label: string | null = null;
	export let options: Array<Option> = [];
	export let selectedValue = '';

	let dropdownId = `dropdown-${uuidv4()}`;

	function renderOption(option: Option) {
		if (option.children && option.children.length > 0) {
			return `
				<optgroup label="{option.label}">
					{#each option.children as child (child.value)}
					<option value="{child.value}">{child.label}</option>
					{/each}
				</optgroup>
			`;
		} else {
			return ` <option value="{option.value}">{option.label}</option> `;
		}
	}
</script>

{#if label}
	<label for={dropdownId} class="accessible-dropdown-label">{label}</label>
{/if}
<select id={dropdownId} bind:value={selectedValue} {...$$restProps}>
	{#each options as option (option.value)}
		{@html renderOption(option)}
	{/each}
</select>
