# HTML – Class 03 Notes
## HTML Headings, Text Formatting, Lists, Attributes, and the Marquee Tag

> **Source:** Class 03 transcript  
> **Language:** English  
> **Level:** Beginner  
> **Purpose:** Understand the HTML tags and attributes introduced in this class, practise them in VS Code, and learn where older HTML techniques should be avoided in modern websites.

---

## 1. Quick Recap of the Previous Class

The instructor begins by revising the previous class:

- HTML stands for **HyperText Markup Language**.
- HTML provides the structure and content of a web page.
- CSS is used for styling and layout.
- JavaScript is used to add behaviour and interactivity.
- VS Code is the code editor used during the course.
- The class previously covered creating files and folders, installing extensions, generating the HTML boilerplate, and running a page with Live Server.

The instructor also revisits the main parts of an HTML document:

- `<!DOCTYPE html>` declares an HTML5 document.
- `<html>` is the root element.
- `<head>` contains document information, metadata, and the page title.
- `<title>` defines the text shown in the browser tab.
- `<body>` contains the content displayed on the web page.

### 1.1 Organising a project folder

The instructor creates a project folder and places related files in separate folders.

A typical structure is:

```text
html-class/
│
├── index.html
│
├── css/
│
├── js/
│
└── media/
```

**Why organise files this way?**

- `index.html` is the main HTML page in this example.
- `css/` can hold stylesheets.
- `js/` can hold JavaScript files.
- `media/` can hold images and other media assets.

The instructor explains that `index.html` is commonly used as the main page of a website. Web servers are often configured to serve a file named `index.html` by default when someone opens a directory.

> **Important clarification:** It is not quite correct to say that a browser automatically gives `index.html` priority over every other HTML file. `index.html` is a widely used default entry-page convention, usually handled by the web server or hosting setup.

### 1.2 Opening the correct file with Live Server

When you create a new HTML file, make sure you run that file with Live Server. If Live Server is already running another page, the browser may continue showing the older page.

**Practical reminder:** Check the browser tab and URL after clicking **Go Live**. Confirm that you are viewing the file you are currently editing.

---

## 2. HTML Heading Tags: `<h1>` to `<h6>`

### Definition

**Heading tags** define headings and subheadings on a web page. HTML provides six heading levels, from `<h1>` to `<h6>`.

```html
<h1>Main Heading</h1>
<h2>Section Heading</h2>
<h3>Subsection Heading</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

### 2.1 Difference between the heading levels

- `<h1>` represents the highest-level heading.
- `<h2>` represents a section under the main heading.
- `<h3>` represents a subsection under an `<h2>`.
- `<h4>`, `<h5>`, and `<h6>` provide further levels of subdivision.
- By default, `<h1>` is visually the largest heading and `<h6>` is the smallest.

The instructor uses a Wikipedia page as an example: the page's main subject, such as “India,” can be represented by the main heading, while the topics inside the page can use lower-level headings.

### 2.2 A logical heading hierarchy

Headings should describe the structure of the page, not merely provide different text sizes.

```html
<h1>India</h1>

<h2>History</h2>
<h3>Ancient History</h3>
<h3>Modern History</h3>

<h2>Geography</h2>
<h3>Climate</h3>
<h3>Rivers</h3>
```

This creates a meaningful hierarchy:

```text
India
├── History
│   ├── Ancient History
│   └── Modern History
└── Geography
    ├── Climate
    └── Rivers
