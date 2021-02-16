
# Credit

The following style guide is taken from [here](https://github.com/apdev/coding-guidelines), with some modifications.

# CSS Style Guide

- use 1 tab indentation
- all lowercase classnames/IDs (no camelCase, use hyphens instead)

```css
#login {}
.gallery {}
```

- use class names/IDs that are as short as possible but as long as necessary
- do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.

```css
.gallery {}
.gallery-item {}
```

- that said, usually don't use IDs in CSS
- put one space after `:` in property declarations
- put one space before `{` in rule declarations
- each declaration should appear on its own line for more accurate error reporting  
  *In instances where a rule set includes only one declaration, consider removing line breaks for readability and faster editing.*
- end all declarations with a semi-colon
- comma-separated property values should include a space after each comma
- do not include spaces after commas within `rgb()`, `rgba()`, `hsl()`, `hsla()` or `rect()` values  
  *This helps differentiate multiple color values (comma, no space) from multiple property values (comma with space)*
- lowercase all hex values, e.g., `#fff`
- use shorthand hex values where available, e.g., `#fff` instead of `#ffffff`

```css
.gallery-item {
  border: 1px solid #0f0;
  color: #000;
  background: rgba(0,0,0,0.5);
}
```

- related property declarations should be grouped together following the order:
    1. **Positioning**  
    *Positioning comes first because it can remove an element from the normal flow of the document and override box model related styles*
    2. **Box model**  
    *The box model comes next as it dictates a component's dimensions and placement.  
Everything else takes place inside the component or without impacting the previous two sections, and thus they come last.*
    3. **Typographic**
    4. **Visual**

```css
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```

- **"never" use `!important`** (sometimes if you work with external sources you just have to)

- when grouping selectors, keep individual selectors to a single line

```css
.item-1,
.item-2,
.item-3 {
  /* … */
}
```

- place closing braces of declaration blocks on a new line
- put comments on the line above what you want to comment on
