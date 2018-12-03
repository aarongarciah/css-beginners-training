# Performance

- Avoid `@import` statements. The stylesheets are downloaded in series blocking and are render blocking.
  ```css
  @import url('fonts.css');
  @import url('about.css');
  ```
- Inline critical CSS to avoid blocking the render of the page.
  ```html
  <html>
    <head>
      <style>
        /* Critial CSS goes here*/
      </style>
    </head>
    <body>
      ...
    </body>
  </html>
  ```
- Tell the browser to load CSS as fast as possible.
  ```html
  <link rel="preload" as="style" href="style.css" onload="this.rel='stylesheet'" />
  <noscript><link rel="stylesheet" href="style.css"/></noscript>
  ```
- Put print styles in another file with the correct media.
  ```html
  <link href="print.css" rel="stylesheet" media="print" />
  ```
- Fonts only are downloaded only when they fulfill the `@font-face` "conditions". [Source](https://css-tricks.com/whats-deal-declaring-font-properties-font-face/).

  ```css
  @font-face {
    font-family: 'My Font';
    /* Only download and use if element matches this font-weight */
    font-weight: 700;
    /* Only download and use if element matches this font-style */
    font-style: italic;
    src: url(my-bold-and-italic-font.woff2) format('woff2');

    /* Only download and use if these characters are used */
    unicode-range: U+0460-052F, U+20B4, U+2DE0-2DFF, U+A640-A69F;
  }

  p {
    font-family: 'My font'; /* Doesn't match */
  }

  strong {
    font-family: 'My font'; /* Does match */
    font-weight: 700;
    font-style: italic;
  }
  ```

- Don't overuse base 64 assets inside CSS files. It makes non-blocking bytes into blocking ones.
