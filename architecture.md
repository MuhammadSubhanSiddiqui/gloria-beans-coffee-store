# Gloria Beans - System Architecture

## Overview

This document outlines the technical architecture of the Gloria Beans Coffee Store website, providing insight into the design decisions, technologies used, and code organization.

## Frontend Stack

### Core Technologies
- **HTML5** (Semantic markup)
- **CSS3** (Modern styling)
- **Google Fonts** (Typography)

### CSS Architecture

#### Style.css (Main Stylesheet)
Primary stylesheet containing:
- Reset and base styles
- Navigation bar styling
- Hero section layouts
- Footer and fixed positioning
- Responsive design utilities

#### style2.css (Login Stylesheet)
Specialized stylesheet for the login/register form containing:
- Form container styling
- Input field designs
- Button actions and hover states
- Card-based UI components

### Key Design Patterns

#### 1. Colors and Theming
```css
--primary-color: rgb(236, 205, 137); /* Gold/Light Brown */
--dark-bg: rgba(0, 0, 0, 0.95);      /* Dark overlays */
--text-white: #ffffff;               /* White text */
```

#### 2. Navigation
- Sticky positioning for seamless navigation
- Flexbox layout for center-aligned menu
- Logo integration with icon
- Responsive anchor links

#### 3. Hero Sections
- Full-screen hero backgrounds
- Centered typography with large fonts
- Call-to-action buttons with hover effects
- Smooth color transitions

#### 4. Product Cards
- Imagery with hover expansion effects
- Descriptive text blocks
- External link integration (Amazon)
- Consistent styling across products

#### 5. Login Form
- Card-based design with shadow effects
- Clean form elements with focus states
- Register/Sign-in toggle buttons
- Social-friendly input styling

## Page Structure

```
├── Header (Navbar)
│   ├── Logo with icon
│   └── Navigation Links
│
├── Main Content (Page-specific)
│   ├── Hero Section
│   ├── Features/Products
│   └── Additional Content
│
└── Footer/Contributors
```

## File Organization

### Page Relationship Flow
```
index.html (Home)
    ↓ Contains links to
store.html (Products)
about.html (Company Info)
contact.html (Contact)
franchises.html (Franchise Gallery)
login.html (User Authentication)
contributors.html (Team Info)

All pages share:
- Common navbar structure
- favicon references
- basic font integrations
```

## CSS Coding Conventions

### Naming Patterns
- BEM-inspired naming where appropriate
- Class names are lowercase with hyphens
- Consistent naming for repeated patterns (e.g., `.b_store`, `.login-form`)

### Positioning Strategy
- Heavy use of `position: absolute`
- `z-index` layering for proper stacking
- `display: flex` for alignment
- Percentage-based widths for responsiveness

### Animation Design
- Smooth transitions with `transition: 0.5s`
- Hover effects for interactivity
- `@keyframes` reserved for future animations
- Color changes for visual feedback

## Responsive Strategy

### Mobile-First Approach
- Base CSS targets mobile devices
- Media queries extend for larger screens
- Flexible containers with `width: 100%`
- Adjusted font sizes and spacing

### Breakpoints
- Desktop view: Default (min-width style)
- Tablet adjustments: Font size and spacing
- Mobile optimizations: Navigation and layouts

## Performance Considerations

### Optimization Techniques
- External stylesheet loading
- External font integration via Google Fonts API
- No JavaScript libraries for minimal footprint
- Placeholder images optimized for web

### Loading Strategy
- `<link rel="preconnect">` for Google Fonts
- Sequential stylesheet loading
- Image placeholders with alt text

## Accessibility Features

### HTML Semantics
- Proper heading hierarchy (`<h1>` to `<h6>`)
- Alt text for images
- Semantic link elements with proper hrefs

### CSS Accessibility
- Sufficient color contrast
- Hover states for interactive elements
- Focus indicators for keyboard navigation
- Readable font sizes (18px+ base)

## Browser Compatibility

### Test Environments
- Chrome (primary target)
- Firefox (extended support)
- Edge (Chromium-based)
- Safari (WebKit-based)

### CSS Support
- Flexbox (CSS3)
- CSS Variables (in process)
- Relative positioning
- Absolute positioning

## Future Enhancements

### Potential Improvements
- JavaScript interactions (mobile menu, form validation)
- CSS Grid implementations
- CSS Scss preprocessing
- API integration for dynamic content
- SEO optimization with meta tags
- Performance monitoring and analytics

### Extension Points
- Additional page templates
- Theme customization features
- Responsive navigation drawer
- Page transitions and animations
- Local storage for user preferences