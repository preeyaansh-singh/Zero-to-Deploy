# HTML – Class 04 Notes
## Multimedia, File Paths, Comments and Inline Frames

> Source: Class 04 Hindi transcript | Language: English | Level: Beginner
>
> These notes follow the lecture's teaching sequence. Technical clarifications and additional practice are explicitly marked. Example filenames and placeholder URLs are illustrative rather than exact copies of the instructor's files.

---

## 1. Recap of Class 03

| Tag / attribute | Purpose |
|---|---|
| `<h1>`–`<h6>` | Heading hierarchy |
| `<p>` | Paragraph |
| `<br>` | Line break |
| `<hr>` | Thematic break |
| `<pre>` | Preserves whitespace and line breaks |
| `<b>`, `<i>` | Bold and italic presentation |
| `<ol>`, `<ul>`, `<li>` | Ordered lists, unordered lists and list items |
| `type` | List marker style where supported |
| `id`, `class` | Identify and group elements |
| `<marquee>` | Legacy scrolling content; avoid in modern HTML |

The instructor emphasizes that practical knowledge matters more than memorizing notes: writing code, fixing bugs, improving websites and reading documentation are essential development skills.

## 2. Introduction to Multimedia Tags

**Multimedia** refers to content such as images, videos and audio that can be included in a web page alongside text. The instructor uses Wikipedia's India page, its flag and audio player to demonstrate why multimedia is useful.

| Content | HTML element | Example use |
|---|---|---|
| Image | `<img>` | Product photo, flag, illustration |
| Video | `<video>` | Product demonstration, background video |
| Audio | `<audio>` | Music, podcast, pronunciation |
| Embedded page | `<iframe>` | YouTube player, map, another HTML page |

Create a new file named `multimedia.html`, generate the HTML boilerplate in VS Code and open the page with Live Server.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multimedia Tags</title>
</head>
<body>
    <h1>Multimedia Tags</h1>
</body>
</html>
```

## 3. Image Tag — `<img>`

**Definition:** The image element displays an image on a web page.

```html
<img src="./media/doraemon.webp" alt="Doraemon">
```

The instructor demonstrates a downloaded Doraemon image and later an online Tom and Jerry image.

### 3.1 Image attributes

| Attribute | Meaning | Example |
|---|---|---|
| `src` | Source: location of the image | `src="./media/doraemon.webp"` |
| `alt` | Alternative text describing the image | `alt="Doraemon"` |
| `width` | Display width in CSS pixels | `width="200"` |
| `height` | Display height in CSS pixels | `height="150"` |

`<img>` is a **void element** (called a self-closing tag in the lecture). It has no separate closing tag and cannot contain child content.

```html
<!-- Correct -->
<img src="photo.jpg" alt="A mountain">
```

### 3.2 Adding a local image

A local image is an image stored in your project folder.

1. Download or obtain an image you have permission to use.
2. Copy it into the project's `media` folder.
3. In VS Code, you can right-click the folder and choose Reveal in File Explorer.
4. Write the image's relative path in `src`.
5. Add descriptive alternative text and save the HTML file.
6. Check the result in Live Server.

```text
HTML-Class/
├── index.html
├── list.html
├── multimedia.html
├── css/
├── js/
└── media/
    ├── doraemon.webp
    ├── bean.mp4
    └── soft-music.mp3
```

```html
<img src="./media/doraemon.webp" alt="Doraemon" width="300">
```

The browser resolves the path from the HTML document's location and requests the image file.

### 3.3 Setting image width

```html
<img src="./media/doraemon.webp" alt="Doraemon" width="200">
<img src="./media/doraemon.webp" alt="Doraemon" width="400">
```

The second image is displayed at twice the width of the first. If only the width is specified, the browser normally preserves the image's aspect ratio.

**Modern clarification:** Use a non-negative integer such as `width="200"` in HTML dimension attributes, rather than `width="200px"`. CSS uses units such as `width: 200px;`. Setting both dimensions incorrectly can distort an image.

## 4. File Paths and Directories

**Definition:** A file path tells the browser where a resource is located. A directory is a folder.

### 4.1 Relative paths

A relative path describes a location relative to the current document (assuming no custom base URL).

| Syntax | Meaning |
|---|---|
| `./` | Current directory |
| `../` | Parent directory (one level up) |
| `../../` | Two levels up |
| `media/photo.jpg` | Enter the media folder and find photo.jpg |

`./media/photo.jpg` and `media/photo.jpg` normally refer to the same resource.

### 4.2 Understanding paths visually

```text
project/
├── media/
│   └── photo.jpg
├── index.html
└── pages/
    └── about.html
