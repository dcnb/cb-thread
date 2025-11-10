# Essay Monograph View

A beautiful, book-inspired reading interface for essay collections, with rich colors and elegant design touches.

## Overview

The Essay Monograph View transforms your `_essay` collection into a stunning digital book experience, featuring:

- **Book-inspired Design**: Warm browns, creams, and gold accents reminiscent of classic books
- **Decorative Elements**: Ornamental dividers, drop caps, corner flourishes
- **Table of Contents**: Sticky dropdown menu with numbered essay badges
- **Elegant Navigation**: Previous/next essay links with hover effects
- **Reading Progress**: "Essay X of Y" indicator
- **Responsive & Print-friendly**: Works beautifully on all devices

## Visual Design Features

### Color Palette
- **Primary**: Saddle brown (#8B4513) - classic book binding color
- **Secondary**: Tan (#D4A574) - aged paper
- **Accent**: Gold (#C9A961) - decorative touches
- **Background**: Cream (#FFF8F0) - paper-like warmth
- **Text**: Dark brown (#3E2723) - easy on the eyes

### Design Touches
- **Drop Cap**: Large decorative first letter
- **Corner Ornaments**: Golden corner brackets on essay article
- **Header Ornament**: Decorative ❦ symbol with lines
- **End Ornament**: ✦ ✦ ✦ symbols marking essay conclusion
- **Numbered Badges**: Circular essay numbers in TOC
- **Gradient Backgrounds**: Subtle paper-like gradients
- **Shadow Effects**: Elegant depth with brown-tinted shadows
- **Justified Text**: Book-style text alignment

## Setup

### Option 1: Individual Essay

Add `layout: essay-monograph` to any essay's frontmatter:

```yaml
---
title: Of Thumbs
byline: MICHEL DE MONTAIGNE
order: 1
layout: essay-monograph
---
```

### Option 2: All Essays (Default)

Change the default layout in `_config.yml`:

```yaml
defaults:
  -
    scope:
      path: ""
      type: "essay"
    values:
      layout: "essay-monograph"  # Changed from "essay-content"
      permalink: /essay/:slug:output_ext
```

### Configuration

In `_data/theme.yml`:

```yaml
##########
# ESSAY MONOGRAPH VIEW
essay-monograph-reading-progress: true # Show "Essay X of Y"
```

## Features in Detail

### Table of Contents Bar

Sticky bar at top (below navbar) with:
- **TOC Button**: Click to see all essays
- **Reading Progress**: Current essay number
- **Book Icon**: Visual indicator
- **Cream gradient background** with gold border

### Essay Display

The main content area features:
- **White paper card** on cream background
- **Golden corner brackets** (top-left, bottom-right)
- **Centered header** with:
  - Essay number (uppercase, letterspaced)
  - Large serif title
  - Italic byline
  - Ornamental divider (❦)

### Content Styling

- **Drop Cap**: First letter is 4.5rem, brown, floating left
- **Justified text**: Book-style alignment with hyphenation
- **Serif font**: Georgia for classic book feel
- **Generous spacing**: 1.9 line-height
- **Styled blockquotes**: Gold left border, cream gradient background
- **Bordered images**: 3px brown border with shadow
- **Decorative end**: Three diamond ornaments

### Navigation

Bottom navigation section with:
- **Previous Essay** (left): Arrow + title preview
- **Back to Top** (center): Scroll to top button
- **Next Essay** (right): Arrow + title preview
- **Hover effects**: Lift up with shadow
- **Keyboard support**: ← → arrow keys

## Customizing Colors

Edit the CSS variables in `_sass/_custom.scss`:

```scss
:root {
  --essay-primary: #8B4513;      /* Main brown */
  --essay-secondary: #D4A574;    /* Tan */
  --essay-accent: #C9A961;       /* Gold accents */
  --essay-dark: #3E2723;         /* Dark brown text */
  --essay-light: #FFF8F0;        /* Cream background */
  --essay-border: #D7CCC8;       /* Light brown borders */
}
```

### Alternative Color Schemes

**Academic Blue:**
```scss
:root {
  --essay-primary: #1B3A52;      /* Navy */
  --essay-secondary: #8FA3B0;    /* Steel blue */
  --essay-accent: #4A7BA7;       /* Blue accent */
  --essay-dark: #1A1A1A;
  --essay-light: #F5F9FC;
  --essay-border: #C5D3DD;
}
```

**Forest Green:**
```scss
:root {
  --essay-primary: #2C5F2D;      /* Forest green */
  --essay-secondary: #97BC62;    /* Light green */
  --essay-accent: #D4AF37;       /* Gold */
  --essay-dark: #1B3A1A;
  --essay-light: #F7F9F5;
  --essay-border: #C8D7C8;
}
```

**Burgundy Classic:**
```scss
:root {
  --essay-primary: #6B2C3D;      /* Burgundy */
  --essay-secondary: #C49FA0;    /* Dusty rose */
  --essay-accent: #D4A574;       /* Gold */
  --essay-dark: #2D1620;
  --essay-light: #FDF7F7;
  --essay-border: #D9C9CA;
}
```

## Typography Customization

The essay monograph uses Georgia serif font. To change:

```scss
.essay-monograph-content {
  font-family: 'Your Font', serif;
  font-size: 1.15rem;  /* Adjust reading size */
}

.essay-monograph-title {
  font-family: 'Your Font', serif;
}
```

### Font Pairing Suggestions

- **Classic**: Georgia (body) + Garamond (headings)
- **Modern Serif**: Merriweather + Playfair Display
- **Elegant**: Crimson Text + Cormorant Garamond
- **Traditional**: Baskerville + Caslon

## Layout Comparison

### essay-content (Original)
- Scrollama.js effects
- Full-width content
- Minimal styling
- Simple "Next" button
- Modern, clean look

### essay-monograph (New)
- Book-inspired design
- Boxed content with borders
- Rich colors and ornaments
- Full navigation with previews
- Classic, elegant look

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (responsive design)

## Accessibility Features

- **Semantic HTML**: Proper heading hierarchy
- **Keyboard Navigation**: Arrow keys work
- **High Contrast**: Dark text on light backgrounds
- **Focus Indicators**: Visible focus states
- **Screen Reader Friendly**: Proper ARIA labels

## Print Styles

When printing:
- TOC bar hidden
- Navigation hidden
- Shadows removed
- Optimized typography (12pt)
- Clean white background

## Tips for Best Results

1. **Essay Ordering**: Use `order` field to control sequence
2. **Consistent Bylines**: Use same author name format
3. **Good Content**: Works best with 3+ paragraphs per essay
4. **Images**: Add borders match the design
5. **Blockquotes**: Style automatically matches theme

## Troubleshooting

**TOC is empty?**
- Verify essays have `order` field
- Check `_config.yml` collections setup

**Wrong layout showing?**
- Clear `_site` directory
- Restart Jekyll server
- Check frontmatter syntax

**Styles not applied?**
- Restart server after CSS changes
- Clear browser cache
- Check for CSS errors in console

**Navigation not working?**
- Ensure multiple essays exist
- Check `order` fields are sequential
- Verify `_config.yml` sorting

## Example Essay Structure

```markdown
---
title: On Writing
byline: VIRGINIA WOOLF
order: 3
layout: essay-monograph
---

The act of writing begins with a single thought,
crystallizing into words upon the page...

{% include essay/feature/aside.html objectid="demo_001" %}

Writing is both an art and a craft...

{% include essay/feature/blockquote.html
   quote="Words, like nature, half reveal and half conceal the soul within."
   speaker="Tennyson" %}

## Section Heading

More content here...
```

## Integration with CollectionBuilder

The essay monograph view works alongside:
- **Regular essays**: Mix layouts in same collection
- **Essay features**: All `essay/feature/` includes work
- **Navigation**: Integrate with site menu
- **Search**: Essays remain searchable

## Future Enhancements

Possible additions:
- **Marginalia**: Side notes in margins
- **Bookmarks**: Save reading position
- **Font size toggle**: Reader accessibility
- **Dark mode**: Evening reading mode
- **Annotations**: Highlight and note features

## Credits

Inspired by:
- **Manifold** (University of Washington Press)
- **Pressbooks** (open source digital publishing)
- Classic book design traditions
- CollectionBuilder design principles
