# HTML – Class 01 Notes

> **Course:** Full Stack Web Development with AI  
> **Class focus:** HTML introduction, VS Code setup, HTML boilerplate, basic tags, and running a page locally  

---

## 1. What This Class Covers

By the end of this session, you should understand:

- What HTML stands for and why websites use it.
- The difference between a website's structure and its design.
- What an IDE/code editor is and why the instructor uses Visual Studio Code (VS Code).
- How to create a project folder, files, and subfolders in VS Code.
- What VS Code extensions do and which two extensions were demonstrated.
- What an HTML boilerplate is and how to generate it with Emmet.
- The purpose of `<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, and `<body>`.
- The basic opening-tag/closing-tag syntax and the difference between a tag and an element.
- How to preview an HTML file using Live Server.

This is a foundation session. The instructor mentions images, links, tables, audio, and video as examples of content that can later be placed inside the body, but those tags are **not explained in detail in this class**.

## 2. What Is HTML?

**HTML stands for HyperText Markup Language.** It is the standard markup language used to define the structure and content of web pages.

A website is generally developed in layers:

1. **Structure – HTML:** defines what content exists on the page and how it is organised.
2. **Presentation – CSS:** controls the visual appearance, such as colours, spacing, layout, and typography.
3. **Behaviour – JavaScript:** adds interactions and dynamic behaviour.

Think of a webpage as a building:

- HTML is the basic structure and rooms.
- CSS is the paint, decoration, and arrangement.
- JavaScript is the electrical system and interactive features.

The instructor's key point is that **HTML creates the structure; CSS handles the design**.

### 2.1 Meaning of the Three Words

| Word | Meaning in this context |
|---|---|
| **HyperText** | Text or content that can contain links to other pages or resources. These links let users move from one page to another. |
| **Markup** | A way of marking or structuring content using tags so the browser can understand the role of different parts. |
| **Language** | A defined set of rules and syntax used to write that markup. |

**Example:** A website may have a Home page and an About page. A navigation link can take a visitor from Home to About. This linking capability is the “hypertext” part.

The markup part tells the browser which content is a heading, paragraph, image, or another type of element.

## 3. Where Do We Write HTML?

Code is written in a code editor or development environment and then opened in a browser.

### 3.1 IDE and Code Editor

**IDE** means **Integrated Development Environment**. An IDE is a software environment that brings together tools used to write and work with code.

The instructor mentions these tools:

- **Visual Studio Code (VS Code)** – the editor used for demonstrations in this course.
- **Sublime Text** – another code editor.
- **Notepad** – can be used to write basic HTML, but it does not provide the same coding assistance and development tools.

> **Useful clarification:** VS Code is commonly described as a source-code editor with many IDE-like features. The instructor uses the term IDE broadly in the lesson.

### 3.2 Why Use VS Code Instead of Notepad?

You can write HTML in a plain-text editor, but you would have to type and manage much more of the code manually. VS Code makes the work easier through features such as:

- Syntax highlighting.
- Code suggestions and completion.
- Emmet abbreviations for generating common HTML structures.
- Extensions that add useful features.
- A project Explorer for managing files and folders.
- Integration with tools used during development.

### 3.3 Installing VS Code

The installation process demonstrated in class is:

1. Open a browser and search for **VS Code download**.
2. Open the official Visual Studio Code download page.
3. Select the package for your operating system (Windows, macOS, or Linux).
4. Download and run the installer.
5. Accept the licence agreement.
6. Continue through the installation steps. The instructor also demonstrates selecting the option to create a desktop icon.
7. Finish the installation and open VS Code.

Download VS Code from its official website: <https://code.visualstudio.com/>

## 4. Understanding the VS Code Interface

When VS Code opens for the first time, you may see a Welcome screen with options such as creating a new file, opening a file, or opening a folder.

The instructor points out these main sections on the left-side Activity Bar:

| Section | Basic purpose |
|---|---|
| **Explorer** | View and manage the files and folders in the current project. |
| **Search** | Search for text across project files. |
| **Source Control** | Work with version-control tools such as Git. |
| **Run and Debug** | Run or debug supported code. |
| **Extensions** | Find and install extra functionality for VS Code. |

The class mainly uses **Explorer** and **Extensions**. Search, Source Control, and Run and Debug are pointed out but not taught in depth.

### 4.1 Open a Project Folder

The instructor recommends opening the main project folder in VS Code and creating the project files from the Explorer panel.

1. Open VS Code.
2. Choose **File → Open Folder** (or use the Open Folder option on the Welcome screen).
3. Create or select a folder for your project.
4. Open/select that folder in VS Code.
5. Use the Explorer panel to create files and subfolders inside it.

**Why open the project folder?** It keeps the files for one project together and lets VS Code display and manage the project structure in one place.

### 4.2 Create Files and Folders

In the Explorer panel, use the icons beside the project folder:

- **New File** – creates a file.
- **New Folder** – creates a subfolder.
- **Refresh** – refreshes the Explorer view.
- **Collapse Folders** – collapses the expanded folder tree.

To create something inside a particular folder, select that folder first and then choose New File or New Folder.

The instructor demonstrates creating folders such as `css`, `js`, and a text/document folder, then creating files inside them.

A simple project structure could look like this:

```text
my-first-project/
├── index.html
├── css/
│   └── style.css
└── js/
    └── script.js