```

From `index.html`:

```html
<img src="./media/photo.jpg" alt="Photo">
```

From `pages/about.html`:

```html
<img src="../media/photo.jpg" alt="Photo">
```

Logic for the second example:

- `../` moves from `pages/` to `project/`.
- `media/` enters the media folder.
- `photo.jpg` selects the file.

VS Code may suggest filenames after typing `./` or `../`, but you should understand the path without relying on autocomplete.

### 4.3 Absolute URLs

An absolute URL specifies a complete web address, including the protocol and domain.

```html
<img src="https://example.com/images/photo.jpg" alt="Photo">
```

This is an illustrative URL; replace it with an actual accessible image URL.

## 5. Alternative Text — `alt`

**Definition:** Alternative text provides a textual replacement for an image.

The instructor intentionally changes the image filename to demonstrate a broken image.

```html
<!-- Correct path -->
<img src="./media/doraemon.webp" alt="Doraemon">

<!-- Incorrect path -->
<img src="./media/doraemon-wrong.webp" alt="Doraemon">
```

When the image cannot load, the browser may display the alternative text instead.

Common causes of broken images:

- Incorrect filename or extension.
- Incorrect folder path.
- Missing file on the server.
- Network failure for a remote image.

### 5.1 Can alt contain another image URL?

The instructor answers this student question: **No.** The `alt` attribute contains text, not a fallback image source. If you put a URL there, it is treated as text.

### 5.2 Modern accessibility clarification

The lecture explains `alt` mainly as text displayed when an image fails. It is also important when the image loads successfully: screen readers can use it to describe the image to people who cannot see it.

```html
<img src="./media/flag.png" alt="Indian national flag">
```

For a purely decorative image that adds no information, use `alt=""`. For meaningful images, describe the relevant content rather than simply writing “image”.

## 6. Adding an Online Image Without Downloading

The instructor demonstrates this using a Tom and Jerry image.

1. Find an image you are permitted to use.
2. Right-click it and select Copy image address.
3. Paste the direct image URL into `src`.
4. Write appropriate `alt` text.

```html
<img src="https://example.com/tom-and-jerry.jpg"
     alt="Tom and Jerry" width="300">
```

| Local image | Online image |
|---|---|
| Stored in your project | Hosted on another server |
| Usually uses a relative path | Usually uses a complete URL |
| You control the project copy | External host controls availability |
| Must deploy the file with the site | Depends on remote access |

**Modern clarification:** Not every copied image address is permanent or publicly accessible. Some hosts block external embedding (hotlinking). An ordinary webpage URL is not necessarily a direct image URL. Check usage rights before using external media.

## 7. HTML Comments

**Definition:** A comment is a note in source code that is not displayed as ordinary page content.

### Syntax

```html
<!-- Your comment goes here -->
```

### 7.1 Why comments are useful

- Label sections of code.
- Explain the purpose of an element.
- Temporarily disable markup while debugging.

```html
<!-- Image section -->
<img src="./media/doraemon.webp" alt="Doraemon">

