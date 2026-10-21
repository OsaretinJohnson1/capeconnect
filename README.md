# Intro to Web Development Practical

A lecturer-facing guide for running this classroom demo live in Cursor.
Open `index.html`, `styles.css`, and `broken.html` alongside this file
so you can jump between them while teaching.

---

## Part 1 - HTML Recap

**What is HTML in simple language:**
HTML (HyperText Markup Language) is the language we use to describe
the *structure* and *content* of a webpage. It does not make things
look pretty — it just says "this is a heading," "this is a paragraph,"
"this is a list." Think of it as the skeleton of a webpage.

**Talking points:**

- **Tags** — Keywords wrapped in angle brackets, like `<p>`. They tell
  the browser what kind of content is coming.
- **Elements** — A tag plus its content plus its closing tag, e.g.
  `<p>Hello</p>` is one element.
- **Attributes** — Extra information added inside the opening tag,
  e.g. `href` in `<a href="...">`. Format: `name="value"`.
- **Opening tags** — `<p>` — marks where content starts.
- **Closing tags** — `</p>` — marks where content ends. Note the
  forward slash.
- **`<head>`** — Information *about* the page (title, linked files).
  Nothing in here is visible on the page itself.
- **`<body>`** — Everything the visitor actually sees on the page.
- **Headings** — `<h1>` to `<h6>`, used for titles and section names.
  `<h1>` is the biggest/most important, `<h6>` the smallest.
- **Paragraphs** — `<p>`, used for blocks of normal text.
- **Links** — `<a href="...">`, used to navigate to another page or
  site.
- **Images** — `<img src="..." alt="...">`, used to display a picture.
- **Lists** — `<ul>` (unordered/bulleted) or `<ol>` (ordered/numbered),
  containing `<li>` list items.

---

## Part 2 - Student HTML Challenge

Give the students this task:

> Create an About Me webpage containing:
> 1. Your name as the main heading
> 2. A paragraph introducing yourself
> 3. A heading called My Interests
> 4. At least three interests in a list
> 5. An image
> 6. A link to a website you use regularly

**LECTURER REFERENCE — expected solution:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me</title>
</head>
<body>
    <h1>My Name</h1>

    <p>Hi, I'm a student learning how to build websites!</p>

    <h2>My Interests</h2>
    <ul>
        <li>Music</li>
        <li>Sports</li>
        <li>Movies</li>
    </ul>

    <img src="images/placeholder.svg" alt="A picture of me">

    <p>
        I often visit
        <a href="https://www.youtube.com">YouTube</a>.
    </p>
</body>
</html>
```

---

## Part 3 - Debugging Challenge

Open `broken.html` in Cursor and in the browser. Do not scroll down to
the answer key on the projector — it is hidden inside an HTML comment
so students will not see it in the browser.

**Questions to ask the class (with answers for you):**

1. *What is wrong with this line?* (point at `<h1>Welcome To My Page`)
   → The `<h1>` is never closed.
2. *Which tag is missing?* (point at the `<image>` line)
   → There's no such tag as `<image>` — it should be `<img>`.
3. *What does the `alt` attribute do?*
   → It provides a text description of the image, used by screen
   readers and shown if the image fails to load.
4. *Why isn't this image displaying?* (point at `profile-pic.png`)
   → The file path is wrong — that file doesn't exist in the
   `images` folder.
5. *Why doesn't this link work?* (point at `<a>Wikipedia</a>`)
   → It has no `href` attribute, so it has no destination.
6. *What happens if we forget to close this tag?*
   → The browser may guess where it ends, sometimes breaking the
   layout of everything after it.
7. *What's wrong with putting `<h2>` inside `<p>`?*
   → `<p>` should only contain text-level content; headings are
   block-level and shouldn't be nested inside a paragraph.

The full breakdown of every mistake (12 in total) is in the HTML
comment at the bottom of `broken.html`, labelled `LECTURER ANSWER KEY`.

---

## Part 4 - Transition to CSS

**Script:**

> "We've created the structure and content of our website using HTML.
> But HTML isn't really responsible for making our website look good.
> What if I want this heading to be blue? What if I want a different
> font? What if I want to change the background? That's where CSS
> comes in."

**Key distinction to write on the board:**

- **HTML** = structure / content (what the page *contains*)
- **CSS** = style / presentation (how the page *looks*)

**Walk through this example:**

```css
h1 {
    color: blue;
    font-size: 36px;
}
```

- `h1` — the **selector** (which element are we styling?)
- `color` — the **property** (what aspect are we changing?)
- `blue` — the **value** (what should it be changed to?)
- `color: blue;` together is called a **declaration**. A rule can
  have many declarations, each ending in a semicolon, all wrapped in
  curly braces `{ }`.

---

## Part 5 - CSS Challenge

Give students the following task:

> Using the About Me webpage you created earlier:
> 1. Change the background colour of the page.
> 2. Change the colour of your main heading.
> 3. Change the font size of your paragraph.
> 4. Change the font used on the page.
> 5. Change the size of your image.

**Reference solution:**

```css
body {
    background-color: lightyellow;
    font-family: Verdana, sans-serif;
}

