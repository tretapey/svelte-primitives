# Svelte primitives

A library with fully accessible svelte components acting as primitives.

All this components are designed with accessibility in mind. Here are some of the ways in which they are accessible:

- **Semantic HTML elements**: Each component uses semantic HTML elements, which helps screen readers and other assistive technology better understand the content and context of the component.
- **ARIA attributes**: In addition to using semantic HTML elements, each component also includes ARIA attributes as needed to provide additional information to assistive technology.
- **Keyboard accessibility**: Each component is fully keyboard accessible, meaning that users can navigate and interact with the component using only the keyboard. This is important for users who may not be able to use a mouse or other pointing device.
- **Focus management**: Each component manages focus appropriately, so that users can easily see where they are on the page and navigate to other parts of the page as needed.
- **Customizability**: Each component includes a range of props that can be used to customize the appearance and behavior of the component to suit the needs of individual users and applications.

By incorporating these and other accessibility best practices, we can help ensure that our components are usable and effective for as many users as possible, regardless of their abilities or assistive technology needs.

## Docs

### Installation

`$ npm i svelte-primitives`

### Usage

In your svelte files you can import any of this components:

`import { Button } from 'svelte-primitives'`

## Components

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

### Checkbox Component

A fully accessible checkbox component for Svelte applications.

#### Props

- `id` (string): Unique identifier for the checkbox.
- `label` (string): Text label for the checkbox.
- `checked` (boolean, default: false): Determines if the checkbox is checked.
- `required` (boolean, default: false): Determines if the checkbox is required.
- `disabled` (boolean, default: false): Determines if the checkbox is disabled.
- `ariaDescribedBy` (string | null, default: null): Optional ARIA description.

#### Events

- `change`: Emitted when the checkbox value changes. Payload: Event.

#### Usage

```html
<Checkbox
  id="my-checkbox"
  label="Check me"
  checked={false}
  on:change={() => console.log('Checkbox changed!')}
  class="custom-class"
  style="background-color: blue;"
/>
```


### Image Component

An accessible image component for Svelte applications.

#### Props

- `src` (string): The URL for the image.
- `alt` (string, default: ''): The alternative text for the image.

#### Usage

```html
<Image
  src="https://example.com/image.jpg"
  alt="Example Image"
  class="custom-class"
  style="background-color: green;"
/>
```

### Textarea Component

An accessible textarea component for Svelte applications.

#### Props

- `id` (string): Unique identifier for the textarea field.
- `label` (string): Text label for the textarea field.
- `value` (string, default: ''): Current textarea field value.
- `placeholder` (string, default: ''): Placeholder text.
- `required` (boolean, default: false): Determines if the textarea is required.
- `disabled` (boolean, default: false): Determines if the textarea is disabled.
- `ariaDescribedBy` (string | null, default: null): Optional ARIA description.

#### Events

- `input`: Fired whenever the textarea value changes.

#### Usage

```html
<Textarea
  id="my-textarea"
  label="My Textarea"
  value="Hello, World!"
  placeholder="Type something here..."
  required
  aria-describedby="textarea-instructions"
  class="custom-class"
  style="background-color: lightblue;"
  on:input={handleTextareaInput}
/>
```

### Select Component

An accessible select or dropdown component for Svelte applications.

#### Props

- `id` (string): Unique identifier for the select field.
- `label` (string): Text label for the select field.
- `options` (array): Array of objects representing the options for the select field. Each object should have a `label` and `value` property.
- `value` (string or null, default: null): Currently selected value.
- `required` (boolean, default: false): Determines if the select field is required.
- `disabled` (boolean, default: false): Determines if the select field is disabled.
- `ariaDescribedBy` (string | null, default: null): Optional ARIA description.

#### Events

- `input`: Fired whenever the select value changes.

#### Usage

```html
<Select
  id="my-select"
  label="My Select"
  value="option1"
  {options}
  required
  aria-describedby="select-instructions"
  class="custom-class"
  style="background-color: lightblue;"
  on:input={handleSelectInput}
/>
```