<!-- Temporarily disabled image
<img src="./media/another.jpg" alt="Another image">
-->
```

### 7.2 VS Code shortcut

`Ctrl + /` toggles comments for the selected line or selection in HTML on Windows. Press it again to uncomment.

**Technical clarification:** The lecture refers to a compiler reading HTML. More precisely, the browser parses HTML and builds a document structure; HTML is markup, not a conventional compiled programming language. Comments are not rendered as page content, but remain visible in the source. Never put passwords or private information inside HTML comments.

## 8. Video Tag — `<video>`

**Definition:** The video element embeds a video file that the browser can play.

Unlike `<img>`, `<video>` has opening and closing tags.

```html
<video src="./media/bean.mp4" width="300" controls></video>
```

### 8.1 Adding a local video

The instructor downloads a short video, renames it, copies it into `media/` and sets its path using `src`.

Without `controls`, the video may look like a still image because the default playback interface is not shown.

```html
<video src="./media/bean.mp4" width="300"></video>
```

Add `controls` to show the browser's native player.

### 8.2 Video attributes

| Attribute | Purpose |
|---|---|
| `src` | Video file location |
| `width`, `height` | Display dimensions |
| `controls` | Shows playback controls |
| `muted` | Starts with sound muted |
| `autoplay` | Requests automatic playback |
| `loop` | Restarts playback when the video ends |

### 8.3 Controls

```html
<video src="./media/bean.mp4" controls width="300"></video>
```

Depending on the browser, the player can provide play/pause, seeking, volume, fullscreen, playback speed, picture-in-picture and download options. The exact interface varies.

### 8.4 Muted and autoplay

```html
<video src="./media/bean.mp4" width="300" muted autoplay></video>
```

- `muted` starts the video without sound.
- `autoplay` asks the browser to play it automatically.
- The instructor combines these attributes to demonstrate a video that starts when the page opens.

### 8.5 Loop

```html
<video src="./media/bean.mp4" width="300" controls muted autoplay loop></video>
```

A short video restarts whenever it reaches its end. This can be useful for a silent decorative product demonstration.

**Modern clarification:** Autoplay is subject to browser policies, user preferences and device settings. Muted video is generally more likely to autoplay, but it is not guaranteed. `controls`, `muted`, `autoplay` and `loop` are boolean attributes: their presence enables them. Writing `autoplay="false"` does not disable autoplay; remove the attribute instead.

## 9. Embedding YouTube Videos

A normal YouTube watch URL points to a webpage, not a directly playable video file. The instructor uses YouTube's generated embed code instead.

### Steps demonstrated

1. Open the desired YouTube video.
2. Click Share.
3. Choose Embed (when available).
4. Copy the generated iframe code.
5. Paste it into the HTML body.
6. Save and test the page.

```html
<iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/VIDEO_ID"
    title="YouTube video player"
    allowfullscreen>
</iframe>
```

Replace `VIDEO_ID` with the actual video identifier or use the full code generated by YouTube.

The embedded player can provide play/pause, volume, quality, speed, fullscreen and other YouTube features depending on availability.

### 9.1 Changing dimensions

The instructor changes the width and height of the iframe. For a standard 16:9 video, keeping the proportions consistent avoids an awkward player shape.

| Width | Height (approximately 16:9) |
|---|---|
| 560 | 315 |
| 480 | 270 |
| 320 | 180 |

**Modern clarification:** An iframe is not a native video element. To request YouTube autoplay, the embed URL and player permissions must be configured appropriately; simply adding an HTML `autoplay` attribute to an iframe is not sufficient. Some videos disallow embedding altogether.

## 10. Online Videos and Other Embedded Media

The instructor tries a copied online media link inside `<video>`, but it does not display as expected. He then copies the provider's embed code and successfully displays an animated cat.

The important lesson is to distinguish a direct media resource from a webpage or embed link.

```html
<!-- Direct video resource: illustrative URL -->
<video src="https://example.com/clip.mp4" controls></video>
```

Use the provider's iframe embed code when the content is supplied as an embeddable player rather than a direct video file.

**Technical clarification:** GIF images normally belong in `<img>`, not `<video>`. Some providers offer MP4 versions of animations, which can be used in `<video>` if accessible and supported. Not every website provides or permits embedding.

## 11. Audio Tag — `<audio>`

**Definition:** The audio element embeds sound that can be played in a browser.

The instructor downloads an audio track, renames it to soft music and stores it in the `media` folder.

```html
<audio src="./media/soft-music.mp3" controls></audio>
```

### 11.1 Why controls are important

Without `controls`, an audio element generally has no visible default player.

```html
<audio src="./media/soft-music.mp3"></audio>
```

With `controls`, users can interact with the native audio player.

### 11.2 Audio attributes

| Attribute | Purpose |
|---|---|
| `src` | Audio file location |
| `controls` | Displays the audio player |
| `muted` | Starts with sound muted |
| `autoplay` | Requests automatic playback |
| `loop` | Repeats the audio |

```html
<audio src="./media/soft-music.mp3" controls muted></audio>
```

The instructor recommends avoiding autoplay and unnecessary looping for ordinary website audio, because unexpected sound can annoy visitors and cause them to leave.

**Modern clarification:** Audio autoplay is also restricted by browser policies. For user-initiated music or podcasts, `controls` alone is often the best default; starting muted is optional rather than mandatory.

## 12. Inline Frame — `<iframe>`

**Definition:** An iframe (inline frame) embeds another document inside the current HTML document.

```html
<iframe src="URL" width="500" height="300" title="Embedded page"></iframe>
```

Think of it as a window inside your web page through which another document can be displayed.

### 12.1 Attributes

| Attribute | Purpose |
|---|---|
| `src` | URL or path of the embedded document |
| `width` | Width of the frame |
| `height` | Height of the frame |
| `title` | Accessible description of the frame (supplementary best practice) |
| `allowfullscreen` | Permits fullscreen where supported |

### 12.2 Embedding an external website

The instructor demonstrates embedding Wikipedia's India page and experimenting with frame dimensions.

```html
<iframe src="https://en.wikipedia.org/wiki/India"
        width="800" height="900" title="Wikipedia article about India">