```

### 2.3 The instructor's H1 rule and a modern clarification

The instructor recommends using `<h1>` for the main heading and then using `<h2>`, `<h3>`, and the remaining levels for the content below it. The instructor also advises against repeatedly using `<h1>` on the same page.

For beginner projects, following **one clear main `<h1>` per page** is a useful and simple convention.

**Technical clarification:** HTML does not make a second `<h1>` invalid, and “only one H1” is not an absolute HTML syntax rule. The important point is to use headings in a logical order that accurately represents the page's content. Do not choose heading tags only because their default font sizes look right; CSS should control visual sizing.

---

## 3. Paragraph Tag: `<p>`

### Definition

The **paragraph tag** is used to place a paragraph of text on a web page.

**Syntax:**

```html
<p>Your paragraph goes here.</p>
```

**Example:**

```html
<p>Good evening! Welcome to my first HTML page.</p>
```

The opening `<p>` tag marks the beginning of the paragraph, and `</p>` marks its end.

### 3.1 Why use a paragraph tag?

A paragraph tag tells the browser that the enclosed content is a paragraph. It also gives the browser a default paragraph layout, including space before and after the paragraph.

You should place ordinary paragraph content inside `<p>` rather than writing loose text directly inside `<body>`.

```html
<body>
    <h1>Welcome</h1>

    <p>This is my first paragraph.</p>
    <p>This is my second paragraph.</p>
</body>
```

### 3.2 What happens to spaces and line breaks in a paragraph?

A common beginner confusion is that pressing Enter or adding several spaces in the HTML editor does not necessarily create the same spacing on the web page.

For example:

```html
<p>
    Good
            Evening
</p>
```

The browser normally collapses runs of whitespace in regular HTML text. The result will generally read as:

`Good Evening`

A new line in your source code is not automatically a visible line break in a paragraph.

To create a deliberate line break, use `<br>`.

---

## 4. Preformatted Text Tag: `<pre>`

### Definition

The `<pre>` tag is used for **preformatted text**. It preserves the spaces and line breaks written inside the element.

**Example:**

```html
<pre>
Good
    Evening
        Everyone
</pre>
```

The browser displays the text with its spacing and line arrangement preserved.

### 4.1 Difference between `<p>` and `<pre>`

| Feature | `<p>` | `<pre>` |
|---|---|---|
| Main purpose | Ordinary paragraph | Preformatted text |
| Multiple spaces | Usually collapsed | Preserved |
| Source-code line breaks | Usually collapsed into normal spacing | Preserved |
| Default font | Usually proportional | Usually monospace |
| Common use | Paragraphs and normal text | Code samples or text where spacing matters |

### Remember

Use `<p>` for normal paragraphs. Use `<pre>` when the exact whitespace and line arrangement are important.

The instructor points out that `<pre>` is not commonly needed for ordinary page paragraphs. It is still useful to understand because it is a distinct HTML element and may appear in questions or code examples.

---

## 5. Line Break Tag: `<br>`

### Definition

The `<br>` tag creates a **line break**. The content after it begins on the next line.

**Example:**

```html
<p>
    Good<br>
    Evening
</p>
```

The browser displays:

```text
Good
Evening
```

### When is `<br>` useful?

Use `<br>` when a line break is genuinely part of the content, for example:

- An address written on separate lines.
- A poem or a short line-based text.
- A deliberate line break within a piece of text.

Do not use repeated `<br>` tags just to create large gaps between sections. Use CSS spacing for layout.

### 5.1 Void elements and the term “self-closing”

The instructor calls `<br>` a **self-closing tag** because it does not have a separate closing tag and does not wrap content.

A more precise HTML term is **void element**.

A void element cannot contain child content and does not require a closing tag.

Both of these notations are commonly encountered:

```html
<br>
<br />
```

In HTML, the normal form is simply `<br>`.

---

## 6. Horizontal Rule Tag: `<hr>`

### Definition

The `<hr>` tag represents a **thematic break** between sections of content. In a typical browser, it appears as a horizontal line.

**Example:**

```html
<p>This is the first section.</p>

<hr>

