<script>
	import { PButton, PInput } from '$lib';
</script>

<h1>Primitives</h1>

<h2>Button Component</h2>
<p>A fully accessible button component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>label</code> (string, default: 'Submit'): Text displayed on the button.</li>
	<li><code>type</code> ('button' | 'submit' | 'reset', default: 'button'): Button type.</li>
	<li><code>disabled</code> (boolean, default: false): Determines if the button is disabled.</li>
	<li><code>ariaLabel</code> (string | null, default: null): Optional ARIA label.</li>
</ul>

<h3>Events</h3>
<ul>
	<li><code>click</code>: Emitted when the button is clicked. Payload: MouseEvent.</li>
</ul>

<h3>Example:</h3>
<PButton />

<hr />

<h3>Input</h3>

<h2>Input Component</h2>
<p>A fully accessible input component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>id</code> (string): Unique identifier for the input field.</li>
	<li><code>label</code> (string): Text label for the input field.</li>
	<li><code>type</code> (string, default: 'text'): Input field type.</li>
	<li><code>value</code> (string, default: ''): Current input field value.</li>
	<li><code>required</code> (boolean, default: false): Determines if the input is required.</li>
	<li><code>disabled</code> (boolean, default: false): Determines if the input is disabled.</li>
	<li><code>ariaDescribedBy</code> (string | null, default: null): Optional ARIA description.</li>
</ul>

<h3>Events</h3>
<ul>
	<li><code>input</code>: Emitted when the input value changes. Payload: Event.</li>
</ul>

<h3>Example:</h3>
<PInput label="hello" />