```

This is a practical example of organising HTML, CSS, and JavaScript files. The exact folder names can vary from project to project.

**Explorer folder arrows:**

- A right-facing arrow means the folder is collapsed.
- A downward-facing arrow means the folder is expanded.

Click the arrow or folder name to expand or collapse it.

## 5. VS Code Extensions

An **extension** is an add-on that provides extra features in VS Code. Extensions can improve the editor's appearance or make a development task easier.

To install one:

1. Open the Extensions section in VS Code.
2. Search for the extension by name.
3. Select the correct result.
4. Click **Install**.

The instructor demonstrates two extensions.

### 5.1 Material Icon Theme

**Purpose:** Improves the appearance of the Explorer by showing recognisable icons for different file types and folders.

For example, HTML, CSS, and JavaScript files can display different icons. This makes the project tree easier to scan visually.

This extension is mainly a visual improvement; it does not change how HTML works.

### 5.2 Live Server

**Purpose:** Starts a local development server and opens the HTML page in a browser. When you save changes, the browser preview can refresh automatically.

This is useful because you do not have to repeatedly locate and reopen the HTML file in the browser after every edit.

The class uses the **Go Live** button in the VS Code status bar to start Live Server.

> **Important distinction:** “Live Server” does not mean that your website has been published on the public internet. It runs a local preview on your own computer. Other people cannot normally access it as a public website just because you clicked Go Live. Publishing a site requires hosting (and usually a domain or a hosting URL), which the instructor says will be covered later.

The demonstration shows an address similar to:

```text
http://127.0.0.1:5500/
```

- `127.0.0.1` is the loopback address for your own computer.
- `5500` is the port shown in the instructor's demonstration. Your port may differ.

## 6. HTML Tags: The Basic Syntax

HTML uses **tags** to mark different types of content.

A typical element with opening and closing tags looks like this:

```html
<p>Hello, everyone!</p>
```

Its parts are:

```html
<p>                  <!-- opening/start tag -->
  Hello, everyone!   <!-- content -->
