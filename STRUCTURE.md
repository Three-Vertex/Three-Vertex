# Project Structure

This project has been refactored into a modular component-based architecture for better maintainability and reusability.

## Directory Structure

```
src/
├── components/              # Reusable components
│   ├── Header.astro        # Navigation bar
│   ├── Footer.astro        # Footer with links
│   ├── Hero.astro          # Hero section with 3D cube
│   ├── EditorShowcase.astro # 3D Editor window mockup
│   ├── Features.astro      # Features grid section
│   └── About.astro         # About section
├── layouts/
│   └── Layout.astro        # Main layout with global styles
└── pages/
    ├── index.astro         # Home page
    └── about.astro         # About page (example)
```

## How to Add a New Page

1. Create a new file in `src/pages/`, for example: `src/pages/contact.astro`

2. Import and use the Layout component:

```astro
---
import Layout from '../layouts/Layout.astro';
---

<Layout title="Contact - Template" description="Get in touch with us">
    <section class="page-section">
        <div class="container">
            <h1 class="page-title">Contact <span class="gradient-text">Us</span></h1>
            <div class="content">
                <!-- Your content here -->
            </div>
        </div>
    </section>
</Layout>

<style>
    /* Your page-specific styles */
</style>
```

3. The page will automatically include:
   - Header with navigation
   - Footer with links
   - Global styles and CSS variables
   - Responsive design

## Reusable Components

### Layout.astro
Main layout wrapper that includes:
- HTML head with meta tags
- Header component
- Footer component
- Global CSS variables and styles

**Props:**
- `title` (required): Page title
- `description` (optional): Meta description

### Header.astro
Navigation bar with:
- Logo
- Navigation links
- CTA button
- Responsive behavior

### Footer.astro
Footer with:
- Branding
- Product, Company, and Legal links
- Copyright notice

### EditorShowcase.astro
Interactive 3D editor window mockup featuring:
- Window controls and realistic interface
- 3-panel layout (sidebar, viewport, properties)
- Animated 3D model with smooth rotations
- Grid backdrop animation
- Axis indicators and stats overlay
- Material editor panel
- Overlaps the hero section for modern design

### Features.astro
Key Domains section showcasing:
- 3D capabilities
- Artificial Intelligence integration
- Web First technologies

### Hero.astro, About.astro
Home page sections that can be:
- Used as-is
- Modified for other pages
- Used as templates for new sections

## CSS Variables

Global CSS variables defined in `Layout.astro`:

```css
--bg-primary: #0a0a0a;
--bg-secondary: #141414;
--bg-tertiary: #1a1a1a;
--text-primary: #ffffff;
--text-secondary: #a0a0a0;
--accent-primary: #ef4444;
--accent-secondary: #dc2626;
--gradient: linear-gradient(135deg, #ef4444 0%, #dc2626 100%);
```

Use these variables in any component for consistent theming.

## Utility Classes

Available globally:
- `.btn-primary` - Primary button with gradient
- `.btn-secondary` - Secondary outlined button
- `.btn-large` - Larger button size
- `.gradient-text` - Gradient colored text
- `.section-title` - Centered section heading
- `.container` - Centered container with max-width

## Example: Creating a New Section Component

```astro
---
// src/components/YourSection.astro
---

<section class="your-section">
    <div class="container">
        <h2 class="section-title">Your Title</h2>
        <!-- Your content -->
    </div>
</section>

<style>
    .your-section {
        padding: 6rem 0;
        background: var(--bg-secondary);
    }
    /* Your styles */
</style>
```

Then use it in any page:

```astro
---
import Layout from '../layouts/Layout.astro';
import YourSection from '../components/YourSection.astro';
---

<Layout title="Your Page">
    <YourSection />
</Layout>
```

