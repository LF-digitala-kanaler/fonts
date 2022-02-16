# <img src="https://github.com/LF-digitala-kanaler/favicon/blob/master/icon.svg" width="24"> Länsförsäkringar Fonts

**Collecting the Länsförsäkringar web font files and the implementations best practices we rely on.**

## Loading fonts
Please check the latest community guidelines before implementing the font files. As of 2022, our method for limiting Flash of invisible text (FOIT) and Flash of Unstyled Text (FOUT) relies on combining preloading and the `font-display: swap` CSS property.

Preloading

```html
<head>
  <!-- ... -->
  <link rel="preload" href="/assets/lf-rubrik.woff2" as="font" type="font/woff2" crossorigin>
  <link rel="preload" href="/assets/intro-cond-bold.woff2" as="font" type="font/woff2" crossorigin>
  <link rel="preload" href="/assets/intro-cond-regular.woff2" as="font" type="font/woff2" crossorigin>
</head>
```

Font display

```css
@font-face {
  font-family: 'LF Rubrik';
  src: url('lf-rubrik.woff2') format('woff2');
  font-display: swap;
  /* ... */
}
```

See the full [CSS implemetation example](https://github.com/LF-digitala-kanaler/fonts/blob/master/index.css).

## Fallbacks

**LF Rubrik** falls back to **Georgia**. **Intro Cond** falls back to **Arial**.

See the [complete font stacks](https://github.com/LF-digitala-kanaler/fonts/blob/master/index.css#L2) in the implemetation example.
