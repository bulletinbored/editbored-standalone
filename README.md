# editbored v1.0.0

A lightweight WYSIWYG Markdown editor with automatic link previews and embedded media support.

## Features

- **WYSIWYG Editing** - Write in Markdown and see formatted output in real-time
- **Automatic Link Previews** - Paste links and get rich preview cards for:
  - YouTube videos
  - Twitter/X posts
  - Facebook posts, videos, and Reels
  - Instagram posts
  - Direct image URLs
  - Generic URLs with favicons
- **Delete Button** - Remove any link preview with the X button
- **Improved Cursor Management** - Seamless cursor positioning after embed previews
- **@Mentions** - Type @ to see autocomplete suggestions for team members
- **Markdown Toolbar** - Quick formatting buttons for common elements
- **Keyboard Shortcuts** - Ctrl+B for bold, Ctrl+I for italic, Ctrl+S to save
- **Auto-save** - Content is automatically saved to local storage
- **Export** - Download your document as a .md file
- **Syntax Highlighting** - Code blocks with automatic language detection

## Getting Started

### Prerequisites

A modern web browser (Chrome, Firefox, Safari, Edge).

### Installation

Open `index.html` in your browser. No server or build process required.

```
open index.html
```

Or serve it with any static file server:

```bash
npx serve .
python -m http.server 8000
```

## Usage

### Writing Markdown

Type standard Markdown syntax in the editor. The content is rendered as formatted HTML as you type.

#### Text Formatting

| Markdown | Result |
|----------|--------|
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `~~strikethrough~~` | ~~strikethrough~~ |
| `` `code` `` | `code` |

#### Headings

```
# Heading 1
## Heading 2
### Heading 3
```

#### Lists

```
- Bullet list item
- Another item

1. Numbered item
2. Another numbered item

- [ ] Task to complete
- [x] Completed task
```

#### Links and Images

```
[Link text](https://example.com)

![Image description](https://example.com/image.jpg)
```

#### @Mentions

Type `@` followed by a name to mention team members. Suggestions will appear automatically.

```
Hey @mario, can you review this?
```

#### Code Blocks

```markdown
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```
```

#### Quotes

```
> "Simplicity is the ultimate sophistication."
> — Leonardo da Vinci
```

#### Tables

```
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
| Cell 3   | Cell 4   |
```

### Link Previews

Paste a URL on its own line to automatically generate a preview card:

- **YouTube**: `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
- **YouTube Shorts**: `https://youtu.be/abc123`
- **Twitter/X**: `https://twitter.com/user/status/1234567890`
- **Facebook**: `https://www.facebook.com/user/posts/123456789`
- **Facebook Reels**: `https://www.facebook.com/reel/123456789`
- **Instagram**: `https://www.instagram.com/p/abc123/`
- **Images**: `https://example.com/image.png`
- **Generic**: Any other URL becomes a card with favicon

Note: Instagram Reels, TikTok, Threads, and Vimeo links are treated as generic links and will display a simple card with favicon instead of an embedded player.

#### Deleting Previews

Each link preview has a remove button (X) in the top-right corner. Click it to delete the preview and continue writing after it.

### Toolbar Reference

| Button | Action | Shortcut |
|--------|--------|----------|
| **B** | Bold | Ctrl+B |
| *I* | Italic | Ctrl+I |
| S | Strikethrough | |
| • | Bullet List | - |
| 1. | Numbered List | 1. |
| 🔗 | Insert Link | |
| 🖼️ | Insert Image | |
| `<>` | Inline Code | |
| {} | Code Block | |
| ❝ | Quote | |
| @ | Mention | @ |

### Actions

- **New** - Clear the document and start fresh
- **Export .md** - Download the current document as a Markdown file

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl/Cmd + B | Bold |
| Ctrl/Cmd + I | Italic |
| Ctrl/Cmd + S | Save |
| Tab | Insert 4 spaces (for code blocks) |

## Architecture

### Core Components

- **Editor** - Contenteditable div with custom Markdown parsing
- **Link Preview System** - Detects URLs and generates embed cards with delete buttons
- **Mention System** - Handles @autocomplete with custom user list
- **Auto-save** - LocalStorage-based persistence
- **Syntax Highlighting** - Highlight.js integration

### File Structure

```
├── index.html           # Main HTML structure
├── css/
│   └── main.css         # All styling (editor, toolbar, previews)
├── js/
│   ├── app.js           # Main application logic
│   └── vendor/
│       └── mentions.js  # Mention/autocomplete system
├── LICENSE              # MIT License
└── README.md            # This file
```

### Technical Details

- Modular structure with separate HTML, CSS, and JavaScript files
- Uses browser native `contenteditable` for editing
- Marked.js for Markdown parsing
- Highlight.js for code syntax highlighting
- Platform-specific embed scripts (Twitter, Facebook, Instagram)
- No external dependencies (CDN only)

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## License

BSD Zero Clause License

Copyright (c) 2026 mlzog

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
