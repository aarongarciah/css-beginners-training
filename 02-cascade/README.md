# Cascade

## What is the Cascade?

> "The cascade is an algorithm that defines how to combine property values originating from different sources."
>
> https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade

## Possible origins

- User-agent stylesheets: browser default styles.
- Author stylesheets: website styles (`style=""`, `<style>`, `<link rel="stylesheet" href="">`).
- User stylesheets: loaded by the user with their browser. Not available in all browsers.

## Final declarations order

1. User agent declarations
2. User declarations
3. Author declarations
4. Author `!important` declarations
5. User `!important` declarations

> Open [index.html](index.html) to see and example.

**[Next chapter 👉](../03-specificity)**