<p>This is the next section.</p>
```

### Important points

- `<hr>` does not wrap text.
- It is a void element, like `<br>`.
- It is useful when the content has a meaningful section break.
- CSS can be used to customise its colour, thickness, width, and spacing.

### `<br>` vs `<hr>`

| Tag | Purpose | Typical result |
|---|---|---|
| `<br>` | Break a line | Moves following text to the next line |
| `<hr>` | Mark a thematic break | Displays a horizontal divider |

---

## 7. Bold Text Tag: `<b>`

### Definition

The `<b>` tag displays its enclosed text in **bold** by default.

**Syntax:**

```html
<b>Text to make bold</b>
```

**Example:**

```html
<p>
    The capital of India is <b>New Delhi</b>.
</p>
```

Only the text placed between `<b>` and `</b>` receives the bold presentation.

### Important distinction

The class demonstrates `<b>` as a way to make selected text bold.

Modern HTML also provides `<strong>`:

```html
<p>
    <strong>Warning:</strong> Save your work before closing the editor.
</p>
```

- `<b>` draws attention to text without necessarily saying that it is more important.
- `<strong>` indicates that the enclosed text has strong importance.

Use the element that matches the meaning of the content.

---

## 8. Italic Text Tag: `<i>`

### Definition

The `<i>` tag displays its enclosed text in *italic* by default. Italic text is usually shown with a slight slant.

**Syntax:**

```html
<i>Text to make italic</i>
```

**Example:**

```html
<p>
    This article is about the <i>Republic of India</i>.
</p>
```

Only the text placed between `<i>` and `</i>` receives the italic presentation.

### `<b>` vs `<i>`

| Tag | Default presentation | Purpose shown in the class |
|---|---|---|
| `<b>` | Bold | Make selected text bold |
| `<i>` | Italic | Make selected text italic |

**Modern semantic alternatives:**

- Use `<strong>` when text has strong importance.
- Use `<em>` when text should receive emphasis.

```html
<p>
    This is <strong>very important</strong>.
    You should <em>carefully</em> read the instructions.
</p>
```

---

## 9. HTML Lists

### Definition

An **HTML list** groups related items together. The instructor explains lists through a shopping example: buying Maggi, Maggi masala, and ketchup.

The class introduces two main list types:

1. Ordered list
2. Unordered list

### 9.1 Ordered List: `<ol>`

An **ordered list** is used when the order or sequence of the items matters.

The tag name is `ol`, which stands for **ordered list**.

**Example:**

```html
<ol>
    <li>Buy Maggi</li>
    <li>Buy Maggi masala</li>
    <li>Buy ketchup</li>
</ol>
```

**Typical browser output:**

1. Buy Maggi
2. Buy Maggi masala
3. Buy ketchup

### 9.2 List Item: `<li>`

The `<li>` tag defines an individual **list item**.

- `li` means list item.
- Each item in an ordered or unordered list is placed inside its own `<li>` element.
- The `<li>` elements are placed inside the parent `<ol>` or `<ul>` element.

**Basic pattern:**

```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

### 9.3 Unordered List: `<ul>`

An **unordered list** is used when the sequence of the items is not important.

The tag name is `ul`, which stands for **unordered list**.

**Example:**

```html
<ul>
    <li>Buy Maggi</li>
    <li>Buy Maggi masala</li>
    <li>Buy ketchup</li>
</ul>
```

**Typical browser output:**

- Buy Maggi
- Buy Maggi masala
- Buy ketchup

The browser displays a marker, commonly a filled circle, before each item.

### 9.4 Ordered list vs unordered list

| Feature | Ordered list | Unordered list |
|---|---|---|
| Tag | `<ol>` | `<ul>` |
| Meaning | Items have a sequence or ranking | Item order is not important |
| Default marker | Numbers | Bullets |
| Each item uses | `<li>` | `<li>` |
| Example | Instructions or ranked steps | Shopping list or feature list |

### 9.5 When should you use each one?

Use an ordered list when the sequence matters:

```html
<h2>How to make tea</h2>

<ol>
    <li>Boil water.</li>
    <li>Add tea leaves.</li>
    <li>Add milk and sugar.</li>
    <li>Strain and serve.</li>
</ol>
```

