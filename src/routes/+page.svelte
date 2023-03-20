<script>
	import { Button, Input, Checkbox, Image, Textarea, Select } from '$lib';
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
<Button />

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
<Input />

<hr />

<h2>Checkbox Component</h2>
<p>A fully accessible checkbox component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>id</code> (string): Unique identifier for the checkbox.</li>
	<li><code>label</code> (string): Text label for the checkbox.</li>
	<li><code>checked</code> (boolean, default: false): Determines if the checkbox is checked.</li>
	<li>
		<code>required</code> (boolean, default: false): Determines if the checkbox is required.
	</li>
	<li>
		<code>disabled</code> (boolean, default: false): Determines if the checkbox is disabled.
	</li>
	<li><code>ariaDescribedBy</code> (string | null, default: null): Optional ARIA description.</li>
</ul>

<h3>Events</h3>
<ul>
	<li><code>change</code>: Emitted when the checkbox value changes. Payload: Event.</li>
</ul>

<h3>Example:</h3>
<Checkbox label="hello" />

<hr />

<h2>Image Component</h2>
<p>An accessible image component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>src</code> (string): The URL for the image.</li>
	<li><code>alt</code> (string, default: ''): The alternative text for the image.</li>
</ul>

<h3>Example:</h3>
<Image src="http://craftsnippets.com/articles_images/placeholder/placeholder.jpg" />

<hr />

<h2>Textarea Component</h2>
<p>An accessible textarea component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>id</code> (string): Unique identifier for the textarea field.</li>
	<li><code>label</code> (string): Text label for the textarea field.</li>
	<li><code>value</code> (string, default: ''): Current textarea field value.</li>
	<li><code>placeholder</code> (string, default: ''): Placeholder text.</li>
	<li><code>required</code> (boolean, default: false): Determines if the textarea is required.</li>
	<li><code>disabled</code> (boolean, default: false): Determines if the textarea is disabled.</li>
	<li><code>ariaDescribedBy</code> (string | null, default: null): Optional ARIA description.</li>
</ul>

<h3>Events</h3>
<ul>
	<li><code>input</code>: Fired whenever the textarea value changes.</li>
</ul>

<h3>Example:</h3>
<Textarea />

<hr />

<h2>Select Component</h2>
<p>An accessible select or dropdown component for Svelte applications.</p>

<h3>Props</h3>
<ul>
	<li><code>id</code> (string): Unique identifier for the select field.</li>
	<li><code>label</code> (string): Text label for the select field.</li>
	<li>
		<code>options</code> (array): Array of objects representing the options for the select field.
		Each object should have a <code>label</code> and <code>value</code> property.
	</li>
	<li><code>value</code> (string or null, default: null): Currently selected value.</li>
	<li>
		<code>required</code> (boolean, default: false): Determines if the select field is required.
	</li>
	<li>
		<code>disabled</code> (boolean, default: false): Determines if the select field is disabled.
	</li>
	<li><code>ariaDescribedBy</code> (string | null, default: null): Optional ARIA description.</li>
</ul>

<h3>Events</h3>
<ul>
	<li><code>input</code>: Fired whenever the select value changes.</li>
</ul>

<h3>Example:</h3>
<Select
	options={[
		{ label: 'Option 1', value: '1' },
		{ label: 'Option 2', value: '2' }
	]}
/>
