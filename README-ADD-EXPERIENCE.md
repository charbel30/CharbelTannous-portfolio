# How to Add a New Experience Section

This README outlines the complete process for adding a new work experience or project to the portfolio website. Follow these steps to ensure consistency across all pages and maintain the site's structure.

## Required Information

Before you begin, gather the following information:

### Essential Details
- **Title**: Job title and company name (e.g., "Frontend Developer at Statbox")
- **Description**: 2-3 sentence overview of the role and key accomplishments
- **Year**: Year of employment/project completion
- **Project Type**: Choose from:
  - "Internship"
  - "Contract Work - Frontend Development"
  - "Full-time Employment"
  - "Personal Project"
  - "Freelance Work"
- **Category**: Choose from:
  - "Professional Experience"
  - "Personal Projects"

### Technical Details
- **Technologies Used**: Array of programming languages/frameworks (e.g., ["React", "JavaScript", "CSS"])
- **Key Features**: 4-5 bullet points describing main accomplishments or features
- **Company/Project URL**: External website link (optional)

### Visual Assets
- **Hero Images**: 2-3 high-quality images showcasing the work
  - Main hero image (recommended: 1200x800px)
  - Additional showcase images or videos
- **Thumbnail Image**: Card thumbnail for work.html and index.html (recommended: 400x300px)
- **Banner Image**: Optional background banner image

## Step 1: Create the Experience Page

### 1.1 Create New HTML File
Create a new file in `/experience/` directory:
```
/experience/[project-slug].html
```

### 1.2 Copy Template Structure
Use `/experience/statbox.html` as a template and modify the following sections:

#### Head Section Updates:
```html
<title>[Job Title - Company] | Charbel Tannous</title>
<meta content="[Description]" name="description" />
```

#### JSON-LD Schema (lines 48-73):
```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "[Project Name] - Charbel Tannous Portfolio",
  "description": "[Brief description]",
  "mainEntity": {
    "@type": "SoftwareSourceCode",
    "name": "[Project Name]",
    "author": {
      "@type": "Person",
      "name": "Charbel Tannous",
      "url": "https://charbeltannous.com"
    },
    "programmingLanguage": ["Technology1", "Technology2"],
    "applicationCategory": "[Category]",
    "features": [
      "Feature 1",
      "Feature 2",
      "Feature 3",
      "Feature 4"
    ]
  }
}
```

#### Hero Section (around line 182):
```html
<h1 class="heading-xlarge">[Job Title at Company]</h1>
```

#### Project Details (around lines 188-198):
```html
<div class="text-size-regular">[Project Type]</div>
<div class="text-size-regular">[Year]</div>
```

#### Hero Images (around lines 212-216):
```html
<img alt="[Alt text]" class="image-full" loading="lazy" src="../images/[image-name]" />
```

#### Project Overview (around line 233):
```html
<div class="text-size-xlarge">
  [Detailed description paragraph]
</div>
```

#### External Link (if applicable, around line 236):
```html
<a href="[external-url]" target="_blank" class="button w-inline-block">
  <div class="button-text">[Button Text]</div>
</a>
```

#### Showcase Section (around line 282):
```html
<p class="text-size-regular">
  [Detailed description of work accomplishments and technical implementation]
</p>
```

## Step 2: Add to Work.html

### 2.1 Locate the Project Items Section
Find the section with `class="works-hero-component w-dyn-items"` (around line 400 in work.html)

### 2.2 Add New Project Item
Add a new project item block:

```html
<div class="project-item w-dyn-item" role="listitem">
  <a
    al=""
    class="work-card w-inline-block"
    href="/experience/[project-slug].html"
    ><div class="work-card-info">
      <div class="text-size-regular text-weight-medium">
        [Company] - [Job Title]
      </div>
      <div class="project-arrow project-arrow-small">
        <div class="arrow-icon-clip">
          <div class="arrow-icon large-arrow-icon w-embed">
            <svg fill="none" height="420" viewbox="0 0 24 24" width="420" xmlns="http://www.w3.org/2000/svg">
              <path d="M13.1722 12L8.22217 7.04999L9.63617 5.63599L16.0002 12L9.63617 18.364L8.22217 16.95L13.1722 12Z" fill="currentColor"></path>
            </svg>
          </div>
          <div class="arrow-icon large-arrow-icon w-embed">
            <svg fill="none" height="420" viewbox="0 0 24 24" width="420" xmlns="http://www.w3.org/2000/svg">
              <path d="M13.1722 12L8.22217 7.04999L9.63617 5.63599L16.0002 12L9.63617 18.364L8.22217 16.95L13.1722 12Z" fill="currentColor"></path>
            </svg>
          </div>
        </div>
      </div>
    </div>
    <div class="work-card-image">
      <img
        alt="[Alt text]"
        class="image-full"
        loading="lazy"
        src="images/[thumbnail-image]"
      />
      <div class="overlay"></div></div
  ></a>
  <div class="tag-wrapper tag-wrapper-small">
    <a class="tag w-inline-block" href="/category/[category-slug].html">
      <div>[Category Name]</div>
    </a>
  </div>
</div>
```