</iframe>
```

**Modern clarification:** This reproduces the lecture's example, but live embedding is not guaranteed. Websites can block framing using security policies such as `X-Frame-Options` or CSP `frame-ancestors`. An iframe does not bypass these restrictions.

### 12.3 Embedding a local HTML file

A student asks whether a local file can be used as the iframe source. The instructor demonstrates the `list.html` file from the previous class.

```html
<iframe src="./list.html" width="500" height="300" title="HTML lists practice"></iframe>
```

The existing list page appears inside the multimedia page. The two documents remain separate.

Avoid embedding the current page inside itself: this can cause recursive nesting or be blocked by the browser.

## 13. Embedding Google Maps

The instructor demonstrates a map embed generator with Jaipur as the location.

### Process demonstrated

1. Open a map embedding service.
2. Enter the location (Jaipur in the class).
3. Choose the map view: standard, satellite or hybrid, if available.
4. Choose zoom level and dimensions.
5. Select responsive sizing if offered.
6. Generate the embed code.
7. Copy and paste it into your HTML page.

**Supplementary recommended approach:** Google Maps itself also offers a Share → Embed a map option for supported locations. Copy the generated iframe code rather than guessing its URL.

```html
<!-- Replace MAP_EMBED_URL with the generated embed URL -->
<iframe src="MAP_EMBED_URL" width="600" height="450"
        title="Map of Jaipur" allowfullscreen></iframe>
```

The generated map may include additional attributes or wrapper elements. The instructor advises beginners to focus on identifying the iframe for now; styling will be covered later.

## 14. HTML Structure vs CSS Styling

A student asks why images appear side by side rather than one above the other. The instructor explains that visual layout and effects will be handled through CSS.

HTML defines the content; CSS controls presentation, including positioning, spacing, responsive sizing and hover effects.

**Supplementary preview (not taught in detail in this class):**

```css
img {
    display: block;
    max-width: 100%;
    height: auto;
}
```

This makes images block-level and helps them fit smaller screens. CSS can also create zoom effects on hover.

## 15. Why Video and Audio Have Closing Tags

The instructor briefly introduces the idea of multiple media sources and says it will be explained later.

| Element | Closing tag? |
|---|---|
| `<img>` | No — void element |
| `<video>` | Yes — `</video>` |
| `<audio>` | Yes — `</audio>` |
| `<iframe>` | Yes — `</iframe>` |

**Supplementary preview:** `<source>` allows multiple media formats to be offered to the browser. It is not covered in detail in this lecture.

```html
<video controls width="400">
    <source src="./media/clip.mp4" type="video/mp4">
    <source src="./media/clip.webm" type="video/webm">
    Your browser does not support the video element.
</video>
```

The browser can select a supported source. `<source>` is itself a void element.

## 16. Complete Class Practice File

Save as `multimedia.html`. Create the media folder and supply your own files with the matching filenames. Replace `VIDEO_ID` with a real YouTube video ID.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Class 04 Practice</title>
</head>
<body>
    <h1>Multimedia Gallery</h1>

    <!-- Image section -->
    <h2>Image</h2>
    <img src="./media/doraemon.webp" alt="Doraemon" width="300">

    <hr>

    <!-- Video section -->
    <h2>Video</h2>
    <video src="./media/bean.mp4" width="400" controls muted loop></video>

    <hr>

    <!-- Audio section -->
    <h2>Audio</h2>
    <audio src="./media/soft-music.mp3" controls></audio>

    <hr>

    <!-- Embedded YouTube video -->
    <h2>YouTube Video</h2>
    <iframe src="https://www.youtube.com/embed/VIDEO_ID"
            width="560" height="315" title="YouTube video"
            allowfullscreen></iframe>

    <!-- Local HTML page -->
    <h2>Previous Class</h2>
    <iframe src="./list.html" width="500" height="300"
            title="Previous class list examples"></iframe>
</body>
</html>
```

