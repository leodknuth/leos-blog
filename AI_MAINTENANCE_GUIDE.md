# Leo's Hugo Blog AI Maintenance Guide

## Executive Summary

This guide provides comprehensive instructions for AI assistants to maintain Leo's Hugo blog hosted at `https://rpai.work`. The blog uses the `hugo-techie-personal` theme with multilingual support (Chinese primary, English secondary) and specialized content types for tech professionals.

**Key Information:**
- **Hugo Version**: v0.152.2+extended
- **Theme**: hugo-techie-personal (Git submodule)
- **Domain**: rpai.work
- **Primary Language**: Chinese (zh-cn)
- **Secondary Language**: English (en-us)
- **Author**: Leo (GitHub: leodknuth)

---

## 1. Project Structure Analysis

### 1.1 Complete Directory Structure

```
leos-blog/
├── 📄 hugo.toml                 # Main configuration file
├── 📄 .gitignore               # Git ignore rules
├── 📄 .gitmodules              # Git submodule configuration
├── 📄 博客内容维护指南.md        # Chinese maintenance guide
├── 📂 archetypes/              # Content templates
│   └── 📄 default.md
├── 📂 assets/                  # Processed resources
│   └── 📂 images/
│       ├── 📄 profile.jpg
│       ├── 📄 profile.png
│       └── 📂 projects/        # Project-specific images
├── 📂 content/                 # Main content directory
│   ├── 📄 _index.md           # Homepage content
│   ├── 📄 about.md            # About page
│   ├── 📂 posts/              # Blog posts
│   │   └── 📄 my-first-post.md
│   ├── 📂 projects/           # Project showcase
│   │   ├── 📄 _index.md
│   │   ├── 📄 ai-code-reviewer.md
│   │   ├── 📄 devops-pipeline.md
│   │   ├── 📄 kubernetes-security-scanner.md
│   │   ├── 📄 legacy-scanner.md
│   │   └── 📄 securecheck.md
│   ├── 📂 gadget/             # Device reviews
│   │   ├── 📄 _index.md
│   │   ├── 📄 macbook-pro-m3.md
│   │   ├── 📄 raspberry-pi-5.md
│   │   ├── 📄 thinkpad-t480.md
│   │   └── 📄 yubikey-5-nfc.md
│   ├── 📂 timeline/           # Timeline events
│   │   ├── 📄 _index.md
│   │   ├── 📄 2023-11-15-award-recognition.md
│   │   ├── 📄 2023-12-05-blog-article.md
│   │   ├── 📄 2024-01-10-training-workshop.md
│   │   ├── 📄 2024-01-15-security-tool-demo.md
│   │   ├── 📄 2024-02-10-ctf-achievement.md
│   │   ├── 📄 2024-02-20-security-tool-release.md
│   │   ├── 📄 2024-03-15-conference-presentation.md
│   │   ├── 📄 2024-04-20-training-workshop.md
│   │   ├── 📄 2024-05-15-recognition-award.md
│   │   └── 📄 2024-06-30-panel-discussion.md
│   └── 📂 about/              # About section
│       └── 📄 _index.md
├── 📂 data/                   # Data files (empty)
├── 📂 i18n/                   # Internationalization (empty)
├── 📂 layouts/                # Custom layouts (empty)
├── 📂 public/                 # Generated site (DO NOT EDIT)
├── 📂 resources/              # Hugo cache (DO NOT EDIT)
├── 📂 static/                 # Static assets
│   └── 📂 images/
│       ├── 📄 profile.jpg
│       ├── 📄 profile.svg
│       ├── 📄 gadget-macbook.svg
│       ├── 📄 project-securecheck.svg
│       └── 📄 timeline-presentation.svg
└── 📂 themes/                 # Theme files
    └── 📂 hugo-techie-personal/  # Git submodule
```

### 1.2 Git Configuration

**Repository Status**:
- Main branch exists but no initial commit yet
- Git submodule: `themes/hugo-techie-personal` from `https://github.com/anantshri/hugo-techie-personal`
- Remote: Not configured (likely intended for GitHub/Cloudflare Pages deployment)

---

## 2. Hugo Configuration Analysis

### 2.1 Core Configuration (hugo.toml)

```toml
baseURL = "https://rpai.work"
defaultContentLanguage = "zh"
defaultContentLanguageInSubdir = true
title = "Leo的技术博客"
theme = "hugo-techie-personal"
disableHugoGeneratorInject = true
enableRobotsTXT = true
```

