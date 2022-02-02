# Länsförsäkringar Fonts
This repo contains the correct font files to be used on our web platforms,
along with an implementations example for the correct font setup.

## Loading fonts
Please reference the latest community guidelines before implementing the font
files.

As of 2022, our method for limiting Flash of invisible text (FOIT) and
Flash of Unstyled Text (FOUT) relies on combining preloading and the
`font-display: swap` CSS property.

**Preloading**
```html
<head>
  <!-- ... -->
  <link rel="preload" href="/assets/intro-cond-regular.woff2" as="font" type="font/woff2" crossorigin>
  <link rel="preload" href="/assets/lf-rubrik.woff2" as="font" type="font/woff2" crossorigin>
</head>
```

**Font display**
```css
@font-face {
  font-family: 'LF Rubrik';
  src: url('lf-rubrik.woff2') format('woff2');
  font-display: swap;
  /* ... */
}
```

## Fallbacks
The woff2 files have slightly modified x-heights (letter height) that match
better with our fallback fonts. While this is a good way to limits layout
shifting during loading, and when fallback fonts are in use, it might cause
these fonts to vertically align differently from the typography used in Figma,
Sketch, or print.

**LF Rubrik** falls back to **Georgia**. **Intro Cond** falls back to
**Arial**. See the [complete font stacks](https://github.com/LF-digitala-kanaler/fonts/blob/master/index.css#L2) in the implemetation
example.