Use an unordered list when the sequence does not matter:

```html
<h2>Things to buy</h2>

<ul>
    <li>Milk</li>
    <li>Bread</li>
    <li>Apples</li>
</ul>
```

---

## 10. List Marker Types

The instructor demonstrates that the default markers of lists can be changed with the `type` attribute.

### 10.1 Changing an ordered list

The `type` attribute can change the numbering style of an `<ol>` list.

| Value | Marker style | Example |
|---|---|---|
| `1` | Numbers | 1, 2, 3 |
| `A` | Uppercase letters | A, B, C |
| `a` | Lowercase letters | a, b, c |
| `I` | Uppercase Roman numerals | I, II, III |
| `i` | Lowercase Roman numerals | i, ii, iii |

**Examples:**

```html
<ol type="A">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

```html
<ol type="i">
    <li>Introduction</li>
    <li>Learning</li>
    <li>Practice</li>
</ol>
```

The default ordered-list style is numeric (`1`, `2`, `3`).

### 10.2 Changing an unordered list

The instructor demonstrates three unordered-list marker styles:

| Value | Marker appearance |
|---|---|
| `disc` | Filled circle |
| `circle` | Hollow circle |
| `square` | Filled square |

**Examples:**

```html
<ul type="disc">
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

```html
<ul type="circle">
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

```html
<ul type="square">
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

### Modern HTML note

The lesson uses the `type` attribute to demonstrate marker changes. For modern web development, CSS is the preferred way to style unordered-list markers:

```html
<ul class="square-list">
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

```css
.square-list {
    list-style-type: square;
}
```

For ordered lists, CSS `list-style-type` can also control the marker appearance. The ordered-list `type` attribute remains useful to recognise in existing HTML and examples.

---

## 11. HTML Attributes

### Definition

An **attribute** provides additional information about an HTML element or changes how that element behaves.

Attributes are written in the **opening tag**, after the tag name.

**General syntax:**

```html
<tagname attribute="value">Content</tagname>
```

Example:

```html
<p id="intro" class="highlight">
    Welcome to HTML.
</p>
```

Here:

- `p` is the tag name.
- `id` is an attribute.
- `intro` is the value of the `id` attribute.
- `class` is another attribute.
- `highlight` is the value of the `class` attribute.

### 11.1 Where do attributes go?

Attributes are written inside the opening tag—not between the opening and closing tags.

**Correct:**

```html
<h1 id="main-heading">Welcome</h1>
```

**Incorrect:**

```html
<h1> id="main-heading" Welcome</h1>
```

### 11.2 The `id` attribute

The `id` attribute gives an element a unique identifier within a page.

```html
<h1 id="main-heading">Welcome</h1>
```

It can be used to target a specific element with CSS or JavaScript.

```css
#main-heading {
    color: blue;
}
```

### 11.3 The `class` attribute

The `class` attribute assigns one or more class names to an element. The same class can be reused on multiple elements.

```html
<p class="highlight">First paragraph</p>
<p class="highlight">Second paragraph</p>
```

CSS can target the class:

```css
.highlight {
    background-color: yellow;
}
```

### 11.4 Difference between `id` and `class`

| Feature | `id` | `class` |
|---|---|---|
| Main purpose | Identifies a specific element | Groups elements under a shared name |
| Reuse | Normally unique on a page | Can be used on many elements |
| CSS selector | `#name` | `.name` |
| Example | `id="header"` | `class="card"` |

**Remember:** The instructor explains that `id` and `class` can be used on different HTML tags. They are called global attributes because they are available on nearly all HTML elements.

### 11.5 The `type` attribute on lists

The lesson also demonstrates an element-specific attribute: `type`.

For example:

```html
<ol type="A">
    <li>One</li>
    <li>Two</li>
</ol>
```

Here, `type="A"` changes the ordered-list markers to uppercase letters.

The `type` attribute is not a universal attribute for every HTML tag. It is only meaningful on elements that support it.

