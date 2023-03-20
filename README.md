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
