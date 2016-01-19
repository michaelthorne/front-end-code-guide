_This is a work in progress…_

# HTML & CSS code guide

## Overview

The purpose of this guide is to help you write consistent, maintainable and scalable code. It is a living document which should reviewed on an ongoing basis. Due to the regular changes in technology and standards, it will need updating over time.

Please [open an issue on GitHub](https://github.com/michaelthorne/codeguide/issues/new) if you’d like to contribute.

## Table of Contents

- [1. General](#general)
- [2. Browser Support](#browser-support)
- [3. HTML](#html)
 - [3.1 General](#html-general)
 - [3.2 Terminology](#html-terminology)
 - [3.3 Document Type Definition (DTD)](#html-document-type-definition)
 - [3.4 Language](#html-language)
 - [3.5 Character Encoding](#html-character-encoding)
 - [3.6 Internet Explorer Compatibility Mode](#html-internet-explorer-compatibility-mode)
 - [3.7 Attribute Order](#html-attribute-order)
 - [3.8 Semantics](#html-semantics)
 - [3.9 Using WAI-ARIA in HTML](#html-using-wai-aria)
 - [3.10 Validation](#html-validation)
- [4. CSS](#css)
 - [4.1 General](#css-general)
 - [4.2 Terminology](#css-terminology)
 - [4.3 Commenting](#css-commenting)
 - [4.4 Naming Conventions](#css-naming-conventions)
 - [4.5 Declaration Order](#css-declaration-order)
 - [4.6 Selectors](#css-selectors)
- [5. JavaScript](#javascript)
- [6. References](#references)
- [7. Inspiration & Credits](#inspiration-and-credits)

<a name="general"></a>
## 1. General

Your codebase must appear as if it was written by a single person, even if many people contributed to it. With style guide driven development, it is crucial that the code is easy to maintain. This must be the focus from the onset, as their is always potential for your project to grow.

- There needs to be a clear separation of concerns: structure, presentation and behavior
- Keep your code readable and easy to understand – think about the next person who has to maintain it
- Consider a sensible maximum for line-length e.g. **80 character** wide columns
- Make use of whitespace to _improve_ readability of the code
- Use [EditorConfig](http://editorconfig.org) if your IDE or text editor supports it
- When in doubt, see if there’s an existing style that people are using or refer to other [guidelines](#6-inspiration--credits)

<a name="browser-support"></a>
## 2. Browser Support

Through the practice of [progressive enhancement and graceful degradation](http://alistapart.com/article/understandingprogressiveenhancement) a website _should_ render in any web browser. But yet, the experience for each visitor will differ based on the features supported in the version of the browser in use.

<a name="html"></a>
## 3. HTML

<a name="html-general"></a>
### 3.1 General

This is the basic structure of an HTML document:

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta http-equiv="x-ua-compatible" content="ie=edge">
    <title>HTML & CSS code guide</title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <link rel="apple-touch-icon" href="/apple-touch-icon.png">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header role="banner">
    
    </header>

    <main role="main">
    
    </main>

    <footer role="contentinfo">
    
    </footer>

    <script src="script.js"></script>

    <script>
        (function(b,o,i,l,e,r){b.GoogleAnalyticsObject=l;b[l]||(b[l]=
        function(){(b[l].q=b[l].q||[]).push(arguments)});b[l].l=+new Date;
        e=o.createElement(i);r=o.getElementsByTagName(i)[0];
        e.src='https://www.google-analytics.com/analytics.js';
        r.parentNode.insertBefore(e,r)}(window,document,'script','ga'));
        ga('create','UA-XXXXX-X','auto');ga('send','pageview');
    </script>
</body>
</html>
```

- Always use lowercase for HTML tag names and attribute values
- Only use double quotes (`""`) around attribute values
- Indentation must be 4 spaces (and not tabs)
- Omit the `type` attribute when including style sheets and scripts
- Remove any trailing whitespace from the end of each line
- Use a new line for every [block-level](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) element

<a name="html-terminology"></a>
### 3.2 Terminology

#### HTML Elements

Elements typically consist of a start and end tag, attributes and contents. The contents of an element are determined by it’s content model. Attributes and their values are not considered to be part of the contents of an element.

Example of an element: `<p>This is the content of a paragraph element.</p>`

> A void element is an element whose content model never allows it to have contents under any circumstances. Void elements can have attributes. – [W3C](http://www.w3.org/TR/html-markup/syntax.html#void-element)

Examples of void elements in HTML: `<hr>`, `<img>`, `<input>`, `<link>`, `<meta>`

#### HTML Tags

Tags are used to mark the start and end of HTML elements. Optionally, tags can have attributes.

Example of a start tag: `<p>`

Example of an end tag: `</p>`

#### HTML Attributes

Attributes have a `name` and `value` and are specified in the element’s start tag.

Example of an element’s attributes: `<img src="" alt="">`

<a name="html-document-type-definition"></a>
### 3.3 Document Type Definition (DTD):

Include the HTML5 doctype:

```html
<!doctype html>
```

> Including the doctype in a document ensures that the browser makes a best-effort attempt at following the relevant specifications. – [W3C](http://www.w3.org/TR/html5/syntax.html#the-doctype)

<a name="html-language"></a>
### 3.4 Language

Specify the language [code](http://www.loc.gov/standards/iso639-2/php/code_list.php) for your HTML document:

```html
<html lang="en">
```

> Authors are encouraged to specify a lang attribute on the root html element, giving the document's language. This aids speech synthesis tools to determine what pronunciations to use, translation tools to determine what rules to use, and so forth. – [W3C](http://www.w3.org/TR/html5/semantics.html#the-html-element)

<a name="html-character-encoding"></a>
### 3.5 Character Encoding

Define the HTML document’s character set as [utf-8](http://www.utf-8.com):

```html
<meta charset="utf-8">
```

> Unicode is a universal character set, ie. a standard that defines, in one place, all the characters needed for writing the majority of living languages in use on computers. It aims to be, and to a large extent already is, a superset of all other character sets that have been encoded. – [W3C](http://www.w3.org/International/articles/definitions-characters)

<a name="html-internet-explorer-compatibility-mode"></a>
### 3.6 Internet Explorer Compatibility Mode

Ensure that IE uses the latest engine:

```html
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> The idea behind compatibility mode is to allow web sites and applications that are not designed to modern standards to continue to work while upgrades can be made, allowing end users to upgrade to the latest browser version. Designating 'IE=edge' is the best practice because it ensures Internet Explorer uses the latest engine. The most current Internet Explorer version includes the latest security updates as well as feature support. The current version is also the fastest version. – [modern.IE](https://www.modern.ie/en-us/performance/how-to-use-x-ua-compatible)

<a name="html-attribute-order"></a>
### 3.7 Attribute Order

In order to improve the general readability of code, it is recommended to place tag attributes in the following order:

- `class`
- `id`, `name`
- `for`, `href`, `src`, `type`
- `action`, `method`, `href`
- `title`, `alt`
- `width`, `height`
- `aria-*`, `role`
- `data-*`

This is an example of the recommended attribute order for an **image**:

```html
<img src="…" width="…" height="…" title="…" alt="…">
```

This is an example of the recommended attribute order for a **form control**:

```html
<input class="…" name="…" type="…">
```

This is an example of the recommended attribute order for an **anchor**:

```html
<a href="…" title="…" target="…" data-attribute="…">
```

This is an example of the recommended attribute order for a **div**:

```html
<div class="…" id="…" aria-controls="…" role="…">
```

<a name="html-semantics"></a>
### 3.8 Semantics

Use the appropriate element when marking up your content to give it meaning on a web page. Semantic code describes the value of the content on a page, independent of it’s style.

Have a look at the [HTML5 Sectioning Element Flowchart](http://html5doctor.com/resources/#flowchart) if you get stuck.

<a name="html-using-wai-aria"></a>
### 3.9 Using WAI-ARIA in HTML

The main goal of the ARIA specification is to improve the overall accessibility of websites.

> WAI-ARIA, the Accessible Rich Internet Applications Suite, defines a way to make Web content and Web applications more accessible to people with disabilities. It especially helps with dynamic content and advanced user interface controls developed with Ajax, HTML, JavaScript, and related technologies. – [WAI-ARIA Overview](http://www.w3.org/WAI/intro/aria)

As per the W3C draft, [using WAI-ARIA in HTML](http://www.w3.org/TR/aria-in-html), rather use native HTML elements wherever possible as it will have the semantics and required behaviour built-in.

<a name="html-validation"></a>
### 3.10 Validation

Ensure that you use valid HTML wherever possible. Use tools like the [W3C Markup Validation Service](http://validator.w3.org) or the [Nu Markup Checker](http://validator.w3.org/nu). There is also a [grunt-html-validation](https://www.npmjs.org/package/grunt-html-validation) plugin which uses the W3C validator to check your HTML.

<a name="css"></a>
## 4. CSS

<a name="css-general"></a>
### 4.1 General

<a name="css-terminology"></a>
### 4.2 Terminology

<a name="css-commenting"></a>
### 4.3 Commenting

<a name="css-naming-conventions"></a>
### 4.4 Naming Conventions

<a name="css-declaration-order"></a>
### 4.5 Declaration Order

<a name="css-selectors"></a>
### 4.6 Selectors

<a name="javascript"></a>
## 5. JavaScript

<a name="references"></a>
## 6. References

- [Dive Into HTML5](http://diveintohtml5.info)
- [HTML5 Doctor](http://html5doctor.com)
- [Mozilla Developer Network](https://developer.mozilla.org)
- [World Wide Web Consortium (W3C)](http://www.w3.org)

<a name="inspiration-and-credits"></a>
## 7. Inspiration & Credits

- [Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
- [Code Guide by Mark Otto](http://codeguide.co)
- [Idiomatic CSS by Nicolas Gallagher](https://github.com/necolas/idiomatic-css)
- [CSS Guidelines by Harry Roberts](http://cssguidelin.es/)
- [TMW Unlimited Front-End Dev guidelines](http://tech.tmw.co.uk/code/TMW-frontend-guidelines)
