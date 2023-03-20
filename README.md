# Svelte primitives

A library with fully accessible svelte components acting as primitives.


## Docs

### Button Component

A fully accessible button component for Svelte applications.

#### Props

- `label` (string, default: 'Submit'): Text displayed on the button.
- `type` ('button' | 'submit' | 'reset', default: 'button'): Button type.
- `disabled` (boolean, default: false): Determines if the button is disabled.
- `ariaLabel` (string | null, default: null): Optional ARIA label.

#### Events

- `click`: Emitted when the button is clicked. Payload: MouseEvent.

#### Usage

```html
<Button
  label="Submit"
  type="submit"
  disabled={false}
  on:click={() => console.log('Button clicked!')}
  class="custom-class"
  style="background-color: red;"
/>
```

### Input Component

An accessible input component for Svelte applications.

#### Props

- `id` (string): Unique identifier for the input field.
- `label` (string): Text label for the input field.
- `type` (string, default: 'text'): Input field type.
- `value` (string, default: ''): Current input field value.
- `placeholder` (string, default: ''): Placeholder text.
- `required` (boolean, default: false): Determines if the input is required.
- `disabled` (boolean, default: false): Determines if the input is disabled.
- `ariaDescribedBy` (string | null, default: null): Optional ARIA description.

#### Events

- `input`: Emitted when the input value changes. Payload: Event.

#### Usage

```html
<Input
  id="username"
  label="Username"
  type="text"
  value=""
  placeholder="Enter your username"
  required={true}
  on:input={() => console.log('Input changed!')}
  class="custom-class"
  style="background-color: yellow;"
/>
```

