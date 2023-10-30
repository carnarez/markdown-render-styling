**Basic styling for my own projects documentation pages.** To be used with the
[template](https://github.com/carnarez/markdown-render/blob/master/markdown_render/template.html)
included in and rendered by the code from the
[`markdown-render`](https://github.com/carnarez/markdown-render) repo. The crude
light/dimmed/dark themes and syntax highlighting were [quite shamelessly] forked from
GitHub colour scheme for consistency.

See below for a detailed description of the defined CSS.

# Configuration

The whole "design" of the minimalistic HTML pages requires a few colours, dimensions and
fonts:

* `background-color`: default background colour,
* `background-color-alt`: alternative background colour,
* `font-color`: default text colour,
* `font-family`: default font for all text,
* `font-family-monospace`: monospace font (for code snippet),
* `font-size`: common font size used by most browsers,
* `icon-size`: size of the icons,
* `link-color`: default clickable link color,
* `max-width`: max width of the text container,
* `side-nav-width`: width of the side navigation bar,
* `top-nav-height`: height of the top navigation bar,
* `line-height`: height of a line of text,
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
| `icon-size` | `20px` | 
| `max-width` | `1000px` |
| `side-nav-width` | `40%` |
| `top-nav-height` | `5rem` (dependent on the font size) |

## Fonts

| Variable name | Value |
|:---|:---|
| `font-family` | [`Arial`](https://en.wikipedia.org/wiki/Arial), `sans-serif` |
| `font-family-monospace` | [`Courier New`](https://en.wikipedia.org/wiki/Courier_(typeface)), `monospace` |

The default font families are chosen from the list of
[web safe fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals#web_safe_fonts).

## Others

| Variable name | Value |
|:---|:---|
| `line-height` | `2rem` (dependent on the font size) |
| `transition-duration` | `0.5s` |

Note the duration parameter is currently applied on the following
[CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions):
`background-color`, `border-color`, `color`, `left`, `margin`, `opacity`,
`text-decoration-color`, `width`.

# Document sections

The content of the document `body` is defined as follows:

```html
<body>
  <nav id="scroller"></nav>
  <nav id="topbar"></nav>
  <header></header>
  <main></main>
</body>
```

See below for a detailed description of the styles applied on the children entities.

## Scrolling progress indicator

```html
<nav id="scroller"></nav>
```

_The styling code associated with this section is defined in the
[`style-navigation.css`](/style-navigation.css) file._

## Top navigation bar

```html
<nav id="topbar">
  <div class="buttons">
    <a class="button toc"></a>
    <a class="button search"></a>
    <span class="spacer"></span>
    <a class="logo"><img></a>
    <span class="spacer"></span>
    <a class="button repo"></a>
    <a class="button theme"></a>
  </div>
</nav>
```

_The styling code associated with this section is defined in the
[`style-navigation.css`](/style-navigation.css) file._

## Splash screen

```html
<header>
  <img>
  <span class="title"></span>
  <span class="subtitle"></span>
</header>
```

## Page content

The content of the `main` section is defined as follows:

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

_The styling code associated with this section is defined in the
[`style-navigation.css`](/style-navigation.css) file._

#### Search

```html
<aside id="search">
  <div class="input-with-buttons">
    <span class="button search"></span>
    <input id="search-input">
    <span class="button reset"></span>
  </div>
  <ul id="search-output"></ul>
</aside>
```

_The styling code associated with this section is defined in the
[`style-search.css`](/style-search.css) file._

### Text content

```html
<article>
  <div class="main-text"></div>
  <span class="spacer"></span>
  <div class="prev-next">
    <a id="prev"></a>
    <span class="spacer"></span>
    <a id="next"></a>
  </div>
</article>
```

#### Main text

_The styling code associated with this section is defined in the
[`style.css`](/style.css) file._

#### Preceding and following articles

_The styling code associated with this section is defined in the
[`style.css`](/style.css) file._

# HTML entities

_The styling code associated with HTML entities (native and/or custom) is defined in the
[`style-entities.css`](/style-entities.css) file._

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
to be defined. The [`github-colours.sh`](/github-colours.sh) script fetches and
aggregates said colours from official themes (search for the `github` keyword in the
[`src/styles/` directory of the `highlight.js` repo](https://github.com/highlightjs/highlight.js/tree/main/src/styles)).

_Colours and style mappings associated with syntax highlighting are defined in the
[`style-highlight.css`](/style-highlight.css) file._

# `@media` rules

The only `@media` rules applied on the defined styles are regarding the _side navigation
bars_ (by default taking the whole screen, but taking a percentage of the latter on
larger displays) and the _preceding/following articles_ links (on top of each other and
taking the whole width of the screen by default, but side-by-side and with a fixed
dimension for larger display).

_`@media` rules are defined in the [`style.css`](/style.css) file._

# Post-processing

Recommendations for post-processing include
[`Autoprefixer`](https://github.com/postcss/autoprefixer),
[`Stylelint`](https://github.com/stylelint/stylelint) and
[`cssnano`](https://github.com/cssnano/cssnano) (via their respective plugins for
[`PostCSS`](https://github.com/postcss/postcss)):

```shell
$ postcss style.css --replace --use autoprefixer  # add vendor prefixes
$ postcss style.css --replace --use stylelint  # lint and catch errors
$ postcss style.css --replace --use cssnano  # minify
```
