# plating

Simple JS Templating

## Installation

`npm install --save plating`

## Usage

Provide any string with all placeholders defined as `{{placeholder|default value}}`, or simply as `{{placeholder}}`.

If no value for `placeholder` is defined, it will fall back to the `default value`, if provided.  If no value is defined and there is no default value, the placeholder will be displayed as entered.  In this case, `{{placeholder}}` would be visible in the rendered version.

## Example

```
const plating = require('plating');

let template = '{{app}} is a simple template system for {{lang|JS}}';

// Get tokens to find out what can be substituted
let tokens = plating.extract(template);

// Render the template, notice the default value used with `lang`
let rendered = plating.render(template, {
	app: 'plating'
});
```

In the example above, `tokens` contains:

```
[
  {
    raw: '{{app}}',
    key: 'app',
    defaultValue: undefined
  },
  {
    raw: '{{lang|JS}}',
    key: 'lang',
    defaultValue: 'JS'
  }
]

```

And `rendered` is:

```
plating is a simple template system for JS
```

## License

MIT
