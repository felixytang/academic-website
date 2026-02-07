# Academic Website Customization Guide

**Live Site:** https://felixytang.github.io/academic-website/

---

## Table of Contents
1. [Quick Start](#quick-start)
2. [File Structure](#file-structure)
3. [Adding New Publications](#adding-new-publications)
4. [Updating Projects](#updating-projects)
5. [Adding Talks/Presentations](#adding-talkspresentations)
6. [Updating Your Profile](#updating-your-profile)
7. [Customizing Appearance](#customizing-appearance)
8. [Local Development](#local-development)
9. [Deployment](#deployment)

---

## Quick Start

### Make a Quick Edit
1. Edit files in your local `academic-website` folder
2. Run these commands:
   ```bash
   git add -A
   git commit -m "Your update message"
   git push origin master:main
   ```
3. Wait 1-2 minutes for GitHub to rebuild the site

---

## File Structure

```
academic-website/
├── _config.yml          # Main site configuration
├── _data/
│   ├── cv.json          # CV data (education, experience, skills)
│   └── navigation.yml   # Navigation menu items
├── _pages/
│   ├── about.md         # Homepage content
│   ├── publications.html
│   ├── projects.html
│   └── cv.md
├── _publications/       # Individual publication files
├── _portfolio/          # Research project files
├── _talks/              # Conference talks
├── _teaching/           # Teaching experience
├── images/              # Site images
│   └── projects/        # Project images
├── files/               # PDFs (CV, papers)
│   └── resume.pdf
└── assets/css/main.scss # Custom styles
```

---

## Adding New Publications

### Step 1: Create a new file
Create `_publications/YYYY-MM-DD-short-title.md`:

```markdown
---
title: "Your Paper Title"
collection: publications
category: manuscripts
permalink: /publication/YYYY-short-title
excerpt: 'Brief description of the paper.'
date: YYYY-MM-DD
venue: 'Journal Name'
paperurl: 'https://doi.org/...'
citation: 'Author1, Author2. (YYYY). "Title." <i>Journal</i>.'
---
Optional longer description of the paper.
```

### Step 2: Commit and push
```bash
git add _publications/
git commit -m "Add new publication: Paper Title"
git push origin master:main
```

---

## Updating Projects

### Edit existing project
Edit files in `_portfolio/`:
- `project-1-arctic.md`
- `project-2-scs.md`
- `project-3-coastal.md`

### Add a new project
Create `_portfolio/project-4-newname.md`:

```markdown
---
title: "Project Title"
excerpt: "Short description.<br/><img src='/academic-website/images/projects/your-image.jpg'>"
collection: portfolio
---

![Project Image](/academic-website/images/projects/your-image.jpg)
*Caption for the image*

## Overview
Project description...

## Methods
- Method 1
- Method 2

## Related Publications
1. Citation 1
2. Citation 2
```

### Add project images
1. Place images in `images/projects/`
2. Use path: `/academic-website/images/projects/filename.jpg`

---

## Adding Talks/Presentations

Create `_talks/YYYY-MM-DD-talk-title.md`:

```markdown
---
title: "Talk Title"
collection: talks
type: "Conference presentation"
permalink: /talks/YYYY-talk-title
venue: "Conference Name"
date: YYYY-MM-DD
location: "City, Country"
---
Description of your talk.
```

---

## Updating Your Profile

### Basic Info (`_config.yml`)
```yaml
author:
  name: "Your Name"
  bio: "Your tagline"
  location: "City, State"
  employer: "University"
  email: "your@email.edu"
  googlescholar: "https://scholar.google.com/..."
  github: "username"
  linkedin: "username"
```

### Homepage (`_pages/about.md`)
Edit the markdown content to update your bio and research description.

### CV Data (`_data/cv.json`)
Update education, work experience, skills, publications, etc.

### Profile Photo
Replace `images/profile.png` with your photo (keep the same filename).

---

## Customizing Appearance

### Colors (`_sass/theme/_contrast_light.scss`)
```scss
$primary-color: #1a1a1a;    // Main accent color
$text: #1a1a1a;             // Text color
$text-muted: #666666;       // Secondary text
$background: #ffffff;       // Background
$border: #e5e5e5;           // Border color
```

### Font Size (`_sass/_themes.scss`)
```scss
$doc-font-size: 14;         // Base font size in px
$type-size-1: 1.75em;       // h1
$type-size-2: 1.5em;        // h2
$type-size-3: 1.25em;       // h3
```

### Custom CSS (`assets/css/main.scss`)
Add custom styles at the bottom of this file.

---

## Local Development

### Setup (one-time)
```bash
# Install Ruby (if not installed)
brew install ruby

# Install dependencies
cd academic-website
bundle install
```

### Run locally
```bash
bundle exec jekyll serve -l -H localhost
```
Open: http://localhost:4000/academic-website/

### Stop server
Press `Ctrl+C`

---

## Deployment

### Automatic (recommended)
Just push to GitHub - the site rebuilds automatically:
```bash
git add -A
git commit -m "Update description"
git push origin master:main
```

### Check deployment status
```bash
gh run list --repo felixytang/academic-website --limit 1
```

---

## Common Tasks

### Update CV PDF
1. Replace `files/resume.pdf` with your new CV
2. Commit and push

### Add a new navigation item
Edit `_data/navigation.yml`:
```yaml
main:
  - title: "New Page"
    url: /newpage/
```

### Hide a section
Remove or comment out the item in `_data/navigation.yml`

### Change site title
Edit `_config.yml`:
```yaml
title: "Your Name"
description: "Your description"
```

---

## Troubleshooting

### Site not updating?
- Wait 2-3 minutes for GitHub Actions to complete
- Check: https://github.com/felixytang/academic-website/actions

### Images not showing?
- Use full path: `/academic-website/images/...`
- Check file exists in `images/` folder

### Local server errors?
```bash
bundle update
bundle exec jekyll serve
```

---

## Resources

- [Academicpages Documentation](https://academicpages.github.io/)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Markdown Guide](https://www.markdownguide.org/)

---

*Last updated: February 2026*
