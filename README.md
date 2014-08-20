# HTML & CSS code guide

The purpose of this guide is to help us write reasonably consistent, maintainable and scalable code. Whilst there are brilliant [guidelines](#inspiration) that already exist, I wanted to create one based on my own experiences. Please [open an issue on GitHub](https://github.com/michaelthorne/codeguide/issues/new) if you’d like to contribute.

## Table of Contents

- [1. General](#general)
 - [1.1 Overview](#overview)
- [2. HTML](#html)
 - [2.1 General](#html-general)
 - [2.2 Doctype](#html-doctype)
 - [2.3 Language](#html-language)
 - [2.4 Character Encoding](#html-character-encoding)
- [3. CSS](#css)
- [4. JavaScript](#less)
- [5. Inspiration](#inspiration)

<a name="general"></a>
## 1. General

Your codebase should appear as if it was written by a single person, even if multiple people contributed to it.

- It doesn’t matter which guide or code style you ultimately end up using, but just make sure you stick to one.
- Keep your code readable and easy to understand – be considerate towards the next person who has to work on it.
- When in doubt, see if there’s an existing pattern that people are using. Or refer to other [guidelines](#inspiration).

<a name="overview"></a>
### 1.1 Overview

If you have a text editor or IDE that supports [EditorConfig](http://editorconfig.org), I highly recommend using it.

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
    <title>Title</title>
</head>
<body>
    <main>
        <h1>Hello world!</h1>
        <p>This is awesome…</p>
    </main>
</body>
</html>
```

<a name="html-doctype"></a>
### 2.2 Doctype

Include the HTML5 document type definition (or DTD):

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

<a name="css"></a>
## 3. CSS

<a name="js"></a>
## 4. JavaScript

<a name="inspiration"></a>
## 5. Inspiration

- [Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
- [Idiomatic CSS by Nicolas Gallagher](https://github.com/necolas/idiomatic-css)
- [CSS Guidelines by Harry Roberts](https://github.com/csswizardry/CSS-Guidelines)
- [Code Guide by Mark Otto](http://codeguide.co)
