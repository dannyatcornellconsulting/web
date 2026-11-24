# Site template reference

The site is built on the **Dimension** template by HTML5 UP
(free for personal and commercial use, CCA 3.0 – <https://html5up.net/license>).

This file keeps the demo ("Elements") content that used to sit in `index.html`, plus
notes on how to add features back to the single page.

## How the page works

| File | Purpose |
| --- | --- |
| `index.html` | The whole site. Header (logo, name, tagline) + empty `#main` + footer. |
| `assets/css/main.css` | Original Dimension stylesheet (compiled from `assets/sass/`). Don't edit; override instead. |
| `assets/css/theme.css` | Cornell Consulting overrides: fonts, colours, glass panel, background image. **Edit this one.** |
| `assets/js/main.js` | Dimension behaviour: opens an `<article>` as a pop-up panel when its `#id` is in the URL. |
| `images/bg-cloud.jpg` | The blue neon cloud background (cropped copy of `images/bg.jpg`). |

`main.css` must load **before** `theme.css` so the overrides win.

Colours and fonts are CSS variables at the top of `theme.css`
(`--accent`, `--panel`, `--font`, etc.), so the look can be changed in one place.

## Adding a section (pop-up "article")

Dimension shows each `<article>` inside `<div id="main">` as an overlay panel
over the background. You open one by linking to its id.

1. Add the article inside `<div id="main">`:

   ```html
   <article id="services">
       <h2 class="major">Services</h2>
       <p>Text goes here.</p>
   </article>
   ```

   A close button is added automatically by `main.js`.

2. Add a nav to the header (after `<div class="content">…</div>`), one `<li>` per article:

   ```html
   <nav>
       <ul>
           <li><a href="#services">Services</a></li>
           <li><a href="#contact">Contact</a></li>
       </ul>
   </nav>
   ```

   The nav was removed because it only held placeholder `-` links. It is already styled in
   `theme.css`, so it will look right as soon as it's added back. 2–4 items works best.

3. Images inside an article:

   ```html
   <span class="image main"><img src="images/migration.jpg" alt="Describe the image" /></span>
   ```

Previous article drafts (Intro, Skill Highlights, Multi Cloud Connectivity, Migration,
CV, Contact) are in the local, git-ignored `index2.html` and in git history
(`git show 45a9697:index.html`).

### Contact form note

The template's form (below) has `action="#"`, so it doesn't send anything.
GitHub Pages is static hosting, so to make a form work you need a form service
(e.g. Formspree, Basin, or Microsoft Forms) and point `action` at it.
A plain `mailto:` link or a LinkedIn link is the simplest alternative.

---

## Elements (original demo content)

Copy any of these into an `<article>` to use them.

### Text

```html
<p>This is <b>bold</b> and this is <strong>strong</strong>. This is <i>italic</i> and this is <em>emphasized</em>.
This is <sup>superscript</sup> text and this is <sub>subscript</sub> text.
This is <u>underlined</u> and this is code: <code>for (;;) { ... }</code>. Finally, <a href="#">this is a link</a>.</p>
<hr />
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
<hr />
<h4>Blockquote</h4>
<blockquote>Fringilla nisl. Donec accumsan interdum nisi, quis tincidunt felis sagittis eget tempus euismod.</blockquote>
<h4>Preformatted</h4>
<pre><code>i = 0;

while (!deck.isInOrder()) {
    print 'Iteration ' + i;
    deck.shuffle();
    i++;
}

print 'It took ' + i + ' iterations to sort the deck.';</code></pre>
```

`<h2 class="major">` (or any heading with `class="major"`) adds the underline rule used for article titles.

### Lists

```html
<h4>Unordered</h4>
<ul>
    <li>Dolor pulvinar etiam.</li>
    <li>Sagittis adipiscing.</li>
    <li>Felis enim feugiat.</li>
</ul>

<h4>Alternate (divider lines)</h4>
<ul class="alt">
    <li>Dolor pulvinar etiam.</li>
    <li>Sagittis adipiscing.</li>
    <li>Felis enim feugiat.</li>
</ul>

<h4>Ordered</h4>
<ol>
    <li>Dolor pulvinar etiam.</li>
    <li>Etiam vel felis viverra.</li>
    <li>Felis enim feugiat.</li>
</ol>
```

### Icons (Font Awesome 5)

Brand icons use `icon brands fa-…`; solid icons use `icon solid fa-…`.
Browse names at <https://fontawesome.com/v5/search?m=free>.

```html
<ul class="icons">
    <li><a href="#" class="icon brands fa-linkedin-in"><span class="label">LinkedIn</span></a></li>
    <li><a href="#" class="icon brands fa-github"><span class="label">GitHub</span></a></li>
    <li><a href="#" class="icon brands fa-twitter"><span class="label">Twitter</span></a></li>
    <li><a href="#" class="icon brands fa-facebook-f"><span class="label">Facebook</span></a></li>
    <li><a href="#" class="icon brands fa-instagram"><span class="label">Instagram</span></a></li>
    <li><a href="mailto:you@example.com" class="icon solid fa-envelope"><span class="label">Email</span></a></li>
</ul>
```

### Buttons / actions

```html
<ul class="actions">
    <li><a href="#" class="button primary">Primary</a></li>
    <li><a href="#" class="button">Default</a></li>
</ul>

<!-- stacked (full width, one per line) -->
<ul class="actions stacked">
    <li><a href="#" class="button primary">Default</a></li>
    <li><a href="#" class="button">Default</a></li>
</ul>

<!-- small -->
<ul class="actions">
    <li><a href="#" class="button small">Small</a></li>
</ul>

<!-- with icon -->
<ul class="actions">
    <li><a href="images/cv.pdf" class="button primary icon solid fa-download">Download CV</a></li>
</ul>

<!-- disabled -->
<ul class="actions">
    <li><span class="button primary disabled">Disabled</span></li>
</ul>
```

### Table

Add `class="alt"` to the `<table>` for the boxed/striped variant.

```html
<div class="table-wrapper">
    <table>
        <thead>
            <tr><th>Name</th><th>Description</th><th>Price</th></tr>
        </thead>
        <tbody>
            <tr><td>Item One</td><td>Ante turpis integer aliquet porttitor.</td><td>29.99</td></tr>
            <tr><td>Item Two</td><td>Vis ac commodo adipiscing arcu aliquet.</td><td>19.99</td></tr>
        </tbody>
        <tfoot>
            <tr><td colspan="2"></td><td>49.98</td></tr>
        </tfoot>
    </table>
</div>
```

### Form

`field half` puts two fields side by side. See the contact form note above about `action`.

```html
<form method="post" action="#">
    <div class="fields">
        <div class="field half">
            <label for="demo-name">Name</label>
            <input type="text" name="demo-name" id="demo-name" placeholder="Jane Doe" />
        </div>
        <div class="field half">
            <label for="demo-email">Email</label>
            <input type="email" name="demo-email" id="demo-email" placeholder="jane@untitled.tld" />
        </div>
        <div class="field">
            <label for="demo-category">Category</label>
            <select name="demo-category" id="demo-category">
                <option value="">-</option>
                <option value="1">Manufacturing</option>
                <option value="2">Shipping</option>
            </select>
        </div>
        <div class="field half">
            <input type="radio" id="demo-priority-low" name="demo-priority" checked>
            <label for="demo-priority-low">Low</label>
        </div>
        <div class="field half">
            <input type="radio" id="demo-priority-high" name="demo-priority">
            <label for="demo-priority-high">High</label>
        </div>
        <div class="field half">
            <input type="checkbox" id="demo-copy" name="demo-copy">
            <label for="demo-copy">Email me a copy</label>
        </div>
        <div class="field">
            <label for="demo-message">Message</label>
            <textarea name="demo-message" id="demo-message" placeholder="Enter your message" rows="6"></textarea>
        </div>
    </div>
    <ul class="actions">
        <li><input type="submit" value="Send Message" class="primary" /></li>
        <li><input type="reset" value="Reset" /></li>
    </ul>
</form>
```
