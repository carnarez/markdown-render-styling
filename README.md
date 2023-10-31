**Basic styling for my own projects documentation pages.** To be used with the
[template](https://github.com/carnarez/markdown-render/blob/master/markdown_render/template.html)
included in and rendered by the code from the
[`markdown-render`](https://github.com/carnarez/markdown-render) repo. The crude
light/dimmed/dark themes and syntax highlighting were [quite shamelessly] forked from
GitHub colour scheme for my own sense of consistency.

Structure of this little codebase:

* [`style-markup.css`](/style-markup.css) defines styles for native and custom HTML
  tags;
* [`style-struct.css`](/style-struct.css) defines styles for the generated pages
  sections;
* [`style-syntax.css`](/style-syntax.css) defines styles for syntax highlighting for
  code snippets;
* [`style.css`](/style.css) defines configuration variables and imports the content 
  above to be bundled.

See below for a more detailed description of the defined CSS.

# Configuration

The whole "design" of the minimalistic HTML pages requires a few colours, dimensions and
fonts:

* `background-color`: default background colour,
* `background-color-alt`: alternative background colour,
* `font-color`: default text colour,
* `link-color`: default clickable link color,
* `font-family`: default font for all text,
* `font-family-monospace`: monospace font (for code snippets),
* `font-size`: common font size used by most browsers,
* `line-height`: height of a line of text,
* `icon-size`: size of the icons,
* `article-width`: max width of the text container,
* `side-nav-width`: width of the side navigation bar,
* `top-nav-height`: height of the top navigation bar,
* `transition-duration`: duration for CSS transitions.

_These variables are defined in the [`style.css`](/style.css) file._

## Colours

| Variable name | Light theme (*default*) | Dimmed theme | Dark theme |
|:---|:---|:---|:---|
| `background-color` | [`#ffffff`](https://www.color-hex.com/color/ffffff) | [`#22272e`](https://www.color-hex.com/color/22272e) | [`#0d1117`](https://www.color-hex.com/color/0d1117) |
| `background-color-alt` | [`#f3f5f7`](https://www.color-hex.com/color/f3f5f7) | [`#2d333b`](https://www.color-hex.com/color/2d333b) | [`#161b22`](https://www.color-hex.com/color/161b22) |
| `font-color` | [`#24292e`](https://www.color-hex.com/color/24292e) | [`#adbac7`](https://www.color-hex.com/color/adbac7) | [`#c9d1d9`](https://www.color-hex.com/color/c9d1d9) |
| `link-color` | [`#0969da`](https://www.color-hex.com/color/0969da) | [`#539bf5`](https://www.color-hex.com/color/539bf5) | [`#539bf5`](https://www.color-hex.com/color/539bf5) | 

## Dimensions

| Variable name | Value |
|:---|:---|
| `font-size` | `16px` (equals to `1rem`) |
| `line-height` | `2rem` (dependent on the font size) |
| `icon-size` | `1.25rem` (dependent on the font size) | 
| `article-width` | `1000px` |
| `side-nav-width` | `40%` |
| `top-nav-height` | `5rem` (dependent on the font size) |

## Fonts

| Variable name | Value |
|:---|:---|
| `font-family` | [`Arial`](https://en.wikipedia.org/wiki/Arial), `sans-serif` |
| `font-family-monospace` | [`Courier New`](https://en.wikipedia.org/wiki/Courier_(typeface)), `monospace` |

The default font families are chosen from the list of
[web safe fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals#web_safe_fonts).

## Miscellaneous

| Variable name | Value |
|:---|:---|
| `transition-duration` | `0.5s` |

Note the duration parameter is currently applied on the following
[CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions):
`background-color`, `border-color`, `color`, `left`, `margin`, `opacity`,
`text-decoration-color`, `width`.

# Document sections

<details>
<summary>Full HTML code</summary>

Below the full [pseudo-]code of the `body` tag of the HTML template.

```html
<body>

  <nav id="scroller"></nav>

  <nav id="topbar">
    <div>
      <a class="sidebar"></a>
      <a class="search"></a>
      <span class="spacer"></span>
      <a class="logo"><img></a>
      <span class="spacer"></span>
      <a class="repo"></a>
      <a class="theme"></a>
    </div>
  </nav>

  <header>
    <img src="splash">
    <span class="title"></span>
    <span class="description"></span>
  </header>

  <main>

    <aside id="toc">toc</aside>

    <aside id="search">
      <header>
        <span class="search"></span>
        <input id="search-input">
        <span class="reset"></span>
      </header>
      <ul id="search-output"></ul>
    </aside>

    <article>
      <div></div>
      <span class="spacer"></span>
      <footer>
        <a id="prev"></a>
        <span class="spacer"></span>
        <a id="next"></a>
      </footer>
    </article>

  </main>

</body>
```

</details>

The high-level content of the document `body` is defined as follows:

```html
<body>
  <nav id="scroller"></nav>
  <nav id="topbar"></nav>
  <header></header>
  <main></main>
</body>
```

See below for a detailed description of the styles applied on the children sections.

_The styling code associated with the sections described below is defined in the
[`style-struct.css`](/style-struct.css) file._

## Scrolling progress indicator

```html
<nav id="scroller"></nav>
```

## Top navigation bar

```html
<nav id="topbar">
  <div>
    <a class="toc"></a>
    <a class="search"></a>
    <span class="spacer"></span>
    <a class="logo"><img></a>
    <span class="spacer"></span>
    <a class="repo"></a>
    <a class="theme"></a>
  </div>
</nav>
```

## Splash screen

```html
<header>
  <img>
  <span class="title"></span>
  <span class="subtitle"></span>
</header>
```

## Page content

The high-level content of the `main` section is defined as follows:

```html
<main>
  <aside id="toc"></aside>
  <aside id="search"></aside>
  <article></article>
</main>
```

See below for a detailed description of the styles applied on the children entities.

### Side navigation bars

#### Table of Contents

```html
<aside id="toc"></aside>
```

#### Search

```html
<aside id="search">
  <header>
    <span class="search"></span>
    <input id="search-input">
    <span class="reset"></span>
  </header>
  <ul id="search-output"></ul>
</aside>
```

### Main content

```html
<article>
  <div></div>
  <span class="spacer"></span>
  <footer>
    <a id="prev"></a>
    <span class="spacer"></span>
    <a id="next"></a>
  </footer>
</article>
```

#### Article content

#### Preceding and following articles

# Markup

_The styling code associated with HTML constructs (native and/or custom) is defined in
the [`style-markup.css`](/style-markup.css) file._

# CSS imports

The free [Solid](https://fontawesome.com/v6/icons?d=gallery&s=solid&m=free),
[Regular](https://fontawesome.com/v6/icons?d=gallery&s=regular&m=free) &
[Brands](https://fontawesome.com/v6/icons?d=gallery&p=2&s=solid&m=free)
[Font Awesome](https://fontawesome.com/) icon sets are made available.

The CSS necessary to render mathematical equations using the
[`KaTeX`](https://katex.org/) package is added to the mix, regardless of whether
equations can be found in the document.

Syntax highlighting is rendered client-side (via
[`highlight.js`](https://highlightjs.org/)) and requires a specific set of (18!) colours
to be defined. The latter can be fetched and aggregates from "official" themes (search
for the `github` keyword in the
[`srcstyles/` directory of the `highlight.js` repo](https://github.com/highlightjs/highlight.js/tree/main/srcstyles)).

<details>
<summary>Fetch GitHub colours</summary>

Below assumption is, all CSS definitions are in the same order in each of the files
scanned.

```shell

function extract_hex {
  grep -e 'background:' -e 'color:' $1 | sed 's/;$//g' | awk '{print$NF}'
}

function format_vars {
  extract_hex $1 | cat -n | sed 's/^[ ]*/  --color-/g;s/\t/: /g;s/$/;/g'
}

src=https://raw.githubusercontent.com/highlightjs/highlight.js/main/src/styles
wget -qq $src/github.css
wget -qq $src/github-dark.css
wget -qq $src/github-dark-dimmed.css

echo '/*
 * source themes downloaded from:
 * https://github.com/highlightjs/highlight.js/tree/main/src/styles
 * and merged to account for the theme switch
 */'
echo

echo -e ":root,\n.light {"
format_vars github.css
echo '}'
echo

echo '.dark {'
format_vars github-dark.css
echo '}'
echo

echo '.dimmed {'
format_vars github-dark-dimmed.css
echo '}'
echo

awk '/.hljs/,0' github-dark-dimmed.css > .tmp-theme

format_vars github-dark-dimmed.css | while read line; do
  var=$(awk '{print$1}' <<< $line | sed 's/://g')
  hex=$(awk '{print$2}' <<< $line | sed 's/;//g')
  sed -i "s/$hex/var\($var\)/" .tmp-theme
done
cat .tmp-theme

rm .tmp-theme github*.css
```

</details>

_External imports are defined in the [`style.css`](/style.css) file, while colours and
style mappings associated with syntax highlighting are defined in the
[`style-syntax.css`](/style-syntax.css) file._

# `@media` rules

The only `@media` rules applied on the defined styles are regarding the _side navigation
bars_ (by default taking the whole screen, but taking a percentage of the latter on
larger displays) and the _preceding/following articles_ links (on top of each other and
taking the whole width of the screen by default, but side-by-side and with a fixed
dimension for larger display).

_`@media` rules are defined in the [`style-struct.css`](/style-struct.css) file._
