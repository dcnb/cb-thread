# Monograph View - Quick Start Guide

A simple, clean digital monograph reading interface for CollectionBuilder.

## What You Get

✅ **Clean Reading Interface** - Focused, book-like layout
✅ **Table of Contents Dropdown** - Easy chapter navigation
✅ **Previous/Next Buttons** - Navigate between chapters
✅ **Keyboard Navigation** - Use arrow keys (← →)
✅ **Responsive Design** - Works on all devices
✅ **CollectionBuilder Design** - Simple, accessible, configurable

## Quick Setup (3 Steps)

### 1. Set Metadata
In your CSV, set `display_template` to `monograph`:

```csv
objectid,title,creator,date,display_template,chapter_number
ch01,Introduction,Author Name,2024-01-01,monograph,1
ch02,Chapter Two,Author Name,2024-01-02,monograph,2
```

### 2. Configure Theme
In `_data/theme.yml`:

```yaml
##########
# MONOGRAPH VIEW
monograph-title: "Your Book Title" # optional
monograph-content-menu: true
monograph-chapter-nav: true
monograph-show-metadata: true
```

### 3. Build & View
```bash
bundle exec jekyll serve
```

Visit: `http://localhost:4000/items/ch01.html`

## Features

### Table of Contents Dropdown
- Click "Table of Contents" button to see all chapters
- Current chapter is highlighted
- Shows chapter numbers if provided

### Chapter Navigation
- **Previous/Next buttons** at bottom with chapter titles
- **Keyboard shortcuts**: ← (previous) and → (next)
- **Smooth transitions** between chapters

### Reading Experience
- Optimized typography for long-form reading
- Centered content area (max-width for readability)
- Clean, distraction-free layout
- Print-friendly styles

### Optional Features
- Chapter numbers (add `chapter_number` field)
- Collapsible metadata section
- Support for images, PDFs, and text content
- Author attribution

## Example Metadata

See `_data/demo-monograph-metadata.csv` for a complete example with 6 chapters.

## Files Added

```
_layouts/item/monograph.html          # Main layout
_includes/monograph/content-menu.html # TOC dropdown
_sass/_custom.scss                    # Styles
docs/monograph-view.md                # Full documentation
```

## Customization

### Change Colors
Use Bootstrap theme colors in `_data/config-theme-colors.csv`:

```csv
color_class,color
primary,#2C5F2D
```

### Adjust Typography
In `_data/theme.yml`:

```yaml
base-font-size: 1.3em
base-font-family: Georgia
```

### Advanced Styling
Edit `_sass/_custom.scss` to customize:
- `.monograph-content` - Reading area styles
- `.monograph-title` - Chapter heading
- `.monograph-chapter-nav` - Navigation buttons

## Tips

1. **Order chapters**: Use `date` field to control order
2. **Add summaries**: Use `description` field for lead paragraphs
3. **Chapter numbers**: Optional but helpful for longer works
4. **Mix templates**: Use `monograph` only for chapters, other templates for other items
5. **Test locally**: Always preview with `bundle exec jekyll serve`

## Design Inspiration

Based on:
- Manifold (UW Press) - clean reading interface
- Pressbooks (open source) - chapter navigation
- CollectionBuilder principles - simple, configurable, accessible

## Need Help?

See full documentation: `docs/monograph-view.md`