## 17. Common Beginner Mistakes and Debugging

| Problem | Likely cause / solution |
|---|---|
| Image does not appear | Check path, filename, extension and network |
| Alternative text displays | Check whether the image source loads |
| Video appears as a still image | Add `controls` and verify the file format |
| Audio player is invisible | Add `controls` |
| Video does not autoplay | Browser policy may block it; try muted playback |
| Video does not repeat | Add `loop` |
| YouTube watch link fails in video tag | Use YouTube's generated iframe embed code |
| External iframe is blank | Check URL and whether the provider allows embedding |
| Image appears stretched | Preserve the aspect ratio |
| Media is visible locally but not after deployment | Ensure files are uploaded and paths match case exactly |
| Comment appears on the page | Check `<!--` and `-->` syntax |
| Images are side by side | Use CSS to control layout |

## 18. Quick Revision Sheet

| Concept | Remember |
|---|---|
| `<img>` | Displays an image; no closing tag |
| `<video>` | Native video player |
| `<audio>` | Native audio player |
| `<iframe>` | Embeds another document |
| `src` | Resource location |
| `alt` | Textual alternative for an image |
| `./` | Current directory |
| `../` | Parent directory |
| `controls` | Shows media playback interface |
| `muted` | Starts without sound |
| `autoplay` | Requests automatic playback |
| `loop` | Repeats media |
| `width`, `height` | Display dimensions |
| `<!-- comment -->` | HTML comment syntax |
| `Ctrl + /` | Toggle comments in VS Code |
| Embed code | Provider-generated markup for displaying external content |

## 19. Practice Tasks (Additional, Not Instructor Assignments)

The instructor did not assign a formal task in this class. These exercises are added for revision.

1. Create a multimedia page with a local image and an online image.
2. Deliberately break an image path and observe the alternative text; then fix it.
3. Move an HTML file into a subfolder and update its image path using `../`.
4. Display the same image at widths of 200 and 400 pixels.
5. Add a local video with playback controls.
6. Experiment with muted autoplay and looping. Observe whether your browser permits autoplay.
7. Add an audio player that only plays when the user chooses to play it.
8. Embed a YouTube video using its generated embed code.
9. Embed a local `list.html` page using an iframe.
10. Embed a map of Jaipur using generated map embed code.
11. Label each section with an HTML comment.
12. Mini-project: build a personal multimedia gallery containing photos, a video, an audio track and a map, using only HTML for the initial version.

## 20. Self-Test Questions

1. What are the three multimedia tags taught in the class?
2. What does `src` stand for and what does it contain?
3. Why is `<img>` called a void element?
4. What is the purpose of `alt`?
5. Can `alt` display a replacement image from another URL?
6. What is the difference between a local image and an online image?
7. What is the difference between `./` and `../`?
8. How do you move two directories upward in a relative path?
9. Write the syntax of an HTML comment.
10. What is the VS Code shortcut for toggling comments?
11. Why might a video appear without playback controls?
12. What is the purpose of `muted`, `autoplay` and `loop`?
13. Why should ordinary website audio not autoplay unexpectedly?
14. Why does a normal YouTube watch URL not work as a direct video source?
15. What does iframe stand for?
16. How do you obtain YouTube embed code?
17. Can an iframe display a local HTML document?
18. How can you embed a Google Map?
19. Why might an external website refuse to appear inside an iframe?
20. Why do audio and video elements have closing tags?

## 21. Key Takeaways

- Multimedia makes web pages capable of displaying images, video and sound.
- Correct resource paths are essential for loading media.
- Alternative text is important for fallback and accessibility.
- Native media elements use attributes to control playback.
- External players and documents can be embedded using iframes when permitted.
- HTML comments help organize and debug code.
- CSS will handle advanced styling, responsive layout and animations.
- Practice the concepts rather than only memorizing tag names.

## 22. Instructor's Attendance Points

- **Point 1:** Image
- **Point 2:** Iframe

The instructor also states that classes run Monday to Friday, with weekends available for practice. No formal assignment was given in this lesson.