</p>                 <!-- closing/end tag -->
```

### 6.1 Opening Tag

An opening tag begins an element. It contains the tag name inside angle brackets.

```html
<p>
```

### 6.2 Closing Tag

A closing tag marks the end of the element. It has a forward slash before the tag name.

```html
</p>
```

### 6.3 Content

The content is the text or other nested elements placed between the opening and closing tags.

```html
<p>This is a paragraph.</p>
```

Here, `This is a paragraph.` is the content.

### 6.4 Common Tag Names Mentioned in the Class

| Purpose | Tag name | Example |
|---|---|---|
| Paragraph | `p` | `<p>My paragraph</p>` |
| Main heading example | `h1` | `<h1>Hello, class!</h1>` |
| Document title | `title` | `<title>My First Page</title>` |
| Main HTML document | `html` | `<html> ... </html>` |
| Document information | `head` | `<head> ... </head>` |
| Visible page content | `body` | `<body> ... </body>` |

The instructor briefly uses an `h1` heading and a paragraph in the first-page demonstration. The detailed study of other HTML tags is left for later classes.

## 7. Tag vs Element

These two terms are related, but they do not mean exactly the same thing.

- A **tag** is the markup notation, such as `<p>` or `</p>`.
- An **element** is the complete HTML unit, usually including its opening tag, content, and closing tag.

Example:

```html
<p>Welcome to my website.</p>
```

- `<p>` – opening tag.
- `Welcome to my website.` – content.
- `</p>` – closing tag.
- The complete `<p> ... </p>` structure – paragraph element.

An element can also contain another element. This is called **nesting**.

```html
<p>Welcome to <strong>my website</strong>.</p>
```

Here, the `strong` element is nested inside the paragraph element. This example illustrates nesting; the class does not teach text-formatting tags in detail.

### 7.1 Keep Separate Elements Separate

When you create a new paragraph, close the previous paragraph and then start the next one.

```html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
```

Do not accidentally place the second paragraph inside the first one unless you intentionally want to create a nested structure. Keep opening and closing tags correctly paired and properly nested.

## 8. The HTML5 Boilerplate

A **boilerplate** is a basic starting structure that you can reuse when creating an HTML page. Instead of manually typing the entire document structure every time, you can generate it in VS Code using Emmet.

### 8.1 Generate the Boilerplate with Emmet

**Emmet** is a toolkit built into VS Code that understands abbreviations and expands them into code.

In an empty `.html` file:

1. Type `!` (an exclamation mark).
2. Choose the Emmet suggestion, or press the relevant completion key shown by VS Code (commonly `Tab` or `Enter`, depending on the editor settings).
3. VS Code inserts the basic HTML document structure.

The instructor also refers to Emmet documentation and its cheat sheet as places to learn more abbreviations.

### 8.2 Basic HTML5 Boilerplate

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Hello, class!</h1>
    <p>This is my first HTML page.</p>
</body>
</html>
```

### 8.3 Explanation of Each Part

#### `<!DOCTYPE html>`

- Declares that the document uses the modern HTML5 document type.
- It helps the browser interpret the page using standards mode.
- It is a declaration, not a normal HTML element with a closing tag.

#### `<html lang="en">`

- The `<html>` element is the **root element** of the page.
- The rest of the page's HTML content is placed inside it.
- `lang="en"` declares that the primary language of the document is English.

#### `<head>`

The `<head>` contains document information and resources that are not normally displayed as the main page content.

In this class, the instructor discusses:

- Character encoding information.
- Viewport settings for responsive layouts.
- The page title.
- Metadata that may be used by browsers and other services.

#### `<meta charset="UTF-8">`

- Declares the character encoding used by the document.
- UTF-8 supports a wide range of characters and symbols.
- It helps text display correctly across browsers and languages.

#### `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

This is important when building pages that adapt to different screen sizes.

- `name="viewport"` identifies the viewport settings.
- `width=device-width` makes the page layout viewport use the device's screen width.
- `initial-scale=1.0` sets the initial zoom level to 100% when the page loads.

Together, these settings help a page display appropriately on phones, tablets, and desktop screens. They do **not** by themselves make a website fully responsive; the layout and CSS must also be designed responsively.

#### `<title>My First Web Page</title>`

- Sets the title of the document.
- The title appears in the browser tab and may also be used by bookmarks and search results.
- It is different from a heading displayed inside the webpage.

For example:

```html
<title>My First Web Page</title>
```

This changes the browser-tab title, not the large heading inside the page.

#### `<body>`