### 2.2 Multilingual Configuration

**Chinese (Primary - zh-cn)**:
- Title: "Leo的技术博客"
- Weight: 1
- Subtitle: "深度思考 · 技术分享 · 个人成长"
- Description: "Leo的个人技术博客，专注于编程思考、系统设计、开源贡献和技术创新。分享从实践中获得的深度见解。"

**English (Secondary - en-us)**:
- Title: "Leo's Tech Blog"
- Weight: 2
- Subtitle: "Deep Thinking · Tech Sharing · Personal Growth"
- Description: "Leo's personal tech blog focusing on programming insights, system design, open source contributions, and technological innovation. Sharing deep insights from practice."

### 2.3 Taxonomies Configuration

```toml
[taxonomies]
  types = "type"           # Content types
  focus = "focus"          # Focus areas
  activities = "activity"  # Activity types
```

### 2.4 Menu Structure

**Chinese Menu**:
1. 时光轴 (/timeline/) - Weight: 2
2. 项目 (/projects/) - Weight: 3
3. 工具 (/gadget/) - Weight: 4
4. 关于 (/about/) - Weight: 5

**English Menu**:
1. Timeline (/timeline/) - Weight: 2
2. Projects (/projects/) - Weight: 3
3. Gadgets (/gadget/) - Weight: 4
4. About (/about/) - Weight: 5

### 2.5 Key Parameters

**Profile**:
- Profile Picture: `images/profile.jpg`
- GitHub: https://github.com/leodknuth
- Footer: "&copy; [Leo的技术博客](https://rpai.work)"
- Banner: "🚀 探索技术世界的无限可能 · 记录每一个成长瞬间"

**Work in Progress System**:
- Enabled: true
- Default Message: "此内容正在更新和完善中，请稍后查看完整版本。"
- Default Title: "🚧 正在更新中"
- Exclude Statuses: ["discontinued", "archived", "completed", "finished"]

**Navigation System**:
- Breadcrumbs: enabled
- Previous/Next: enabled
- Breadcrumb Separator: "›"
- Section Context: shown

**Timeline Configuration**:
- Activity Icons: enabled

---

## 3. Content Types and Patterns

### 3.1 Content Sections

#### 3.1.1 Posts (`content/posts/`)
**Purpose**: Blog articles and technical posts
**Front Matter Pattern**:
```yaml
+++
title = "Article Title"
date = YYYY-MM-DDTHH:MM:SS+08:00
draft = false
type = "post"
description = "SEO description"
keywords = ["keyword1", "keyword2"]
tags = ["tag1", "tag2"]
author = "Leo"
+++
```

#### 3.1.2 Projects (`content/projects/`)
**Purpose**: Project showcase and portfolio
**Required Front Matter**:
```yaml
---
title: "Project Title"
date: YYYY-MM-DDTHH:MM:SSZ
focus_area: "Focus Area"
status: "active"  # active, completed, discontinued
tech_stack: ["Technology1", "Technology2"]
project_type: "Project Type"
demo_url: "https://example.com"
---
```

**Common Status Values**: `active`, `completed`, `discontinued`, `archived`
**Project Types**: `Personal`, `Commercial SaaS`, `Open Source`, `Research`

#### 3.1.3 Gadgets (`content/gadget/`)
**Purpose**: Device reviews and tech equipment
**Required Front Matter**:
```yaml
---
title: "Device Name"
date: YYYY-MM-DDTHH:MM:SSZ
status: "active"  # active, discontinued, archived
category: "Device Category"
purchase_date: "YYYY-MM-DD"
price: "$Price"
type: gadget
gadget: "device-slug"
specs:
  key1: "value1"
  key2: "value2"
---
```

**Common Status Values**:
- `active`: Currently used
- `discontinued`: No longer used but functional
- `archived`: ⚠️ 已归档设备

#### 3.1.4 Timeline (`content/timeline/`)
**Purpose**: Chronological events and achievements
**File Naming Convention**: `YYYY-MM-DD-event-title.md`
**Required Front Matter**:
```yaml
---
title: "Event Title"
date: YYYY-MM-DDTHH:MM:SSZ
activity: ["activity1", "activity2"]
focus: ["focus1", "focus2"]
event: "Event Name"
location: "Location"
redirect_url: "https://example.com"
featured_image: "images/image.jpg"
---
```

