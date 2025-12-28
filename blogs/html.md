<pre class="ascii">
┌──────────────────────────────────┐ ┌───────────────────────────────────────────┐ ┌───────────────────────────────────────────┐
|     _   _ _____ __  __ _         | │ Latest posts                              │ │ NAV                                       │
|    | | | |_   _|  \/  | |        | │ - <a href="/blogs/html.md">HTML</a>                                    │ │ - <a href="/blogs/html.md">HTML</a>                                    │
|    | |_| | | | | |\/| | |        | │ - ...                                     │ │ - <a href="https://github.com/0-harshit-0/">About</a>                                   │
|    |  _  | | | | |  | | |___     | │                                           │ │                                           │
|    |_| |_| |_| |_|  |_|_____|    | │                                           │ │                                           │
└──────────────────────────────────┘ └───────────────────────────────────────────┘ └───────────────────────────────────────────┘
</pre>

- [Skip to learning resources](#more-reading-material).
- Let's start with the full form 😜: **HyperText Markup Language**.
- HTML is used to provide structure to a web page.
- This structure can be used to make a visually appealing and accessible site.
- This structure can also be used by machines/search engines/algorithms to understand a site, because they can't _"see"_ or _"use"_ a page the way humans do, they infer meaning from structure (HTML mostly) and presentation cues (CSS).


## Tags

- Tags are the basic building blocks of HTML. HTML uses tags to structure and describe content (for example, `<p>`, `<a>`, and `<div>`).

- Each tag has its own role and often comes with default browser styles. Here's a quick-start list:
    - `<html>`   The root element that wraps the whole HTML document.
    - `<head>`   Holds metadata like the page title and other non-visible setup info.
    - `<body>`   Contains the visible content of the page.
    - `<div>`   A generic block container used to group content (often for layout/styling).
    - `<h1>`   A top-level heading.
    - `<p>`   A paragraph of text.
> Check out https://www.w3schools.com/TAGS/default.asp for an extensive list of tags.

- Although it's possible to reset styles and build a whole page using just one tag (like `<div>`), machines can't reliably understand the meaning of different parts of the page if everything is in the same tag. For example, a common "everything is a div" structure looks like this:
```html
<div>
  <div>heading</div>
  <div>
    <div>nav1</div>
    <div>nav2</div>
    <div>nav3</div>
  </div>
</div>

<div>
  <div>topic heading 1</div>
  <div>
    <div>content</div>
  </div>

  <div>topic heading 2</div>
  <div>
    <div>content</div>
  </div>
</div>

<div>footer</div>
```
Now, this looks fine, and you can style it, add animations, etc., but the machine sees only one thing everywhere (i.e., `<div>`). It will try to infer structure using other signals, but not having meaningful tags can lead to issues.


## Attributes

- Attributes add extra information and behavior to an HTML element by attaching name/value pairs inside the opening tag (for example, href, src, alt, id, class).
- "id" is meant to uniquely identify one element on a page, while "class" is reusable across many elements (and one element can have multiple classes).
- Example: `<div id="hero" class="section section--featured">...</div>`.
> Explore more attributes at https://www.w3schools.com/html/html_attributes.asp.


## Topics to cover to complete your HTML journey:
- Tags (semantics, metas, doctype, etc)
- Attributes (styles, events, i18n, a11y, datasets)
- Elements (an element is typically a start tag + content + end tag, or a void element)
- Templates
- Custom elements
- JSON schema


> [!NOTE]
> Recommended(by me) source for complete and properly learning: https://web.dev/html.


## More reading material

- [HTML history](https://www.w3.org/People/Raggett/book4/ch02.html#:~:text=In%20other%20words%2C%20there%20could,from%20one%20paper%20to%20another.)
- https://web.dev/html


