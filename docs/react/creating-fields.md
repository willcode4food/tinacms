# Creating Fields in React

This is a guide to creating [Field Plugin](../concepts/field-plugins.md) Components in React.

## Component

The `Component` is React component that accepts three props:

- `field`: The [field definition](../concepts/forms.md#field-definitions) for the current field.
- `input`: The data and callbacks necessary to make an input.
- `meta`: Metadata about the field in the form. (e.g. `dirty`, `valid`)

Checkout the [`react-final-form`](https://github.com/final-form/react-final-form#fieldrenderprops) docs for a more detailed description of the `input` and `meta` props.

## Example

Here is an example of a simple text field plugin. The `Component` renders the label, the input, and the errors for the field.

```javascript
import { CMS } from '@forestryio/cms'

let cms = new CMS()

cms.fields.register({
  name: 'text',
  Component({ input, meta, field }) {
    return (
      <>
        <label htmlFor={field.name}>{field.label | field.name}</label>
        <input type="text" {...input} />
        <div class="field-error">{meta.error}</div>
      </>
    )
  },
})
```