**Activity Types**: `talk`, `presentation`, `conference`, `workshop`, `ctf`, `award`, `recognition`, `training`, `panel`, `discussion`, `tool`, `quote`, `article`, `curator`, `whitepaper`

#### 3.1.5 About (`content/about/`)
**Purpose**: Personal information and about page
**Required Front Matter**:
```yaml
+++
title = "About Me"
date = YYYY-MM-DDTHH:MM:SS+08:00
draft = false
type = "about"
description = "Description for SEO"
+++
```

### 3.2 Section Index Files

Each content section has an `_index.md` file that defines the section page:
- `content/_index.md`: Homepage
- `content/projects/_index.md`: Projects section page
- `content/gadget/_index.md`: Gadgets section page
- `content/timeline/_index.md`: Timeline section page
- `content/about/_index.md`: About section page

---

## 4. Theme Features and Shortcodes

### 4.1 Available Shortcodes

#### 4.1.1 Notice Shortcode
**Purpose**: Display styled notice boxes
**Syntax**: `{{< notice type "custom title" >}}Content{{< /notice >}}`
**Available Types**:
- `warning`: ⚠️ Warning notices
- `info`: ℹ️ Information notices
- `tip`: 💡 Tips and suggestions
- `note`: 📝 General notes (default)

**Example**:
```markdown
{{< notice info "Current Status" >}}
**Daily Driver** - Primary development machine
{{< /notice >}}
```

#### 4.1.2 Image Shortcodes
- `img`: Basic image display
- `article-img`: Article-specific images
- `fontawesome`: Font Awesome icons

#### 4.1.3 Media Shortcodes
- `oembed`: Embedded content (YouTube, Twitter, etc.)

### 4.2 Custom Theme Features

#### 4.2.1 Work in Progress Badges
- Automatically displays for content not in final status
- Customizable messages and titles
- Configurable exclusion statuses

#### 4.2.2 Navigation System
- Breadcrumb navigation
- Previous/Next post navigation
- Section context display

#### 4.2.3 Timeline Features
- Activity icons for different event types
- Chronological ordering
- Event categorization

#### 4.2.4 Project Features
- Status badges (active, completed, discontinued)
- Tech stack display
- Demo URL integration
- Focus area categorization

#### 4.2.5 Gadget Features
- Status indicators
- Specification display
- Purchase information
- Device categorization

---

## 5. File Organization Patterns

### 5.1 Static Files (`static/`)
- **Purpose**: Direct copy to public directory
- **Location**: `/static/` → `https://rpai.work/`
- **Current Contents**:
  - `static/images/profile.jpg`: Profile picture
  - `static/images/profile.svg`: Profile logo
  - Various device and project icons

### 5.2 Asset Files (`assets/`)
- **Purpose**: Processed by Hugo pipelines
- **Location**: Processed and optimized
- **Current Contents**:
  - Device-specific SVG icons
  - Project-specific SVG icons
  - Profile images (multiple formats)

### 5.3 Image Naming Conventions
- **Gadget Images**: `gadget-{device-name}.svg`
- **Project Images**: `project-{project-name}.svg`
- **Timeline Images**: `timeline-{event-type}.svg`
- **Profile Images**: `profile.{jpg,png,svg}`

---

## 6. Development and Deployment Workflow

### 6.1 Local Development

#### 6.1.1 Prerequisites
- Hugo v0.152.2+ extended
- Git
- Modern browser

#### 6.1.2 Development Commands
```bash
# Start development server
hugo server

# Include drafts in development
hugo server --buildDrafts

# Custom port
hugo server --port=1313

# Bind to all interfaces
hugo server --bind=0.0.0.0 --port=1313

# Build for production
hugo

# Build with optimization
hugo --gc --minify
```

#### 6.1.3 Development URLs
- **Chinese Site**: http://localhost:1313/zh/
- **English Site**: http://localhost:1313/en/
- **Root Redirect**: http://localhost:1313/ → /zh/

### 6.2 Content Creation Workflow

#### 6.2.1 Create New Content
```bash
# Blog post
hugo new posts/article-title.md

# Project
hugo new projects/project-name.md

# Gadget review
hugo new gadget/device-name.md

# Timeline event
hugo new timeline/YYYY-MM-DD-event-title.md
```

