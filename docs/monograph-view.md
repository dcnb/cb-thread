# Monograph View Feature

The Monograph View provides a clean, book-like reading interface for digital monographs and long-form content, inspired by platforms like Manifold and Pressbooks.

## Features

- **Clean Reading Interface**: Focused, distraction-free reading experience with optimal typography
- **Table of Contents Dropdown**: Easy navigation between chapters/sections
- **Chapter Navigation**: Previous/Next buttons at the bottom of each chapter with chapter titles
- **Keyboard Navigation**: Use arrow keys to move between chapters (← previous, → next)
- **Collapsible Metadata**: Chapter information available but out of the way
- **Responsive Design**: Works on all devices from desktop to mobile
- **Print-Friendly**: Optimized layout when printing chapters

## Setup Instructions

### 1. Configure Metadata

In your metadata CSV file (e.g., `_data/demo-metadata.csv`), add items with `display_template` set to `monograph`:

```csv
objectid,title,creator,date,description,display_template,chapter_number
chapter_001,Introduction,Author Name,2024-01-01,Opening chapter introducing the main themes,monograph,1
chapter_002,Historical Context,Author Name,2024-01-02,Background and historical context,monograph,2
chapter_003,Main Analysis,Author Name,2024-01-03,Core analysis and arguments,monograph,3
```

**Key Fields:**
- `display_template`: Set to `monograph` to use the monograph view
- `chapter_number` (optional): Display chapter numbers
- `date`: Used for sorting chapters (use dates to control order)
- `title`: Chapter title
- `creator`: Author name (optional)
- `description`: Chapter summary or lead paragraph (optional)

### 2. Configure Theme Settings

In `_data/theme.yml`, configure the monograph view options:

```yaml
##########
# MONOGRAPH VIEW
#
monograph-title: "Your Book Title Here" # appears in table of contents
monograph-content-menu: true # show/hide table of contents dropdown
monograph-chapter-nav: true # show/hide previous/next navigation
monograph-show-metadata: true # show/hide collapsible metadata section
```

### 3. Add Content

You can add content in several ways:

#### Option A: Use Page Content (Markdown)

Create a markdown file in `pages/` directory:

```markdown
---
title: Chapter One
objectid: chapter_001
display_template: monograph
chapter_number: 1
creator: Author Name
---

Your chapter content here in markdown format.

## Section Heading

More content...
```

#### Option B: Use Object Location

For PDF or image-based chapters, add the file path:

```csv
objectid,title,display_template,object_location,format
chapter_001,Introduction,monograph,/objects/chapter01.pdf,application/pdf
```

#### Option C: Use Transcripts

For items with full text in separate files:

```csv
objectid,title,display_template,object_transcript
chapter_001,Introduction,monograph,/objects/chapter01.txt
```

## Design Philosophy

The monograph view follows CollectionBuilder design principles:

1. **Simple and Clean**: Minimal visual distractions to focus on content
2. **Bootstrap-Based**: Uses Bootstrap 5 components for consistency
3. **Configurable**: Easy to enable/disable features via theme.yml
4. **Accessible**: Keyboard navigation and semantic HTML
5. **Responsive**: Works across all device sizes

## Customization

### Typography

Adjust the base font settings in `_data/theme.yml`:

```yaml
base-font-size: 1.3em
base-font-family: Georgia # or any web-safe font
```

### Colors

Customize colors using Bootstrap theme colors in `_data/config-theme-colors.csv`:

```csv
color_class,color
primary,#2C5F2D
secondary,#97BC62
```

### Advanced Styling

For more control, edit `_sass/_custom.scss` and modify the monograph-specific styles:

```scss
.monograph-content {
  font-size: 1.2rem; // adjust reading size
  max-width: 800px; // adjust content width
}

.monograph-title {
  color: #2C5F2D; // custom title color
}
```

## Examples

### Example 1: Academic Monograph

```yaml
# theme.yml
monograph-title: "Environmental History of the Pacific Northwest"
monograph-content-menu: true
monograph-chapter-nav: true
```

```csv
objectid,title,creator,date,chapter_number,display_template
intro,Introduction,Dr. Smith,2024-01-01,1,monograph
ch1,Early Settlement,Dr. Smith,2024-01-02,2,monograph
ch2,Industrial Era,Dr. Smith,2024-01-03,3,monograph
conclusion,Conclusion,Dr. Smith,2024-01-04,4,monograph
```

### Example 2: Digital Essay Collection

```yaml
# theme.yml
monograph-title: "Essays on Digital Culture"
monograph-content-menu: true
monograph-chapter-nav: true
monograph-show-metadata: true
```

## Tips and Best Practices

1. **Ordering**: Use the `date` field to control chapter order (items are sorted by date)
2. **Chapter Numbers**: Add `chapter_number` field for clearer navigation
3. **Descriptions**: Use the `description` field for chapter summaries (displays as lead paragraph)
4. **Mixed Content**: Combine with other display templates - only items with `display_template: monograph` appear in the reading interface
5. **Testing**: Use `bundle exec jekyll serve` to preview locally before deploying

## Keyboard Shortcuts

- `←` (Left Arrow): Previous chapter
- `→` (Right Arrow): Next chapter

## Browser Support

Works with all modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers

## Troubleshooting

**Chapters not appearing in order?**
- Check the `date` field - chapters are sorted by date

**Table of contents is empty?**
- Ensure items have `display_template: monograph` in metadata
- Check that metadata file is properly configured in `_config.yml`

**Styling not applied?**
- Restart Jekyll server after making changes to `_sass/_custom.scss`
- Clear browser cache

**Navigation buttons not working?**
- Verify that multiple chapters exist
- Check that `monograph-chapter-nav` is set to `true` in theme.yml

## Integration with Other Features

The monograph view works alongside standard CollectionBuilder features:

- **Search**: Monograph items are searchable via the main search
- **Browse**: Items appear in browse pages unless filtered
- **Timeline/Map**: If you add `latitude`, `longitude`, or `date` fields, items appear in visualizations
- **Data Export**: Monograph metadata can be exported via the data page

## Future Enhancements

Possible additions in future versions:
- Side notes and annotations
- Reading progress indicator
- Dark mode toggle
- Bookmark functionality
- Citation export for chapters
