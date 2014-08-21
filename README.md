# HTML & CSS code guide

The purpose of this guide is to help us write reasonably consistent, maintainable and scalable code. Whilst there are brilliant [guidelines](#inspiration) that already exist, this condensed guide will help you get started. Please [open an issue on GitHub](https://github.com/michaelthorne/codeguide/issues/new) if you’d like to contribute.

## Table of Contents

- [1. General](#general)
 - [1.1 Overview](#overview)
- [2. HTML](#html)
 - [2.1 General](#html-general)
 - [2.2 Document Type Definition (DTD)](#html-document-type-definition)
 - [2.3 Language](#html-language)
 - [2.4 Character Encoding](#html-character-encoding)
 - [2.5 IE Compatibility Mode](#html-ie-compatibility-mode)
 - [x.x Using WAI-ARIA in HTML](#html-using-wai-aria)
 - [x.x Validation](#html-validation)
- [3. CSS](#css)
- [4. JavaScript](#less)
- [5. References](#references)
- [6. Inspiration](#inspiration)

<a name="general"></a>
## 1. General

Your codebase should appear as if it was written by a single person, even if multiple people contributed to it.

- It doesn’t matter which guide or style you use, but ensure that you stick to one
- Keep your code readable and easy to understand – think about the next person who has to work on it
- When in doubt, see if there’s an existing pattern that people are using or refer to other [guidelines](#inspiration)

<a name="overview"></a>
### 1.1 Overview

Use [EditorConfig](http://editorconfig.org) if your IDE or text editor supports it.

- Use **4 spaces** for indenting instead of tabs to ensure consistency (_never_ mix spaces and tabs)
- Consider a sensible maximum for line-length e.g. **80 character** wide columns
- Make use of whitespace to _improve_ readability of the code

<a name="html"></a>
## 2. HTML

<a name="html-general"></a>
### 2.1 General

This is a basic HTML document with the recommended **4 space** indenting:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <title>HTML & CSS code guide</title>
    <link rel="stylesheet" href="style.css" />
</head>
<body>
    <main role="main">
        <h1>Table of Contents</h1>
        <p>The purpose of this guide…</p>
    </main>
    <script src="script.js"></script>
</body>
</html>
```

- Always use lowercase for HTML element names, attributes and attribute values
- Only use double quotes (`""`) around attribute values
- You can omit the `type` attribute for style sheets and scripts (unless you’re not using CSS or JavaScript)
- Remove any trailing whitespace from the end of each line
- Use a new line for every [block-level](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) element

<a name="html-document-type-definition"></a>
### 2.2 Document Type Definition (DTD):

Include the HTML5 doctype:

```html
<!DOCTYPE html>
```

> Including the DOCTYPE in a document ensures that the browser makes a best-effort attempt at following the relevant specifications. – [W3C](http://www.w3.org/TR/html5/syntax.html#the-doctype)

<a name="html-language"></a>
### 2.3 Language

Specify the language [code](http://www.loc.gov/standards/iso639-2/php/code_list.php) (English):

```html
<html lang="en">
```

> Authors are encouraged to specify a lang attribute on the root html element, giving the document's language. This aids speech synthesis tools to determine what pronunciations to use, translation tools to determine what rules to use, and so forth. – [W3C](http://www.w3.org/TR/html5/semantics.html#the-html-element)

<a name="html-character-encoding"></a>
### 2.4 Character Encoding

Define the HTML document’s character set as [utf-8](http://www.utf-8.com):

```html
<meta charset="utf-8" />
```

> Unicode is a universal character set, ie. a standard that defines, in one place, all the characters needed for writing the majority of living languages in use on computers. It aims to be, and to a large extent already is, a superset of all other character sets that have been encoded. – [W3C](http://www.w3.org/International/articles/definitions-characters)

<a name="html-ie-compatibility-mode"></a>
### 2.5 IE Compatibility Mode

Ensure that Internet Explorer uses the latest engine:

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
```

> The idea behind compatibility mode is to allow web sites and applications that are not designed to modern standards to continue to work while upgrades can be made, allowing end users to upgrade to the latest browser version. Designating 'IE=edge' is the best practice because it ensures Internet Explorer uses the latest engine. The most current Internet Explorer version includes the latest security updates as well as feature support. The current version is also the fastest version. – [modern.IE](https://www.modern.ie/en-us/performance/how-to-use-x-ua-compatible)

<a name="html-using-wai-aria"></a>
### x.x Using WAI-ARIA in HTML

The main goal of the ARIA specification is to improve the overall accessibility of websites.

> WAI-ARIA, the Accessible Rich Internet Applications Suite, defines a way to make Web content and Web applications more accessible to people with disabilities. It especially helps with dynamic content and advanced user interface controls developed with Ajax, HTML, JavaScript, and related technologies. – [WAI-ARIA Overview](http://www.w3.org/WAI/intro/aria)

As per the W3C draft, [using WAI-ARIA in HTML](http://www.w3.org/TR/aria-in-html), rather use native HTML elements wherever possible as it will have the semantics and required behaviour built-in.

<a name="html-validation"></a>
### x.x Validation

Ensure that you use valid HTML wherever possible. Use tools like the [W3C Markup Validation Service](http://validator.w3.org) or the [Nu Markup Checker](http://validator.w3.org/nu). There is also a [grunt-html-validation](https://www.npmjs.org/package/grunt-html-validation) plugin.

<a name="css"></a>
## 3. CSS

<a name="js"></a>
## 4. JavaScript

<a name="references"></a>
## 5. References

- [HTML5 Doctor](http://html5doctor.com)
- [Mozilla Developer Network](https://developer.mozilla.org)
- [World Wide Web Consortium (W3C)](http://www.w3.org)

<a name="inspiration"></a>
## 6. Inspiration

- [Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
- [Idiomatic CSS by Nicolas Gallagher](https://github.com/necolas/idiomatic-css)
- [CSS Guidelines by Harry Roberts](https://github.com/csswizardry/CSS-Guidelines)
- [Code Guide by Mark Otto](http://codeguide.co)