---

## 12. VS Code Shortcut: Toggle Word Wrap

The instructor demonstrates a shortcut for long lines of code or text.

**Shortcut: `Alt + Z`**

This toggles **Word Wrap** in VS Code.

When a line is very long, it may extend horizontally beyond the visible editor area. Word Wrap makes the text continue on the next visual line inside the editor.

- Press `Alt + Z` to enable Word Wrap.
- Press `Alt + Z` again to disable it.

**Important:** Word Wrap changes only how text is displayed inside the VS Code editor. It does not insert line breaks into your HTML file.

The instructor also demonstrates:

**Shortcut: `Alt + Shift + Down Arrow`**

This duplicates the current line or selected lines downward in VS Code, which is useful when creating repeated `<li>` elements.

---

## 13. Marquee Tag: `<marquee>`

### Definition

The `<marquee>` element was used to make text or other content move or scroll across a page.

The instructor demonstrates it with the text “Skill Campus”.

**Basic example:**

```html
<marquee>
    Skill Campus
</marquee>
```

By default, the content moves horizontally across the page.

### Important modern HTML warning

`<marquee>` is an obsolete, non-standard HTML element. It is taught here because it appears in the class transcript and may be useful to recognise in older examples.

**Do not use `<marquee>` in modern production websites.** Use CSS animations or other modern techniques when you need moving text.

### 13.1 The `direction` attribute

The instructor demonstrates changing the direction in which the marquee content moves.

| Value | Movement |
|---|---|
| `left` | Moves towards the left |
| `right` | Moves towards the right |
| `up` | Moves upwards |
| `down` | Moves downwards |

**Example:**

```html
<marquee direction="right">
    Skill Campus
</marquee>
```

Other direction examples:

```html
<marquee direction="left">Moving left</marquee>
<marquee direction="up">Moving up</marquee>
<marquee direction="down">Moving down</marquee>
```

The default direction is typically left.

### 13.2 The `behavior` attribute

The `behavior` attribute changes the movement pattern.

The instructor demonstrates three values:

| Value | Behaviour |
|---|---|
| `scroll` | Content continuously moves across the marquee area |
| `slide` | Content moves into the area and stops at the end |
| `alternate` | Content moves back and forth, bouncing between the edges |

**Examples:**

```html
<marquee behavior="scroll">
    Continuous movement
</marquee>
```

```html
<marquee behavior="slide">
    Moves once and stops
</marquee>
```

```html
<marquee behavior="alternate">
    Moves back and forth
</marquee>
```

### 13.3 The `scrollamount` attribute

The instructor uses `scrollamount` to change the movement speed.

- A larger value makes the content move faster.
- A smaller value makes it move more slowly.

**Example:**

```html
<marquee scrollamount="10">
    Skill Campus
</marquee>
```

The instructor compares values such as `1`, `10`, and `20` to show the difference in movement speed.

### 13.4 The `bgcolor` attribute

The instructor demonstrates `bgcolor` to set the background colour of the marquee area.

**Example:**

```html
<marquee bgcolor="yellow">
    Skill Campus
</marquee>
```

The marquee area receives a yellow background.

**Modern HTML note:** `bgcolor` is an old presentation attribute and should not be used for modern styling. CSS is the preferred approach for colours and backgrounds.

### 13.5 Combining the marquee attributes

The following example combines the attributes demonstrated in class:

```html
<marquee
    direction="right"
    behavior="alternate"
    scrollamount="10"
    bgcolor="yellow"
>
    Skill Campus
</marquee>
```

This example represents the class demonstration:

- `direction="right"` sets the movement direction.
- `behavior="alternate"` makes the content bounce back and forth.
- `scrollamount="10"` controls the movement amount/speed.
- `bgcolor="yellow"` sets the background colour in this legacy element.

### 13.6 Why the instructor says not to use marquee in modern development

The instructor explains that marquee is not commonly used today because animations can be created with CSS. CSS provides much more control over movement, speed, timing, direction, and responsive behaviour.