- Contains the page content that the browser displays in the main webpage area.
- Headings, paragraphs, images, links, tables, audio, and video elements are examples of content placed in the body.
- In this class, the instructor demonstrates a heading and paragraph in the body.

### 8.4 Head vs Body – Quick Comparison

| `<head>` | `<body>` |
|---|---|
| Contains document metadata and information. | Contains the page's main content. |
| Includes the title and meta elements shown in this lesson. | Includes headings and paragraphs shown in this lesson. |
| Its contents are generally not displayed as the page's main content. | Its content is rendered in the browser's page area. |

**Remember:** The title in `<head>` appears in the browser tab. The heading or paragraph in `<body>` appears in the webpage itself.

## 9. Creating and Running Your First HTML Page

The instructor first demonstrates manually creating a small HTML file in Notepad, then moves to VS Code to make the workflow easier.

### 9.1 Create the File

1. Open your project folder in VS Code.
2. Create a new file named `index.html`.
3. Type `!` and generate the HTML boilerplate using Emmet.
4. Add a title inside `<title>`.
5. Add a heading and paragraph inside `<body>`.
6. Save the file.

### 9.2 Example: First Webpage

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Hello, class!</h1>
    <p>This is my first HTML page.</p>
    <p>Welcome to my website.</p>
</body>
</html>
```

### 9.3 Preview It with Live Server

1. Save `index.html`.
2. Make sure the Live Server extension is installed.
3. Click **Go Live** in the VS Code status bar.
4. Your default browser should open the page on a local address.
5. Edit the HTML and save again. Live Server should refresh the browser preview automatically.

### 9.4 How to Know Whether a File Is Saved

The instructor points out the unsaved-change indicator in the editor tab:

- A small dot on the file tab indicates that there are unsaved changes.
- After saving, the dot disappears and the normal close icon is shown.

Use **Ctrl + S** on Windows/Linux or **Cmd + S** on macOS to save your work.

## 10. Emmet and Lorem Ipsum

The instructor demonstrates using Emmet to generate placeholder text.

**Lorem Ipsum** is dummy text used as temporary content while designing or testing a layout. It is not meaningful website copy.

Examples in VS Code:

```text
lorem100
```

This can generate a block of placeholder text of approximately 100 words, depending on the Emmet abbreviation and editor behaviour.

```text
lorem20
```

This can generate a shorter placeholder block.

Use placeholder text while practising, then replace it with real content before publishing a website.

## 11. Local Preview vs Publishing a Website

This distinction is emphasised during the Live Server demonstration.

| Local preview | Published website |
|---|---|
| Runs on your own computer, commonly through `localhost` or `127.0.0.1`. | Is deployed to a hosting service and can be accessed through a public URL, subject to its access settings. |
| Useful while building and testing. | Used when you want other people to visit the website. |
| Starting Live Server does not publish your website. | Requires a deployment/hosting process. A domain may also be connected. |

Do not confuse the word “Live” in Live Server with publishing a website publicly.

## 12. Common Beginner Mistakes to Avoid

1. **Confusing HTML with CSS:** HTML defines structure; CSS controls presentation.
2. **Forgetting a closing tag:** For elements that use opening and closing tags, make sure both are present.
3. **Putting visible page content in the wrong place:** The main content demonstrated in this class belongs inside `<body>`.
4. **Confusing `<title>` with `<h1>`:** The title is shown in the browser tab; the heading is shown in the webpage.
5. **Not saving the file:** Save after making changes. Check the editor tab for the unsaved indicator.
6. **Opening only an individual file when you need the full project:** Open the project folder so you can manage all related files together.
7. **Expecting Live Server to publish the website:** It provides a local development preview, not public hosting.
8. **Assuming the viewport meta tag alone makes a page responsive:** It sets the viewport behaviour; responsive layout work is also needed.
9. **Confusing a tag with an element:** A tag is the markup notation; an element is the complete structure.

## 13. Practical Class Task

The instructor's practical task is to become comfortable with VS Code and practise the concepts covered in the session.

Complete the following:

- [ ] Install VS Code.
- [ ] Open a dedicated project folder in VS Code.
- [ ] Practise creating folders and files through the Explorer panel.
- [ ] Install **Material Icon Theme**.
- [ ] Install **Live Server**.
- [ ] Create an `index.html` file.
- [ ] Generate the HTML5 boilerplate using Emmet.
- [ ] Change the page title.
- [ ] Add one `<h1>` heading and at least two `<p>` paragraphs inside `<body>`.
- [ ] Save the file and run it using **Go Live**.
- [ ] Change some text, save again, and observe the browser preview refresh.
- [ ] Practise creating a `css` folder and a `js` folder.

### Small Practice Challenge

Create a simple personal introduction page containing:

- A suitable browser-tab title.
- One main heading with your name or a page title.
- Two paragraphs: one introducing the page and one describing what you are learning.

For now, focus on the document structure and correct tag syntax. Styling and more advanced tags can be added in later lessons.

## 14. Quick Revision Sheet

| Question | Answer |
|---|---|
| What is the full form of HTML? | HyperText Markup Language. |
| What is HTML used for? | Defining the structure and content of web pages. |
| Which technology handles design? | CSS. |
| What does IDE stand for? | Integrated Development Environment. |
| Which editor is used in this class? | Visual Studio Code (VS Code). |
| What is an extension? | An add-on that provides extra features in VS Code. |
| Which extension improves file icons? | Material Icon Theme. |
| Which extension runs a local browser preview? | Live Server. |
| What is a boilerplate? | A reusable starting structure for an HTML document. |
| What helps generate the boilerplate in VS Code? | Emmet; type `!` in an HTML file and accept the suggestion. |
| What does `<!DOCTYPE html>` do? | Declares the document as HTML5. |
| What is the root element? | `<html>`. |
| What belongs inside `<head>`? | Document metadata and the title. |
| What belongs inside `<body>`? | The main page content. |
| What does `<title>` control? | The browser-tab/document title. |
| What does `<h1>` represent in the example? | A main heading displayed in the page. |
| What does `<p>` represent? | A paragraph. |
| What is a closing tag? | A tag with `/` before its name, such as `</p>`. |
| What is an HTML element? | The complete structure made from its tag(s) and content. |
| Does Live Server publish a site publicly? | No. It creates a local development preview. |
| What is Lorem Ipsum? | Placeholder text used during layout and content practice. |

## 15. Practice Questions

Try answering these without looking at the notes.

1. Explain the difference between HTML and CSS.
2. What does “HyperText” mean in HTML?
3. Why is VS Code more convenient than a plain-text editor for this course?
4. What is the purpose of the Explorer panel?
5. What is the difference between a file and a folder in a project?
6. What do Material Icon Theme and Live Server do?
7. What is an HTML boilerplate?
8. Explain the purpose of `<!DOCTYPE html>`.
9. What is the role of the `<head>` element?
10. What is the role of the `<body>` element?
11. How is `<title>` different from `<h1>`?
12. What is the difference between a tag and an element?
13. Why should you save your HTML file before checking the browser preview?
14. What does the address `127.0.0.1` indicate in the class demonstration?
15. Why is running a page with Live Server different from publishing it online?

---

## 16. Class Logistics Mentioned in the Transcript

The instructor also gives these batch-related instructions during the session. They are administrative details, not HTML concepts:

- The attendance form is shared through the batch's WhatsApp community.
- The instructor says the Google Form contains two attendance fields: **Point 1: HTML** and **Point 2: VS** (VS Code).
- The instructor states that attendance should be above 80% to qualify for the course certificate.
- The instructor says students have seven days to mark attendance for a class.

Check the current batch announcements for the latest process, as administrative instructions can change.

---

### Final Takeaway

HTML provides the structure of a webpage. A good first step is to understand the HTML5 boilerplate, know what belongs in the head and body, and practise writing simple elements. Use VS Code, Emmet, and Live Server to make the learning workflow easier—but keep practising the HTML yourself so you understand the code that the editor generates.