### 2.3 Add Mobile Styles (if needed)
If the thumbnail needs mobile-specific styling, add CSS in the `<style>` section:

```css
@media screen and (max-width: 767px) {
  .[project-slug]-thumb {
    width: 100%;
    height: 200px;
    object-fit: contain;
    display: block;
  }
}
```

## Step 3: Add to Index.html

### 3.1 Update JSON-LD Schema
Find the `workExample` array in the JSON-LD schema (around line 180) and add:

```json
{
  "@type": "SoftwareSourceCode",
  "name": "[Project Name]",
  "codeRepository": "https://charbeltannous.com/experience/[project-slug].html",
  "url": "[external-url]",
  "programmingLanguage": ["Technology1", "Technology2"],
  "description": "[Brief description]"
}
```

### 3.2 Add Project Card
Find the projects grid section and add a new project card:

```html
<div class="tag-wrapper tag-wrapper-small">
  <a class="tag w-inline-block" href="/category/[category-slug].html">
    <div>[Category Name]</div>
  </a>
</div>
<a class="project-card w-inline-block" href="/experience/[project-slug].html">
  <div class="project-background">
    <img
      alt="[Alt text]"
      class="image-full"
      loading="lazy"
      src="images/[thumbnail-image]"
    />
    <div class="overlay"></div>
  </div>
  <div class="work-card-info">
    <div class="text-size-regular text-weight-medium">
      [Project Title]
    </div>
    <div class="project-arrow project-arrow-small">
      <!-- Same arrow SVG structure as work.html -->
    </div>
  </div>
</a>
```

## Step 4: Add Images

### 4.1 Image Requirements
- **Format**: WebP preferred, PNG/JPG acceptable
- **Hero Images**: High resolution, optimized for web
- **Thumbnails**: 400x300px recommended
- **File Naming**: Use descriptive, lowercase names with hyphens

### 4.2 Image Locations
- Place all images in `/images/` directory
- Reference images using relative paths: `../images/[filename]` (from experience pages) or `images/[filename]` (from root pages)

## Step 5: Update Navigation (if needed)

### 5.1 Update "Next Project" Links
In the experience page, update the "Find another project" section to link to other relevant projects.

## Example File Structure

After adding a new experience, your structure should look like:

```
/
├── experience/
│   ├── anghami.html
│   ├── statbox.html
│   └── new-project.html          # New file
├── images/
│   ├── new-project-hero.webp     # New images
│   ├── new-project-thumb.jpg
│   └── new-project-banner.png
├── index.html                    # Updated
├── work.html                     # Updated
└── README-ADD-EXPERIENCE.md      # This file
```

## Checklist

Before going live, verify:

- [ ] Experience page loads correctly with all content
- [ ] Images load properly with appropriate alt text
- [ ] Links work between all pages
- [ ] Mobile responsiveness is maintained
- [ ] JSON-LD schema is valid
- [ ] Meta tags are properly set
- [ ] Project appears on both work.html and index.html
- [ ] Category tags are consistent
- [ ] External links open in new tabs
- [ ] All file paths are correct

## Notes

- **Consistency**: Follow the exact HTML structure and CSS classes from existing pages
- **SEO**: Ensure meta descriptions are unique and descriptive
- **Performance**: Optimize images before adding them
- **Accessibility**: Include proper alt text for all images
- **Testing**: Test on mobile and desktop before deploying

This process ensures your new experience integrates seamlessly with the existing portfolio structure while maintaining design consistency and functionality.