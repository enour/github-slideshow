# GitHub Slideshow Repository Explanation

## Project Overview

The **enour/github-slideshow** repository is a Jekyll-based slideshow presentation system designed specifically for GitHub Learning Lab courses. It combines the power of Jekyll static site generation with reveal.js v3.9.2 to create interactive, web-based presentations for teaching Git and GitHub concepts.

### Key Features
- **Educational Focus**: Built for GitHub Learning Lab to teach Git and GitHub workflows
- **Interactive Presentations**: Uses reveal.js for smooth, professional slideshow experiences
- **GitHub Pages Ready**: Configured for seamless deployment on GitHub Pages
- **Collaborative Editing**: Integrated with Eraser tool for real-time collaboration
- **Markdown-Based**: Simple slide creation using Markdown in Jekyll posts

## Technical Architecture

### Core Technologies
- **Jekyll**: Static site generator for processing content and templates
- **reveal.js v3.9.2**: JavaScript presentation framework for interactive slideshows
- **Ruby/Bundler**: Dependency management for Jekyll and related gems
- **GitHub Pages**: Hosting and deployment platform
- **Node.js/npm**: Package management for reveal.js dependency

### Architecture Flow
1. **Content Creation**: Slides written as Jekyll posts in Markdown
2. **Processing**: Jekyll processes posts and applies layouts/templates
3. **Integration**: reveal.js handles presentation rendering and interactions
4. **Deployment**: GitHub Pages serves the generated static site

## File Structure Breakdown

### Configuration Files
- **`_config.yml`**: Main Jekyll configuration with reveal.js settings
  - Site metadata (title: "github-slideshow", author: "GitHubTeacher")
  - reveal.js configuration (transitions, themes, controls)
  - Jekyll plugins and build settings
- **`Gemfile`**: Ruby dependencies including `github-pages` gem
- **`package-lock.json`**: Locks reveal.js v3.9.2 dependency

### Content Structure
- **`_posts/0000-01-01-intro.md`**: Sample slide content with Eraser integration
- **`index.html`**: Main presentation entry point that loops through posts
- **`my new github slideshow.md`**: Additional sample content
- **`folder/a file in a new folder.md`**: Example of organized content

### Layout System
- **`_layouts/presentation.html`**: Main presentation template with reveal.js structure
- **`_layouts/slide.html`**: Individual slide layout template
- **`_layouts/print.html`**: Print-friendly layout option

### Include Components
- **`_includes/head.html`**: HTML head with reveal.js CSS imports
- **`_includes/script.html`**: JavaScript initialization for reveal.js
- **`_includes/slide.html`**: Slide section template with dynamic attributes

### Development Scripts
- **`script/setup`**: Dependency installation and environment setup
- **`script/server`**: Local development server launcher
- **`script/cibuild`**: Continuous integration build script
- **`script/stage`**: Staging deployment utilities

## reveal.js Integration Details

### CSS Loading
```html
<!-- From _includes/head.html -->
<link rel="stylesheet" href="/node_modules/reveal.js/css/reveal.css">
<link rel="stylesheet" href="/node_modules/reveal.js/css/theme/moon.css">
<link rel="stylesheet" href="/node_modules/reveal.js/lib/css/monokai.css">
```

### JavaScript Initialization
```javascript
// From _includes/script.html
Reveal.initialize({
    hash: true,
    dependencies: [
        { src: 'node_modules/reveal.js/plugin/markdown/marked.js' },
        { src: 'node_modules/reveal.js/plugin/markdown/markdown.js' },
        { src: 'node_modules/reveal.js/plugin/highlight/highlight.js' },
        { src: 'node_modules/reveal.js/plugin/notes/notes.js', async: true }
    ]
});
```

### Configuration Options
The `_config.yml` file contains extensive reveal.js customization:
- **Controls**: Navigation controls disabled
- **Progress**: Progress bar enabled
- **History**: Browser history integration
- **Transitions**: Linear transition effects
- **Themes**: Moon theme with Solarized dark variant
- **Slide Numbers**: Format "c/t" (current/total)