#### 6.2.2 Content Management Process
1. **Create** content file using Hugo commands
2. **Edit** front matter and content
3. **Add** images to appropriate directories
4. **Test** locally with `hugo server`
5. **Review** multilingual functionality
6. **Commit** changes to Git
7. **Deploy** to production

### 6.3 Git Workflow

#### 6.3.1 Repository Setup
```bash
# Add remote repository (not yet configured)
git remote add origin <repository-url>

# Initial commit (pending)
git add .
git commit -m "Initial commit: Hugo blog setup"
git push -u origin main
```

#### 6.3.2 Content Updates
```bash
# Stage changes
git add .

# Commit with descriptive message
git commit -m "Add project review: MacBook Pro M3"

# Push to remote
git push origin main
```

### 6.4 Deployment Configuration

**Intended Platform**: Cloudflare Pages (based on domain rpai.work)
**Build Command**: `hugo --gc --minify`
**Build Output**: `public/` directory
**Environment**: Production

---

## 7. Content Templates

### 7.1 Blog Post Template
```markdown
+++
title = "Article Title"
date = {{ .Date }}
draft = false
type = "post"
description = "SEO-friendly description"
keywords = ["keyword1", "keyword2"]
tags = ["tag1", "tag2"]
author = "Leo"
+++

## Introduction

Article introduction...

## Main Content

Detailed content...

## Conclusion

Summary and conclusions...
```

### 7.2 Project Template
```markdown
---
title: "Project Name"
date: {{ .Date }}
focus_area: "Focus Area"
status: "active"
tech_stack: ["Technology1", "Technology2"]
project_type: "Personal"
demo_url: "https://example.com"
---

## Project Overview

Project description...

## Technical Details

Technical implementation...

## Features

- Feature 1
- Feature 2

{{< notice info "Development Status" >}}
**Status**: {{ .Get "status" }}
{{< /notice >}}
```

### 7.3 Gadget Review Template
```markdown
---
title: "Device Name Full Model"
date: {{ .Date }}
status: "active"
category: "Device Category"
purchase_date: "YYYY-MM-DD"
price: "$Price"
type: gadget
gadget: "device-slug"
specs:
  processor: "Processor Details"
  memory: "Memory Configuration"
  storage: "Storage Configuration"
  display: "Display Specifications"
---

## Usage Context

{{< notice info "Current Status" >}}
**Daily Driver** - Primary use case description
{{< /notice >}}

## Performance Experience

### Performance Analysis
Detailed performance assessment...

## Hardware Assessment

### Build Quality & Design
Physical build evaluation...

## Productivity Impact

### Positive Changes
Benefits experienced...

### Minor Limitations
Drawbacks identified...

## Value Assessment

### Pricing Consideration
Value for money analysis...

### Recommended For
Ideal user profiles...

## Long-term Outlook

Long-term assessment...

**Overall Rating: X/10** - Summary evaluation
```

### 7.4 Timeline Event Template
```markdown
---
title: "Event Title"
date: {{ .Date }}
activity: ["activity1", "activity2"]
focus: ["focus1", "focus2"]
event: "Event Name"
location: "City, Country"
redirect_url: "https://example.com"
featured_image: "images/event-image.jpg"
---

## Event Overview

Description of the event...

## Key Takeaways

{{< notice tip "Key Insights" >}}
1. Insight 1
2. Insight 2
3. Insight 3
{{< /notice >}}

## Topics Covered

- Topic 1
- Topic 2
- Topic 3
```

---

## 8. Maintenance Operations

### 8.1 Content Updates

#### 8.1.1 Update Existing Content
1. **Locate** the content file in appropriate directory
2. **Update** front matter if needed
3. **Edit** content body
4. **Update** associated images if necessary
5. **Test** changes locally
6. **Commit** changes with descriptive message

#### 8.1.2 Change Content Status
```yaml
# For projects and gadgets
status: "active"        # → "completed"
status: "active"        # → "discontinued"
status: "active"        # → "archived"
```

### 8.2 Configuration Updates

#### 8.2.1 Update Site Information
Edit `hugo.toml`:
```toml
# Basic information
title = "New Title"
subtitle = "New Subtitle"

# Profile information
[params]
  profile_pic = "images/new-profile.jpg"
  description = "New description"

# Social links
[params.social_links]
  github_url = "https://github.com/username"
  # Add other social platforms as needed
```

