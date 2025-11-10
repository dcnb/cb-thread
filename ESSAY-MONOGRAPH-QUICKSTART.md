# Essay Monograph View - Quick Start

Beautiful book-inspired reading interface for your essay collection with colors and design touches.

## What You Get

✨ **Book-Inspired Design** with warm browns, creams, and gold
📖 **Drop Caps** - Large decorative first letters
🎨 **Ornamental Dividers** - Classic book decorations
📑 **Table of Contents** - Sticky dropdown with numbered badges
⬅️➡️ **Smart Navigation** - Previous/next with essay previews
📊 **Reading Progress** - "Essay X of Y" indicator
⌨️ **Keyboard Support** - Arrow keys to navigate

## Quick Setup (2 Minutes)

### For Individual Essays

Add one line to essay frontmatter:

```yaml
---
title: Of Thumbs
byline: MICHEL DE MONTAIGNE
order: 1
layout: essay-monograph  # ← Add this
---
```

### For All Essays

Edit `_config.yml`:

```yaml
defaults:
  -
    scope:
      path: ""
      type: "essay"
    values:
      layout: "essay-monograph"  # ← Change from essay-content
      permalink: /essay/:slug:output_ext
```

That's it! 🎉

## Visual Features

### Colors
- **Saddle Brown** (#8B4513) - Main color
- **Gold** (#C9A961) - Accents
- **Cream** (#FFF8F0) - Backgrounds
- **White** - Content cards

### Design Elements
- Decorative corner brackets
- Header ornament (❦)
- Drop cap first letter
- End ornaments (✦ ✦ ✦)
- Circular essay numbers
- Book-like shadows

## Files Added

```
_layouts/essay-monograph.html          # New layout
_sass/_custom.scss                     # Styles added
_data/theme.yml                        # Config added
docs/essay-monograph-view.md           # Full docs
```

## Try It Out

```bash
bundle exec jekyll serve
```

Visit: `http://localhost:4000/essay/of-thumbs`

## Customizing Colors

Easy! Edit `_sass/_custom.scss`:

```scss
:root {
  --essay-primary: #8B4513;      /* Your color */
  --essay-accent: #C9A961;       /* Your accent */
  --essay-light: #FFF8F0;        /* Background */
}
```

### Pre-made Schemes

**Academic Blue**
```scss
--essay-primary: #1B3A52;
--essay-accent: #4A7BA7;
--essay-light: #F5F9FC;
```

**Forest Green**
```scss
--essay-primary: #2C5F2D;
--essay-accent: #D4AF37;
--essay-light: #F7F9F5;
```

**Burgundy**
```scss
--essay-primary: #6B2C3D;
--essay-accent: #D4A574;
--essay-light: #FDF7F7;
```

## Navigation

**On Screen:**
- Click "Table of Contents" button
- Click Previous/Next essay links
- Click "Back to Top" button

**Keyboard:**
- `←` Previous essay
- `→` Next essay

## Key Differences from Original

| Feature | essay-content | essay-monograph |
|---------|--------------|-----------------|
| Style | Modern, clean | Classic book |
| Colors | Default | Brown/gold/cream |
| TOC | No | Yes, dropdown |
| Navigation | Simple next | Full prev/next |
| First Letter | Normal | Drop cap |
| Ornaments | No | Yes |
| Background | Plain | Gradient |
| Borders | No | Decorative |

## Tips

1. **Ordering**: Use `order: 1, 2, 3` to control essay sequence
2. **Author**: Use `byline` field for consistent attribution
3. **Mix Layouts**: Some essays can use `essay-content`, others `essay-monograph`
4. **Content Length**: Works best with 3+ paragraphs

## Configuration

In `_data/theme.yml`:

```yaml
##########
# ESSAY MONOGRAPH VIEW
essay-monograph-reading-progress: true # Show "Essay X of Y"
```

## Troubleshooting

**No TOC?**
- Add `order` field to essays
- Restart Jekyll

**Wrong styles?**
- Clear `_site` folder
- Clear browser cache
- Restart server

**Navigation broken?**
- Check `order` fields exist
- Verify multiple essays

## What Works

- All `essay/feature/` includes
- Images and videos
- Asides and blockquotes
- Links and formatting
- Responsive design
- Print styles

## See It In Action

The current Montaigne essays work perfectly:
- Of Thumbs (order: 1)
- Of Smells (order: 2)
- Of Sleep (order: 4)
- Of a Monstrous Child (order: 5)

## Full Documentation

See `docs/essay-monograph-view.md` for:
- Detailed customization
- Alternative color schemes
- Font pairing options
- Accessibility features
- Print styling
- And more!

---

**Made with 📚 for CollectionBuilder**
