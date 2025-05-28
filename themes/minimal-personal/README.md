# Minimal Personal Hugo Theme

A clean, minimalist Hugo theme designed for personal websites, portfolios, and blogs. Features a black and white color scheme with a focus on typography and content.

## Features

- **Minimalist Design**: Clean, typography-focused layout with black and white color scheme
- **Responsive**: Mobile-first design that works on all devices
- **Fast Performance**: Optimized CSS and minimal JavaScript
- **Multiple Content Types**: Support for blog posts, projects, music, and custom sections
- **SEO Optimized**: Proper meta tags, Open Graph, and Twitter Card support
- **Flexible**: Easy to customize and extend with new sections

## Sections Included

### Blog
- Full-featured blog with pagination
- Tags support
- Reading time estimation
- Post navigation (previous/next)
- RSS feed support

### Projects
- Project portfolio with image support
- Technology tags
- External links (demo, GitHub, website)
- Detailed project pages

### Music
- Music showcase with cover art
- Streaming platform links (Spotify, YouTube, SoundCloud)
- Artist and duration information
- Detailed track information

### About
- Personal information and bio
- Skills and technologies
- Contact information

## Installation

1. Clone or download this theme to your Hugo site's `themes` directory:
```bash
git clone https://github.com/yourusername/minimal-personal.git themes/minimal-personal
```

2. Update your `hugo.toml` configuration:
```toml
theme = 'minimal-personal'
```

## Configuration

### Basic Configuration

```toml
baseURL = 'https://yoursite.com/'
languageCode = 'en-us'
title = 'Your Name'
theme = 'minimal-personal'

# Pagination
paginate = 10
paginatePath = "page"

# Enable syntax highlighting
pygmentsUseClasses = true
pygmentsCodeFences = true

[params]
  description = "Your site description"
  author = "Your Name"
  email = "your-email@example.com"
  
  # Hero section
  [params.hero]
    title = "Your Name"
    subtitle = "Your tagline or description"
  
  # About preview on homepage
  about_preview = "Brief description for the about section preview"
  
  # Social links
  [[params.social]]
    name = "GitHub"
    url = "https://github.com/yourusername"
  
  [[params.social]]
    name = "LinkedIn"
    url = "https://linkedin.com/in/yourusername"
```

### Content Structure

Create the following content structure:

```
content/
├── about/
│   └── _index.md
├── blog/
│   ├── _index.md
│   └── your-posts.md
├── projects/
│   ├── _index.md
│   └── your-projects.md
└── music/
    ├── _index.md
    └── your-music.md
```

## Content Examples

### Blog Post

```yaml
---
title: "Your Post Title"
date: 2024-01-15
draft: false
author: "Your Name"
tags: ["tag1", "tag2"]
---

Your blog post content here...
```

### Project

```yaml
---
title: "Project Name"
date: 2024-01-10
draft: false
technologies: ["React", "Node.js", "MongoDB"]
github_url: "https://github.com/yourusername/project"
demo_url: "https://project-demo.com"
image: "/images/project-screenshot.jpg"
---

Project description and details...
```

### Music

```yaml
---
title: "Song Title"
date: 2024-01-05
draft: false
artist: "Your Name"
duration: "3:45"
spotify_url: "https://open.spotify.com/track/..."
youtube_url: "https://youtube.com/watch?v=..."
cover: "/images/album-cover.jpg"
---

Song description and details...
```

## Customization

### Colors

The theme uses CSS custom properties for easy color customization. Edit `static/css/style.css`:

```css
:root {
    --primary-color: #000000;
    --secondary-color: #ffffff;
    --text-color: #333333;
    --light-gray: #f8f8f8;
    --border-color: #e0e0e0;
    --hover-color: #666666;
}
```

### Adding New Sections

1. Create a new content directory: `content/newsection/`
2. Add an `_index.md` file for the section
3. Update the navigation in `layouts/partials/header.html`
4. Optionally create custom layouts in `layouts/newsection/`

### Custom Layouts

The theme supports custom layouts for different content types. Create files in:
- `layouts/blog/` for blog-specific layouts
- `layouts/projects/` for project-specific layouts
- `layouts/music/` for music-specific layouts

## Development

### File Structure

```
themes/minimal-personal/
├── layouts/
│   ├── _default/
│   │   ├── baseof.html
│   │   ├── list.html
│   │   └── single.html
│   ├── partials/
│   │   ├── header.html
│   │   └── footer.html
│   └── index.html
├── static/
│   └── css/
│       └── style.css
├── theme.toml
└── README.md
```

### Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This theme is released under the MIT License. See LICENSE file for details.

## Support

For questions, issues, or feature requests, please open an issue on the GitHub repository. 