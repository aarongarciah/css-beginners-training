# Inheritance

## What is Inheritance?

> "In CSS, inheritance controls what happens when no value is specified for a property on an element. Refer to any CSS property definition to see whether a specific property inherits by default ("Inherited: yes") or not ("Inherited: no")."
>
> https://developer.mozilla.org/en-US/docs/Web/CSS/Inheritance

## Inherited properties

- `font-size`, `color`, `text-align`, etc.
- Whe no value specified, the element gets the computed value of its parent.
- Only the root element (`html` or `:root`) gets the initial value for a given property.

## Non-inherited properties

- `border`, `background`, `display`, etc.
- If no value provided for a property, the property always gets the initial value.

## `inherit` keyword

- Works on inherit and non-inherited properties.
- Makes non-inherited properties inherited.

## What is the initial value of a property?

- The initial value of a property is the value defined in the specification.
- Not to be confused with the user-agent stylesheet value.
- The initial value can be forced in any property with the `initial` keyword.
- Rarely useful.

```css
div {
  display: inline-block;
}

div.initial {
  display: initial; /* display: inline */
}
```

## `all` property

- The `all` property sets all properties to a given value:
  - `initial`
  - `inherit`
  - `unset`: inherited properties to inherit; non-inherited properties to inicial.
  - `revert`: specifies behavior that depends on the stylesheet origin to which the declaration belongs.

**[Next chapter 👉](../05-progressive-enhancement)**