#### 8.2.2 Update Menu Structure
Add new menu items in `hugo.toml`:
```toml
# Chinese menu
[[languages.zh.menu.main]]
  name = "新菜单项"
  url = "/new-section/"
  weight = 6

# English menu
[[languages.en.menu.main]]
  name = "New Menu Item"
  url = "/new-section/"
  weight = 6
```

### 8.3 Image Management

#### 8.3.1 Add New Images
```bash
# For general use
cp image.jpg static/images/image.jpg

# For projects
cp project-image.svg assets/images/projects/project-image.svg

# For gadgets
cp gadget-icon.svg assets/images/gadget-device.svg
```

#### 8.3.2 Update Profile Picture
```bash
# Replace profile image
cp new-profile.jpg static/images/profile.jpg
cp new-profile.png assets/images/profile.png
```

#### 8.3.3 Image Optimization
- Use WebP format for better compression
- Provide multiple sizes for responsive design
- Use SVG for icons and simple graphics
- Compress JPEG/PNG for photographs

### 8.4 SEO Optimization

#### 8.4.1 Meta Descriptions
Each content piece should have a unique, descriptive meta description:
```yaml
description = "Specific, keyword-rich description under 160 characters"
```

#### 8.4.2 Structured Data
The theme automatically generates structured data for:
- Articles and blog posts
- Projects and portfolios
- Organization information
- Breadcrumb navigation

#### 8.4.3 XML Sitemaps
Automatically generated at:
- `/sitemap.xml` - Main sitemap
- `/zh/sitemap.xml` - Chinese content
- `/en/sitemap.xml` - English content

---

## 9. Troubleshooting Guide

### 9.1 Common Issues

#### 9.1.1 Build Failures
**Symptoms**: `hugo` command fails with errors
**Solutions**:
1. **Check syntax** in `hugo.toml`
2. **Validate front matter** in Markdown files
3. **Verify image paths** and references
4. **Check for missing** required front matter fields

#### 9.1.2 Missing Images
**Symptoms**: Images not displaying correctly
**Solutions**:
1. **Verify file paths** in `static/` and `assets/`
2. **Check image references** in content
3. **Ensure proper file extensions**
4. **Validate Hugo resource processing**

#### 9.1.3 Language Switching Issues
**Symptoms**: Language switcher not working
**Solutions**:
1. **Verify language configuration** in `hugo.toml`
2. **Check `defaultContentLanguageInSubdir = true`**
3. **Ensure content exists** for both languages
4. **Validate menu structure** for each language

#### 9.1.4 Theme Not Loading
**Symptoms**: Site appears unstyled
**Solutions**:
1. **Check Git submodule status**: `git submodule status`
2. **Update submodule**: `git submodule update --init --recursive`
3. **Verify theme path** in `hugo.toml`
4. **Check theme compatibility** with Hugo version

### 9.2 Performance Issues

#### 9.2.1 Slow Build Times
**Solutions**:
1. **Use `--gc --minify`** for production builds
2. **Optimize image sizes** before adding to site
3. **Limit resource processing** for unused assets
4. **Use Hugo cache** effectively

#### 9.2.2 Large Site Size
**Solutions**:
1. **Compress images** before adding
2. **Use modern formats** (WebP, AVIF)
3. **Enable resource minification**
4. **Remove unused assets**

### 9.3 Content Issues

#### 9.3.1 Missing Sections
**Symptoms**: 404 errors for section pages
**Solutions**:
1. **Create `_index.md` files** for each section
2. **Verify section names** match menu configuration
3. **Check content type configuration**
4. **Validate taxonomy settings**

#### 9.3.2 Incorrect Sorting
**Symptoms**: Content not in expected order
**Solutions**:
1. **Use proper date format** in front matter
2. **Add weight parameter** for manual ordering
3. **Verify taxonomy configuration**
4. **Check theme sorting logic**

---

## 10. Best Practices

### 10.1 Content Creation

#### 10.1.1 Front Matter Standards
- **Required fields**: title, date, type
- **Recommended fields**: description, status, focus areas
- **Date format**: `YYYY-MM-DDTHH:MM:SSZ` or `YYYY-MM-DDTHH:MM:SS+08:00`
- **Status consistency**: Use standard status values across content types

#### 10.1.2 Content Organization
- **Use descriptive filenames** with kebab-case
- **Follow naming conventions** for consistency
- **Group related content** in appropriate sections
- **Maintain chronological order** for timeline events

