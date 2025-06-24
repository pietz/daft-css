# Daft CSS

**An opinionated fork of PicoCSS with more components and a refined visual design**

## About This Fork

DaftCSS is a fork of the excellent [PicoCSS](https://github.com/picocss/pico) framework. Just like Pico, it's a minimal class-light semantic CSS framework that adds and changes a few things:

- **Revolutionary Color System**: Single CSS file with infinite color themes via 1 CSS variable (v1.0)
- **Adjusted Styling**: Is it more beautiful than Pico? No, it just take the design in a different more `shadcn/ui` direction.
- **Additional Components**: Extended component library beyond Pico's minimal set
- **Scale**: PicoCSS scales weirdly huge on larger viewports. Daft keeps it at a reasonable scale.
- **More Utilities**: Additional utilities and helpers while keeping the semantic, class-light philosophy

This project maintains the core philosophy of semantic HTML and minimal classes from PicoCSS, but adds a layer of enhanced functionality and different visual polish for developers who want more out-of-the-box.

## Changelog

### What's different from PicoCSS

- [x] **Default Only** - We removed `classless`, `fluid` and `conditional` options
- [x] **No Themes** - Instead of different CSS files, just change the `--daft-theme` base color
- [x] **Disabled Scaling** - Elements and fonts remain consistent sizes on bigger viewports
- [x] **Less Spacing** - Reduced padding and margins inside and between different elements
- [x] **Simplified Variables** - Reduced from 336+ color variables to ~30 core variables
- [x] **Visual Details** - Multiple small design, color and layout changes
- [x] **Inter Font** - As the default font family if it's installed

### Additions

- [x] **Element Sizing Utilities** - Added `.small` and `.large` classes for buttons, form elements and forms
- [x] **Grid Column Spanning** - `.span-2`, `.span-3`, and `.span-4` make grid items span multiple columns
- [x] **Badge Component** - `.badge` component with size and color variants `<span class="badge">Badge</span>`

## Quick Start

### Installation

Download Daft CSS and link `/css/daft.min.css` in the `<head>` of your website.

```html
<link rel="stylesheet" href="css/daft.min.css">
```

### Customizing Theme Colors

Change your entire theme with just one CSS variable:

```css
:root {
  --daft-theme: #0066cc; /* Any color you want! */
}
```

Or use any CSS color format:
- RGB: `rgb(255, 107, 107)`
- HSL: `hsl(0, 100%, 71%)`
- Named colors: `dodgerblue`

### Starter HTML template

```HTML
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="color-scheme" content="light dark">
    <link rel="stylesheet" href="css/daft.min.css">
    <title>Hello world!</title>
  </head>
  <body>
    <main class="container">
      <h1>Hello world!</h1>
    </main>
  </body>
</html>
```

## Credits

This project is built upon the excellent foundation of [PicoCSS](https://github.com/picocss/pico), created by [Lucas Larroche](https://github.com/lucaslarroche). We are grateful for their work in creating a minimal, semantic CSS framework that serves as the perfect starting point for this more opinionated variant.

## Contributing

We welcome contributions! Please read our contributing guidelines before submitting PRs.

## License

Like the original PicoCSS, this project is licensed under the [MIT License](https://github.com/picocss/pico/blob/master/LICENSE.md).