## Educational Features

### GitHub Learning Lab Integration
- Designed as a template for Git/GitHub education
- Sample content demonstrates version control concepts
- Interactive elements encourage hands-on learning
- Compatible with GitHub's educational workflows

### Eraser Collaborative Editing
- **Integration Links**: Direct links to Eraser workspaces in slide content
- **Real-time Collaboration**: Multiple users can edit presentations simultaneously
- **Visual Elements**: Support for diagrams and images via Eraser
- **GitHub Sync**: Changes sync back to GitHub repository

### Sample Content Structure
- Welcome slides with navigation instructions
- Educational messaging about open source (reveal.js)
- Interactive elements and media integration
- Demonstration of collaborative editing workflows

## Development Workflow

### Initial Setup
```bash
# Run the setup script
./script/setup
```
This script:
- Installs Homebrew dependencies (macOS)
- Sets up Ruby environment with rbenv
- Installs gem dependencies via Bundler
- Initializes git submodules

### Local Development
```bash
# Start local development server
./script/server
```
Equivalent to: `bundle exec jekyll serve`

### Dependency Management
- **Ruby Dependencies**: Managed via `Gemfile` and Bundler
  - `github-pages` gem (>= 207) for GitHub Pages compatibility
  - `html-proofer` for link validation
  - `tzinfo-data` for Windows compatibility
- **JavaScript Dependencies**: reveal.js managed via npm/package-lock.json

### GitHub Pages Deployment
- **Automatic Deployment**: Pushes to main branch trigger GitHub Pages builds
- **Jekyll Processing**: GitHub Pages runs Jekyll build automatically
- **Static Assets**: reveal.js files served from node_modules directory
- **Custom Domain**: Configurable via GitHub Pages settings

### Build Process
1. Jekyll processes Markdown posts into HTML
2. Layouts wrap content with reveal.js structure
3. Includes add CSS/JS dependencies
4. Static files copied to `_site` directory
5. GitHub Pages serves generated site

## Key Configuration Highlights

### Jekyll Settings
```yaml
# From _config.yml
title: github-slideshow
author: GitHubTeacher
description: A fun activity for learning Git and GitHub.
highlighter: rouge
markdown: kramdown
plugins:
  - jemoji
```

### reveal.js Customization
```yaml
# From _config.yml reveal section
reveal:
  controls: false
  progress: true
  history: true
  center: true
  transition: linear
  width: 1000
  height: 920
```

## Licensing and Attribution

### MIT License
- **Copyright**: (C) 2016 Thomas Friese
- **License Type**: MIT License (permissive open source)
- **Usage Rights**: Free to use, modify, and distribute
- **Attribution**: Original author credit maintained

### Dependencies
- **reveal.js**: Also MIT licensed by Hakim El Hattab
- **Jekyll**: MIT licensed by Tom Preston-Werner
- **GitHub Pages**: Free hosting for public repositories

## Getting Started

### Prerequisites
- Ruby (managed via rbenv recommended)
- Bundler gem
- Git
- Node.js/npm (for reveal.js)

### Quick Start
1. **Clone Repository**: `git clone https://github.com/enour/github-slideshow.git`
2. **Setup Environment**: `./script/setup`
3. **Start Server**: `./script/server`
4. **View Presentation**: Open `http://localhost:4000`
5. **Edit Content**: Modify files in `_posts/` directory
6. **Deploy**: Push changes to GitHub for automatic Pages deployment

### Creating New Slides
1. Create new Markdown file in `_posts/` directory
2. Use Jekyll front matter for slide configuration
3. Write slide content in Markdown
4. Jekyll automatically includes in presentation sequence

This repository serves as an excellent example of combining modern web technologies for educational purposes, demonstrating how Jekyll and reveal.js can create engaging, interactive learning experiences for Git and GitHub education.