A basic modern CSS animation example:

```html
<div class="moving-text">
    Skill Campus
</div>
```

```css
.moving-text {
    white-space: nowrap;
    animation: move-text 5s linear infinite alternate;
}

@keyframes move-text {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

This is supplementary modern CSS knowledge, not a code example taught in the transcript.

---

## 14. Complete Practice Example

The following single HTML file combines the main topics introduced in this class.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Class 03 Practice</title>
</head>

<body>

    <h1 id="main-heading">Learning HTML</h1>

    <h2>Introduction</h2>

    <p class="intro">
        HTML is used to create the structure of web pages.
        It helps us organise headings, paragraphs, and lists.
    </p>

    <p>
        This is a paragraph with a <b>bold word</b> and an
        <i>italic word</i>.
    </p>

    <h2>Using a Line Break</h2>

    <p>
        Good<br>
        Evening
    </p>

    <hr>

    <h2>Preformatted Text</h2>

    <pre>
Good
    Evening
        Everyone
    </pre>

    <h2>Ordered List</h2>

    <ol type="A">
        <li>Learn HTML</li>
        <li>Learn CSS</li>
        <li>Learn JavaScript</li>
    </ol>

    <h2>Unordered List</h2>

    <ul type="square">
        <li>Notebook</li>
        <li>Pen</li>
        <li>Laptop</li>
    </ul>

</body>
</html>
```

### What this example practises

| HTML feature | Where it appears |
|---|---|
| Main heading | `<h1>` |
| Subheadings | `<h2>` |
| Paragraph | `<p>` |
| Bold text | `<b>` |
| Italic text | `<i>` |
| Line break | `<br>` |
| Horizontal rule | `<hr>` |
| Preformatted text | `<pre>` |
| Ordered list | `<ol>` |
| Unordered list | `<ul>` |
| List item | `<li>` |
| Unique identifier | `id="main-heading"` |
| Reusable class | `class="intro"` |
| List marker style | `type="A"` and `type="square"` |

---

## 15. Common Beginner Mistakes

1. **Using a heading tag just to make text large:** Use headings to organise page content. Use CSS to control the visual size.
2. **Skipping heading levels without a reason:** Keep the heading hierarchy logical, such as H1 → H2 → H3.
3. **Expecting Enter to create a visible line break in a paragraph:** Normal HTML collapses source whitespace. Use `<br>` when a line break is meaningful.
4. **Using `<pre>` for every paragraph:** Use `<p>` for ordinary paragraphs and `<pre>` when whitespace must be preserved.
5. **Forgetting `<li>` inside a list:** Each list item belongs inside an `<li>` element.
6. **Confusing `<ol>` and `<ul>`:** Use `<ol>` when sequence matters and `<ul>` when it does not.
7. **Putting attributes outside the opening tag:** Write attributes inside the opening tag, such as `<p class="intro">`.
8. **Assuming every attribute works on every tag:** `id` and `class` are broadly available; other attributes are element-specific.
9. **Using `<marquee>` in a modern website:** It is obsolete. Use CSS animation instead.
10. **Thinking `Alt + Z` inserts HTML line breaks:** It only toggles how long lines wrap visually in the VS Code editor.

---

## 16. Quick Revision Sheet

| Tag / Attribute | Meaning / Purpose |
|---|---|
| `<h1>` | Highest-level heading |
| `<h2>` – `<h6>` | Lower-level headings |
| `<p>` | Paragraph |
| `<pre>` | Preformatted text; preserves whitespace |
| `<br>` | Line break |
| `<hr>` | Thematic break / horizontal divider |
| `<b>` | Bold presentation |
| `<i>` | Italic presentation |
| `<ol>` | Ordered list |
| `<ul>` | Unordered list |
| `<li>` | List item |
| `type` | Changes list marker style where supported |
| `id` | Identifier for a specific element |
| `class` | Reusable class name for elements |
| `<marquee>` | Legacy scrolling-content element; avoid in modern sites |
| `direction` | Legacy marquee movement direction |
| `behavior` | Legacy marquee movement pattern |
| `scrollamount` | Legacy marquee movement amount/speed |
| `bgcolor` | Legacy background-colour attribute |

