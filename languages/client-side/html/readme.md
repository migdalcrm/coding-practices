# Credit

The following style guide is taken from [here](https://gist.github.com/ryansechrest/8693303), with some modifications.

# HTML Style Guide

All rules and guidelines in this document apply to HTML files.

> The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).

**Icon Legend**:

`·` Space, `⇥` Tab, `↵` Enter/Return

<!-- ---------------------------------------------------------------------- -->

## Table of Contents

1. [**Files**](#1-files)
	[Filename](#filename)
2. [**Comments**](#3-comments)
	1. [Single-line Comments](#1-single-line-comments)
	2. [Multi-line Comments](#2-multi-line-comments)
3. [**Formatting**](#4-formatting)
	1. [Line Indentation](#1-line-indentation)
	2. [Direct Child Elements](#2-direct-child-elements)
	3. [Block, List and Table Elements](#3-block-list-and-table-elements)
	4. [Trailing Whitespace](#4-trailing-whitespace)
	5. [Elements and Attributes](#5-elements-and-attributes)
4. [**Elements and Attributes**](#5-elements-and-attributes)
	1. [Optional Open/Close Tags](#1-optional-openclose-tags)
	2. [Attribute Values](#2-attribute-values)
	3. [Attribute Booleans](#3-attribute-booleans)
	4. [Type Attribute](#4-type-and-language-attribute)
5. [**Best Practices**](#6-best-practices)
	1. [Structures, Styles and Scripts](#1-structures-styles-and-scripts)
	2. [Valid HTML](#2-valid-html)
	3. [Semantic HTML](#3-semantic-html)
	4. [Form Field Names](#5-form-field-names)

<!-- ---------------------------------------------------------------------- -->

## 1. Files

This section describes the format and naming convention of HTML files.

#### Filename

1. **Letters** MUST be all lowercase
	* e.g. `sidebar.html`, `sidebar.php`
2. **Words** MUST be separated with a hyphen
	* e.g. `social-media-widget.html`, `social-media-widget.php`

&#9650; [Table of Contents](#table-of-contents)

<!-- ---------------------------------------------------------------------- -->

## 2. Comments

This section describes how comments should be formatted and used.

1. [**Single-line comments**](#1-single-line-comments) MUST be on one line and text inside MUST be surrounded by spaces
	* e.g. `<!-- This is a comment -->`
2. [**Multi-line comments**](#2-multi-line-comments) MUST start and end on their own line and text MUST NOT be indented
	* i.e. `<!--` `↵` `Line number one` `↵` `Line number two` `↵` `-->`
3. [**Closing tag comments**](#3-closing-tag-comments) SHOULD include the class or ID symbol and name
	* e.g. `</div><!-- #main-wrapper -->`
4. [**Sensitive information**](#4-sensitive-information) MUST NOT be placed in a comment
	* e.g. `<!-- Sends email to user@domain.com -->`

&#9650; [Table of Contents](#table-of-contents)

<!-- ------------------------------ -->

### 1. Single-line Comments

Single-line comments MUST be on one line and text inside MUST be surrounded by spaces.

#### &#10006; Incorrect

```html
<!--
This is a comment
-->
```

&#8627; Incorrect because `<!--`, `This is a comment` and `-->` should be one line.

```html
<!--This is a comment-->
```

&#8627; Incorrect because there is no space before or after `This is a comment`.

#### &#10004; Correct

```html
<!-- This is a comment -->
```

&#9650; [Comments](#3-comments)

<!-- ------------------------------ -->

### 2. Multi-line Comments

Multi-line comments MUST start and end on their own line and text MUST NOT be indented.

#### &#10006; Incorrect

```html
<!-- This is a comment
that spans multiple lines
-->
```

&#8627; Incorrect because `<!--` and `This is a comment` are on one line.

```html
<!--
	This is a comment
	that spans multiple lines
-->
```

&#8627; Incorrect because `This is a comment` and `that spans multiple lines` are indented.

#### &#10004; Correct

```html
<!--
This is a comment
that spans multiple lines
-->
```

&#9650; [Comments](#3-comments)

<!-- ---------------------------------------------------------------------- -->

## 3. Formatting

This section outline various, general formatting rules related to whitespace and text.

1. [**Line indentation**](#1-line-indentation) MUST be accomplished using tabs
	* i.e. `<ul>` `↵` `⇥` `<li>`
2. [**Direct child elements**](#2-direct-child-elements) within `html`, `body`, `style` or `script` element MUST NOT be indented
	* i.e. `<body>` `↵` `<h1></h1>` `↵` `</body>`, `<head>` `↵` `⇥` `...` `</head>`
3. [**Block, list and table elements**](#3-block-list-and-table-elements) MUST start on a new line and their children MUST be indented
	* i.e. `<div>` `↵` `⇥` `<h1>`, `<table>` `↵` `⇥` `<th>`
4. [**Trailing whitespace**](#4-trailing-whitespace) MUST NOT be present
	* i.e. no `<p></p>` `·` `·` `↵`
5. [**Elements and attributes**](#5-elements-and-attributes) MUST be all lowercase
	* e.g. `<a href="" title="">`, `<link rel="stylesheet" href="">`

&#9650; [Table of Contents](#table-of-contents)

<!-- ------------------------------ -->

### 1. Line Indentation

Line indentation MUST be accomplished using tabs.

#### &#10006; Incorrect

```html
<ul>
  <li>Item number one</li>
  <li>Item number two</li>
</ul>
```

&#8627; Incorrect because `<li>` is indented with spaces instead of tabs.

#### &#10004; Correct

```html
<ul>
	<li>Item number one</li>
	<li>Item number two</li>
</ul>
```

&#9650; [Formatting](#4-formatting)

<!-- ------------------------------ -->

### 2. Direct Child Elements

Direct child elements within `html`, `body`, `style` or `script` element MUST NOT be indented.

#### &#10006; Incorrect

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Welcome</title>
		<meta charset="utf-8">
		<style>
			#main-wrapper {
				width: 960px;
			}
		</style>
		<script>
			function show_alert() {
				
			}
		</script>
	</head>
	<body>
		<div id="main-wrapper">
			<h1>Welcome</h1>
			<p>This is a skeleton document.</p>
		</div>
	</body>
</html>
```

&#8627; Incorrect because `<head>`, `<body>` and `<div>` are indented.<br />
&#8627; Incorrect because contents within `<style>` and `<script>` are indented.

#### &#10004; Correct

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<title>Welcome</title>
	<meta charset="utf-8">
	<style>
	#main-wrapper {
		width: 960px;
	}
	</style>
	<script>
	function show_alert() {
		
	}
	</script>
</head>
<body>
<div id="main-wrapper">
	<h1>Welcome</h1>
	<p>This is a skeleton document.</p>
</div>
</body>
</html>
```

&#9650; [Formatting](#4-formatting)

<!-- ------------------------------ -->

### 3. Block, List and Table Elements

Block, list and table elements MUST start on a new line and their children MUST be indented.

#### &#10006; Incorrect

```html
<div><p>This is a paragraph.</p></div>

<ul><li>Item one</li><li>Item two</li></ul>

<table><tr><th>Header</th></tr><tr><td>Content</td></tr></table>
```

&#8627; Incorrect because `<div>`, `<ul>`, `<table>` and`<tr>` are not on their own line.<br />
&#8627; Incorrect because `<p>`, `<li>`, `<tr>` and `<td>`are not indented.

#### &#10004; Correct

```html
<div>
	<p>This is a paragraph.</p>
</div>

<ul>
	<li>Item one</li>
	<li>Item two</li>
</ul>

<table>
	<tr>
		<th>Header</th>
	</tr>
	<tr>
		<td>Content</td>
	</tr>
</table>
```

&#9650; [Formatting](#4-formatting)

<!-- ------------------------------ -->

### 4. Trailing Whitespace

Trailing whitespace MUST NOT be present.

#### &#10006; Incorrect

```html
<p>This is a paragraph.</p>   
```

&#8627; Incorrect because there are spaces after `</p>`.

#### &#10004; Correct

```html
<p>This is a paragraph.</p>
```

&#9650; [Formatting](#4-formatting)

<!-- ------------------------------ -->

### 5. Elements and Attributes

Elements and attributes MUST be all lowercase.

#### &#10006; Incorrect

```html
<div ID="mainWrapper" class="DESKTOP">
	<P>This is a paragraph</P>
</div>
```

&#8627; Incorrect because `ID`, `mainWrapper`, `DESKTOP` and `<P>` are not lowercase.

#### &#10004; Correct

```html
<div id="main-wrapper" class="desktop">
	<p>This is a paragraph</p>
</div>
```

&#9650; [Formatting](#4-formatting)

<!-- ---------------------------------------------------------------------- -->

## 4. Elements and Attributes

This section addresses how to utilize elements and attributes.

1. [**Optional open/close tags**](#1-optional-openclose-tags) MUST be included
	* e.g. `<ul><li></li></ul>`
2. [**Attribute values**](#2-attribute-values) MUST be wrapped in double quotation marks
	* e.g. `<a href="" title="">Link</a>`
3. [**Attribute booleans**](#3-attribute-booleans) SHOULD NOT include a value
	* e.g. `<input type="text" name="" autofocus>`
4. [**Type attribute**](#4-type-and-language-attribute) MUST bbe included on `link` and `script` tags
	* e.g. `<script src=""></script>`

&#9650; [Table of Contents](#table-of-contents)

<!-- ------------------------------ -->

### 1. Optional Open/Close Tags

Optional open/close tags MUST be included.

#### &#10006; Incorrect

```html
<!DOCTYPE html>
<html lang="en">
<div id="main-wrapper">
	<h1>Welcome</h1>
	<p>This is a skeleton document.
</div>
</html>
```

&#8627; Incorrect because `<head></head>`, `<body></body>` and `</p>` are missing.

#### &#10004; Correct

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<title>Welcome</title>
</head>
<body>
<div id="main-wrapper">
	<h1>Welcome</h1>
	<p>This is a skeleton document.</p>
</div>
</body>
</html>
```

&#9650; [Elements and Attributes](#5-elements-and-attributes)

<!-- ------------------------------ -->

### 2. Attribute Values

Attribute values MUST be wrapped in double quotation marks.

#### &#10006; Incorrect

```html
<form action=processor.php class='application'>
	...
</form>
```

&#8627; Incorrect because `processor.php` and `application` are not wrapped in double quotes.

#### &#10004; Correct

```html
<form action="processor.php" class="application">
	...
</form>
```

&#9650; [Elements and Attributes](#5-elements-and-attributes)

<!-- ------------------------------ -->

### 3. Attribute Booleans

Attribute booleans SHOULD NOT include a value.

#### ~ Acceptable

```html
<input type="text" name="first_name" autofocus="autofocus">
```

&#8627; Acceptable, but `autofocus` value is not required for `autofocus` attribute.

#### &#10004; Correct

```html
<input type="text" name="first_name" autofocus>
```

&#9650; [Elements and Attributes](#5-elements-and-attributes)

<!-- ------------------------------ -->

### 4. Type Attribute

Type attribute MUST be included on `script` and `link` tags.

#### &#10006; Incorrect

```html
<script src="script.js"></script>
```
```html
<link rel="stylesheet" href="style.css" />
```
&#8627; Incorrect because `type` attribute is not included.

#### &#10004; Correct

```html
<script type="text/javascript src="script.js"></script>
```
```html
<link type="text/css" rel="stylesheet" href="style.css" />
```

&#9650; [Elements and Attributes](#5-elements-and-attributes)

<!-- ---------------------------------------------------------------------- -->

## 5. Best Practices

1. [**Structures, styles and scripts**](#1-structures-styles-and-scripts) MUST be separated from each other
	* e.g. `<a class="button" data-track="pageview">Read More</a>`
2. [**Valid HTML**](#2-valid-html) MUST be written
	* i.e. yes `<ul><li></li></ul>`, no `<ul><p></p></ul>`
3. [**Semantic HTML**](#3-semantic-html) MUST be written
	* i.e. yes `<a href="">View Options</a>`, no `<div class="click">View Options</div>`
4. [**Form field names**](#5-form-field-names) MUST use underscores to separate words
	* e.g. `<input type="text" name="first_name">`

&#9650; [Table of Contents](#table-of-contents)

<!-- ------------------------------ -->

### 1. Structures, Styles and Scripts

Structures, styles and scripts MUST be separated from each other.

#### &#10006; Incorrect

```html
<div class="internships-module">
	...
</div>
```

&#8627; Incorrect because structure, style and functionality are not decoupled.

#### &#10004; Correct

```html
<div class="module internships">
	...
</div>
```

&#9650; [Best Practices](#6-best-practices)

<!-- ------------------------------ -->

### 2. Valid HTML

Valid HTML MUST be written.

#### &#10006; Incorrect

```html
<ul>
	<li>Item one</li>
	<li>Item two</li>
	<ul>
		<li>Sub-item one</li>
		<li>Sub-item two</li>
	</ul>
</ul>
```

&#8627; Incorrect because `<ul>` cannot be a child of a `<ul>`.

#### &#10004; Correct

```html
<ul>
	<li>Item one</li>
	<li>Item two</li>
	<li>
		<ul>
			<li>Sub-item one</li>
			<li>Sub-item two</li>
		</ul>
	</li>
</ul>
```

&#9650; [Best Practices](#6-best-practices)

<!-- ------------------------------ -->

### 3. Semantic HTML

Semantic HTML MUST be written.

#### &#10006; Incorrect

```html
<div class="button">Click Here</div>
```

&#8627; Incorrect because `<a>` is the elementing for clicking, not `<div>`.

```html
<p><strong>Lorem ipsum:</strong> Dolor sit amet, consectetur
adipiscing elit. Sed tincidunt urna id dui aliquet facilisis. Maecenas nulla diam,
scelerisque et nisl congue, ornare fermentum turpis. Pellentesque eu lorem nulla.
Sed interdum sagittis eros non vulputate. Donec sed interdum ante. Phasellus non
molestie nulla.</p>
```

&#8627; Incorrect because `Lorem ipsum` is to be bold, not strongly spoken by a screen reader.

```html
<div class="textarea">Write your text here.</div>
```

&#8627; Incorrect because `<div>` is not a natural element for user input.

#### &#10004; Correct

```html
<a href="#" class="button">Click Here</a>

<p><b>Lorem ipsum:</b> Dolor sit amet, consectetur adipiscing
elit. Sed tincidunt urna id dui aliquet facilisis. Maecenas nulla diam, scelerisque
et nisl congue, ornare fermentum turpis. Pellentesque eu lorem nulla. Sed interdum
sagittis eros non vulputate. Donec sed interdum ante. Phasellus non molestie
nulla.</p>

<textarea name="comment">Write your text here.</textarea> 
```

&#9650; [Best Practices](#6-best-practices)

<!-- ------------------------------ -->

### 4. Form Field Names

Form field names MUST use underscores to separate words.

#### &#10006; Incorrect

```html
<input type="text" name="emailaddress">
<input type="text" name="email-address">
```

&#8627; Incorrect because `emailaddress` and `email-address` are not using underscores between words.

#### &#10004; Correct

```html
<input type="text" name="email_address">
```

&#9650; [Best Practices](#6-best-practices)

---

&#9650; [Table of Contents](#table-of-contents)

Inspired in part by style guides from: [CKAN](http://docs.ckan.org/en/latest/html-coding-standards.html), [Google](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml), [jQuery](http://contribute.jquery.org/style-guide/html/), and [WordPress](http://make.wordpress.org/core/handbook/coding-standards/html/).