h1 {
    color: purple;
}

p {
    font-size: 20px;
}

img {
    width: 150px;
}
```

Remind students to link their CSS file in `<head>`:

```html
<link rel="stylesheet" href="styles.css">
```

---

## Part 6 - Assignment Clinic

Students should open the websites they are pitching in two days.
Pair them up for peer review.

**Partner A reviews Partner B's website:**

- Can I tell what the website is about?
- Are headings used properly?
- Is the content organised?
- Do the images display?
- Do the links work?
- Is the HTML structured properly?
- Can the creator explain the purpose of the website?
- What is one thing that could be improved?

Then partners swap roles and repeat.

---

## Part 7 - Questions I Can Ask the Class

Ask these throughout the lesson. Answers are directly underneath each
one, for your reference only.

1. **What does HTML stand for?**
   HyperText Markup Language.
2. **What is a tag?**
   A keyword in angle brackets that tells the browser what kind of
   content follows, e.g. `<p>`.
3. **What is the difference between `<head>` and `<body>`?**
   `<head>` holds information about the page (not visible); `<body>`
   holds everything visitors actually see.
4. **What does `href` do?**
   It specifies the destination URL of a link.
5. **What does `src` do?**
   It specifies the source file (e.g. an image) to load.
6. **Why do images need alt text?**
   For accessibility (screen readers) and as a fallback if the image
   fails to load.
7. **What would happen if I removed this tag?**
   (Context-dependent) Usually the browser will try to guess the
   structure, which can break layout or nesting.
8. **Does HTML control what the website looks like or what it
   contains?**
   What it contains (structure/content) — not appearance.
9. **What is CSS used for?**
   Styling and presentation — colours, fonts, spacing, sizing.
10. **What is a CSS selector?**
    The part of a CSS rule that chooses which HTML element(s) to
    style, e.g. `h1`.
11. **What symbol is used to close a tag?**
    A forward slash inside angle brackets, e.g. `</p>`.
12. **What's the difference between an ordered and unordered list?**
    Ordered lists (`<ol>`) are numbered; unordered lists (`<ul>`) use
    bullet points.
13. **What's an attribute?**
    Extra information added to an opening tag, written as
    `name="value"`.
14. **Why do we use a `<title>` tag?**
    It sets the text shown in the browser tab.
15. **What does the viewport meta tag do?**
    It helps the page display correctly on different screen sizes,
    especially mobile devices.
16. **What happens if two tags overlap incorrectly (bad nesting)?**
    The browser may render the page in an unexpected way; nested tags
    must open and close in the correct order.
17. **Why should CSS usually go in a separate file instead of inline?**
    It keeps structure (HTML) and style (CSS) separate, making both
    easier to read, maintain, and reuse across multiple pages.

---

## If Students Are Ahead

Simple extensions to keep faster students engaged:

- **Ordered vs unordered lists** — Ask them to convert their
  interests list into an `<ol>` and notice the numbering appear
  automatically.
- **Adding multiple pages** — Create a second file, e.g.
  `contact.html`, with the same basic HTML structure.
- **Navigation between two HTML files** — Add a link in `index.html`
  pointing to `contact.html` (and back again), e.g.
  `<a href="contact.html">Contact</a>`.
- **Introducing `class` and `id` attributes** — Explain that `class`
  can be reused on many elements, while `id` should be unique to one
  element. Example: `<p class="highlight">`.
- **Adding a simple CSS class** — Have them style just the elements
  with that class:
  ```css
  .highlight {
      color: red;
  }
  ```

## If Students Are Struggling

Simplify the lesson to just these core concepts, and hold off on CSS
entirely until they're solid here:

- HTML document structure (`<!DOCTYPE html>`, `<html>`, `<head>`,
  `<body>`)
- Headings (`<h1>`–`<h6>`)
- Paragraphs (`<p>`)
- Lists (`<ul>`, `<li>`)
- Links (`<a href="...">`)
- Images (`<img src="..." alt="...">`)

Have them practise writing just these elements by hand until they can
explain what each one does, before introducing anything about
appearance or styling.