### Important values to remember

**Ordered list (`<ol type="...">`):**

- `1` → 1, 2, 3
- `A` → A, B, C
- `a` → a, b, c
- `I` → I, II, III
- `i` → i, ii, iii

**Unordered list (as demonstrated in the lesson):**

- `disc` → filled circle
- `circle` → hollow circle
- `square` → filled square

**Marquee (legacy element):**

- `direction`: `left`, `right`, `up`, `down`
- `behavior`: `scroll`, `slide`, `alternate`

**VS Code shortcuts:**

- `Alt + Z` → Toggle Word Wrap
- `Alt + Shift + Down Arrow` → Duplicate line/selection downward

---

## 17. Practice Tasks

Practise the following in VS Code using a separate file such as `class-03-practice.html`.

1. Create a page with one `<h1>` and at least three lower-level headings.
2. Write two paragraphs using `<p>`.
3. Make one word bold using `<b>` and another italic using `<i>`.
4. Use `<br>` to put a person's name and address on separate lines.
5. Add an `<hr>` between two content sections.
6. Use `<pre>` to display three lines with different indentation.
7. Create an ordered list of five steps. Try `1`, `A`, `a`, `I`, and `i`.
8. Create an unordered list of five items. Try `disc`, `circle`, and `square`.
9. Add an `id` to one heading and a reusable `class` to two paragraphs.
10. Identify the legacy marquee attributes shown in the class. Experiment only in a practice file, and then try to reproduce a similar moving-text effect with CSS.

---

## 18. Self-Test Questions

Try answering these without looking at the notes.

1. What is the purpose of heading tags in HTML?
2. How many heading levels does HTML provide?
3. What is the difference between `<h1>` and `<h6>`?
4. What is the purpose of the `<p>` tag?
5. Why does pressing Enter in a paragraph's source code not always create a visible new line?
6. What is the purpose of the `<pre>` tag?
7. What is the difference between `<p>` and `<pre>`?
8. What does `<br>` do?
9. What does `<hr>` do?
10. Why are `<br>` and `<hr>` called void elements?
11. What is the purpose of `<b>` and `<i>`?
12. What is the difference between an ordered and an unordered list?
13. What does `<li>` represent?
14. Which attribute changes the marker style of a list in the class examples?
15. What are the `id` and `class` attributes used for?
16. Where should attributes be written?
17. What does `Alt + Z` do in VS Code?
18. What is the purpose of the `<marquee>` element?
19. What is the difference between `scroll`, `slide`, and `alternate`?
20. Why should modern developers avoid `<marquee>`?

---

## 19. Key Takeaways from Class 03

- HTML has six heading levels: `<h1>` through `<h6>`.
- Use headings to create a meaningful content hierarchy.
- Use `<p>` for ordinary paragraphs.
- Use `<pre>` when spaces and line breaks must be preserved.
- Use `<br>` for a meaningful line break and `<hr>` for a thematic break.
- `<b>` and `<i>` provide bold and italic presentation.
- `<ol>` creates an ordered list; `<ul>` creates an unordered list.
- `<li>` represents an individual list item.
- Attributes provide additional information or configuration to an element.
- `id` identifies a particular element; `class` groups elements for reusable styling.
- The `type` attribute is demonstrated for changing list markers.
- `<marquee>` and its attributes are legacy material; modern moving effects should be built with CSS.
- Regular practice is necessary. The instructor recommends practising the tags covered in the class before moving ahead.

---

## 20. Instructor's Attendance Points

The instructor states these two words for the class attendance form:

- **Point 1:** `Heading`
- **Point 2:** `List`

