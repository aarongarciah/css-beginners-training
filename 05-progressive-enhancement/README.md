# Progressive Enhancement

> "Progressive enhancement is a design philosophy that centers around providing a baseline of essential content and functionality to as many users as possible, while at the same time going further and delivering the best possible experience only to users of the most modern browsers that can run all the required code."
>
> https://developer.mozilla.org/en-US/docs/Glossary/Progressive_Enhancement

## Progressive enhancement in CSS

_Progressive enhancement [is and ancient and big topic](https://alistapart.com/article/understandingprogressiveenhancement), but here we'll only cover the CSS part._

When the user-agent encounters a CSS rule that doesn't understand, it'll ignore it. That's one of the building blocks of CSS.

```css
body {
  bla: blabla; /* This declaration is ignored */
  background: red; /* This declaration is applied */
}
```

By simply using the cascade, we can provide fallbacks to older browsers. Let's see an example of using Grid Layout with a Flexbox fallback.

```css
.container {
  display: flex;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 10px;
  padding: 10px;
}

.container__item {
  flex: 0 0 33.333333%;
  border: 1px solid gold;
}
```

The previous code will be interpreted like this by a browser that doesn't support Grid Layout:

```css
.container {
  display: flex;
  padding: 10px;
}

.container__item {
  flex: 0 0 33.333333%;
  border: 1px solid gold;
}
```

Now, imagine that we want to change the `padding` on the `.container` element. Let's use `@supports`.

```css
.container {
  display: flex;
  padding: 10px;
}

.container__item {
  flex: 0 0 33.333333%;
  border: 1px solid gold;
}

@supports (display: grid) {
  .container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 10px;
    padding: 0;
  }
}
```

**[Next chapter 👉](../06-performance)**
