# My Reset CSS

This is my custom reset CSS file. It’s similar to many of the classic resets with my own twist, feel free to use it as and when you wish.

## The Breakdown

First, we simply take all elements, including the pseudo-elements, and set them to border-box sizing. If you don’t know what border-box is, you should, it makes CSS sane. See [here for more](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing).

By the way, I've seen people use *::before to select pseudo-elements instead of just ::before , they function the exact same way so save yourself the character.

```css
*,
::before,
::after {
  box-sizing: border-box;
}
```

Almost all CSS Resets remove default margin and padding from all elements. I take this a step further and remove default border and outline. Again, this is my personal preference but I find having no border or outline preferable as it gives me a clean slate to style from.

```css
* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
}
```

Next is another classic reset whereby we remove the default list styling. The primary reason for this is to reduce all browsers to the same starting point.

```css
ol,
ul {
 list-style: none;
}
```

I don't use images, SVGs, videos or the like inline. Why are they inline elements? I’m not going to question W3C’s logic and of course you can use the abovementioned elements inline, but I almost never do. So I make them block elements, simple.

I also give the elements a max-width of 100% to prevent them from overflowing their containers.

I don't see this on many CSS Resets but it’s definitely been done before.

```css
img,
svg,
video,
canvas,
picture {
  display: block;
  max-width: 100%;
}
```

I hate when buttons’ font is different to that of the context they’re placed in. Of course, this happens by default. Why not let them, and other elements which behave that way, inherit their font styling?

```css
input,
button,
select,
textarea {
  font: inherit;
}
```

CSS automatically line-wraps where there isn’t enough space to fit all of a word on a line. The issue is that it takes a ‘soft-wrap’ approach, meaning at least in English it’ll only wrap on spaces and hyphens. If you have a single word which is longer (see wider) than its element then it’ll overflow.

This gets super messy as words either overlap other elements, get hidden or create unwanted x-axis scroll.

There’s not a flawless solution to this but break-word allows us to tell the browser to break part of a word onto the next line when it’s going to overflow otherwise. I’ll apply it to all common text elements.

```css
p,
h1,
h2,
h3,
h4,
h5,
h6,
span {
  overflow-wrap: break-word;
}
```

## I’m Probably Wrong
This isn't the right way to do this or the perfect CSS Reset.

It’s a CSS Reset that works for the way I design and style websites. I’ll probably change my mind next week and add something to it.

If you like it you can copy it from above or find it on GitHub.

If you hate it, tell me why at [frankpierce.me](https://www.frankpierce.me/) or email me at piercefrank10@gmail.com