#### 10.1.3 SEO Best Practices
- **Unique meta descriptions** for each page
- **Keyword optimization** in titles and descriptions
- **Proper heading hierarchy** (H1 → H2 → H3)
- **Image alt text** for accessibility and SEO

### 10.2 Technical Standards

#### 10.2.1 File Management
- **Absolute paths** for all file references
- **Consistent image naming** conventions
- **Proper file organization** in static/assets
- **Version control** for all content changes

#### 10.2.2 Configuration Management
- **Environment-specific** configurations
- **Backup important files** before changes
- **Test configuration changes** locally
- **Document custom configurations**

#### 10.2.3 Performance Optimization
- **Image optimization** before upload
- **Resource minification** for production
- **Cache configuration** for static assets
- **Lazy loading** for images when possible

### 10.3 Maintenance Standards

#### 10.3.1 Regular Tasks
- **Review and update** outdated content
- **Check for broken links** and images
- **Optimize image sizes** and formats
- **Update dependencies** and theme

#### 10.3.2 Backup Procedures
- **Git version control** for all content
- **Regular commits** with descriptive messages
- **Tag releases** for major milestones
- **Backup theme customizations**

#### 10.3.3 Quality Assurance
- **Test multilingual functionality**
- **Validate HTML output** and accessibility
- **Check mobile responsiveness**
- **Verify all navigation links**

---

## 11. Quick Reference Commands

### 11.1 Development Commands
```bash
# Start development server
hugo server

# Include drafts
hugo server --buildDrafts

# Custom port and bind
hugo server --bind=0.0.0.0 --port=1313

# Production build
hugo

# Optimized production build
hugo --gc --minify

# Check configuration
hugo config

# List all content
hugo list all

# Validate site
hugo check
```

### 11.2 Content Creation Commands
```bash
# Create new blog post
hugo new posts/article-title.md

# Create new project
hugo new projects/project-name.md

# Create new gadget review
hugo new gadget/device-name.md

# Create new timeline event
hugo new timeline/YYYY-MM-DD-event-title.md
```

### 11.3 Git Commands
```bash
# Check status
git status

# Add all changes
git add .

# Commit changes
git commit -m "Descriptive commit message"

# Push to remote
git push origin main

# Update theme submodule
git submodule update --init --recursive

# Check submodule status
git submodule status
```

### 11.4 File Locations
```bash
# Main configuration
hugo.toml

# Content directories
content/posts/
content/projects/
content/gadget/
content/timeline/
content/about/

# Static assets
static/images/
assets/images/

# Theme files
themes/hugo-techie-personal/

# Generated site
public/
```

---

## 12. Emergency Procedures

### 12.1 Site Recovery
1. **Restore from Git**: `git checkout HEAD -- .`
2. **Rebuild site**: `hugo --gc --minify`
3. **Verify locally**: `hugo server`
4. **Deploy to production**

### 12.2 Theme Recovery
```bash
# Remove and reinitialize theme submodule
git rm themes/hugo-techie-personal
git submodule deinit themes/hugo-techie-personal
git submodule add https://github.com/anantshri/hugo-techie-personal themes/hugo-techie-personal
```

### 12.3 Content Recovery
1. **Check Git history**: `git log -- content/file.md`
2. **Restore specific version**: `git checkout [commit] -- content/file.md`
3. **Compare versions**: `git diff HEAD HEAD~1 -- content/file.md`

---

## 13. Contact and Support

### 13.1 Theme Documentation
- **Theme Repository**: https://github.com/anantshri/hugo-techie-personal
- **Hugo Documentation**: https://gohugo.io/documentation/
- **Markdown Guide**: https://www.markdownguide.org/

### 13.2 Common Issues
- **Build problems**: Check front matter syntax
- **Theme issues**: Verify submodule status
- **Deployment issues**: Validate build process
- **Performance issues**: Optimize images and resources

### 13.3 Debug Information
- **Hugo Version**: v0.152.2+extended
- **Theme**: hugo-techie-personal
- **Domain**: rpai.work
- **Languages**: zh-cn (primary), en-us (secondary)
- **Content Types**: posts, projects, gadget, timeline, about

---

**AI Assistant Instructions**: Use this comprehensive guide to maintain, update, and troubleshoot Leo's Hugo blog. Follow the established patterns and conventions for consistency. Always test changes locally before deployment and commit changes with descriptive messages.