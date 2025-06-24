# Daft CSS v1.0 Migration Guide

## Overview

Daft CSS v1.0 introduces a revolutionary simplified color system that replaces 19 separate theme files with a single CSS file and dynamic color calculations.

## Key Changes

### Before (v0.x)
- 19 separate CSS files (daft.amber.css, daft.blue.css, etc.)
- 336+ color-related CSS variables
- Fixed, predefined color themes
- ~500KB total CSS for all themes

### After (v1.0)
- 1 single CSS file (daft.css)
- ~30 core CSS variables
- Infinite color possibilities
- ~50KB total CSS

## Migration Steps

### 1. Update Your HTML

**Before:**
```html
<!-- Old way - specific theme file -->
<link rel="stylesheet" href="css/daft.blue.min.css">
```

**After:**
```html
<!-- New way - single file -->
<link rel="stylesheet" href="css/daft.min.css">
```

### 2. Customize Your Theme

Simply set one CSS variable with any valid CSS color:

```css
:root {
  --daft-theme: #2060df;  /* Hex */
}

/* Also works with: */
--daft-theme: rgb(32, 96, 223);      /* RGB */
--daft-theme: hsl(220, 85%, 55%);    /* HSL */
--daft-theme: tomato;                /* Named colors */
--daft-theme: #f09;                  /* Short hex */
```

### 3. Theme Color Equivalents

| Old Theme File | New Color Value |
|----------------|-----------------|
| daft.azure.css | `--daft-theme: #0172ad;` |
| daft.blue.css | `--daft-theme: #2060df;` |
| daft.green.css | `--daft-theme: #10b981;` |
| daft.orange.css | `--daft-theme: #f97316;` |
| daft.purple.css | `--daft-theme: #8b5cf6;` |
| daft.red.css | `--daft-theme: #ef4444;` |

### 4. Custom Overrides

If you were overriding specific color variables:

**Before:**
```css
:root {
  --daft-primary-hover: #1848a0;
  --daft-primary-focus: rgba(24, 72, 160, 0.25);
}
```

**After:**
These are now automatically calculated! If you need to override:
```css
:root {
  /* Adjust the calculation instead */
  --daft-primary-hover: color-mix(
    in srgb,
    var(--daft-theme),
    black 25%  /* More contrast */
  );
}
```

## Component Changes

### Simplified Variables

Many component-specific colors have been consolidated:

| Old Variables | New Variable |
|---------------|--------------|
| `--daft-h1-color`, `--daft-h2-color`, etc. | `--daft-text` |
| `--daft-card-border-color`, `--daft-table-border-color`, etc. | `--daft-border` |
| `--daft-code-background-color`, `--daft-card-sectioning-background-color` | `--daft-background-subtle` |

### Semantic Colors

Success, danger, and warning colors remain unchanged:
- `--daft-success: #10b981`
- `--daft-danger: #ef4444`
- `--daft-warning: #f59e0b`

## Browser Support

The new system uses modern CSS features:
- CSS Custom Properties (CSS Variables) - [97%+ support](https://caniuse.com/css-variables)
- `color-mix()` - [90%+ support](https://caniuse.com/mdn-css_types_color_color-mix)
- HSL color functions - [99%+ support](https://caniuse.com/css3-colors)

For older browsers, the default blue theme will be used as a fallback.

## Benefits of Upgrading

1. **Smaller bundle**: 90% reduction in CSS size
2. **Better performance**: Single file, fewer network requests
3. **Infinite customization**: Any color, not just 19 presets
4. **Easier maintenance**: Simpler codebase
5. **Future-proof**: Built on modern CSS standards

## Need Help?

- Check out `example-simplified.html` for a live demo
- See the [README](README.md) for more examples
- Open an issue if you encounter problems

## Rollback Plan

If you need to temporarily rollback:
1. Keep using the old CSS files (they still work)
2. The old files are archived in the `v0.x` branch
3. You can gradually migrate component by component

---

Thank you for using Daft CSS! We're confident this simplified system will make your development experience much better.