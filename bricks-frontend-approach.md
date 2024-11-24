# Frontend Development Approach for Bricks - Theme First

## Overview
This guide outlines the process for developing Bricks themes using Claude.ai, focusing on the Theme-First approach. This methodology ensures consistent design implementation and efficient development.

## 1. Initial Setup

### 1.1 Required Files for Claude.ai
```plaintext
project_root/
├── screenshots/              # Website screenshots
│   ├── full-page.jpg        # Full page screenshots
│   ├── components/          # Individual component screenshots
│   └── responsive/          # Mobile/tablet views
├── html/                    # HTML templates
│   ├── base-template.html   # Basic structure
│   └── components/          # Component HTML files
└── theme/                   # Theme files
    ├── style.css           
    └── theme-settings.json  # Bricks theme settings
```

### 1.2 Screenshot Guidelines
- Full page: 1920px width
- Components: Isolated with padding
- Clear element boundaries
- Include hover/active states
- Show responsive variations

### 1.3 HTML Template Requirements
```html
<!-- Include structure markers -->
<div class="section-marker">Hero Section</div>
<div class="component-marker">Navigation</div>

<!-- Include CSS classes -->
<div class="sf-container">
  <div class="sf-content">
    <!-- Content -->
  </div>
</div>
```

## 2. Theme Development Process

### 2.1 Extract Design Tokens
Provide Claude.ai with screenshots to extract:

```json
{
  "colors": {
    "primary": "#0047B1",
    "secondary": "#B0DCF4",
    "background": "#F9F6F3"
  },
  "typography": {
    "headings": "Didact Gothic",
    "body": "Didact Gothic"
  },
  "spacing": {
    "container": "1280px",
    "section": "60px"
  }
}
```

### 2.2 Generate Theme Settings
Ask Claude.ai:
```plaintext
"Based on these design tokens and screenshots, please generate the Bricks theme settings JSON for:
1. Colors
2. Typography
3. Container settings
4. Spacing system"
```

### 2.3 Component Analysis
For each component:
```plaintext
"Please analyze this component screenshot and provide:
1. Bricks structure
2. Required classes
3. Responsive behavior
4. Interactive states"
```

## 3. Implementation Workflow

### 3.1 Base Setup
1. Create theme settings:
```bash
# Theme structure
/bricks-with-child-theme
  /smooth-flow-theme
    style.css
    functions.php
```

2. Import settings:
```php
// functions.php
add_action('init', 'smooth_flow_theme_settings');
```

### 3.2 Component Development
For each component:

1. **Show Claude.ai:**
   - Component screenshot
   - Desired behavior
   - Responsive requirements

2. **Request Structure:**
```plaintext
"Please provide:
1. HTML structure for Bricks
2. CSS classes needed
3. Custom styles
4. Responsive breakpoints"
```

3. **Implementation:**
   - Create component in Bricks
   - Add to template library
   - Test responsive behavior

### 3.3 Page Templates
For full pages:
```plaintext
"Based on this full-page screenshot, please provide:
1. Section breakdown
2. Component hierarchy
3. Global styles needed
4. Responsive strategy"
```

## 4. Quality Assurance

### 4.1 Checklist for Claude.ai Reviews
```markdown
- [ ] Color usage consistency
- [ ] Typography hierarchy
- [ ] Spacing patterns
- [ ] Component modularity
- [ ] Responsive behavior
- [ ] Interactive states
- [ ] Performance optimization
```

### 4.2 Testing Process
1. Desktop review
2. Mobile/tablet review
3. Interactive elements
4. Loading performance
5. Cross-browser check

## 5. Best Practices

### 5.1 Naming Conventions
```css
/* Prefix all custom classes */
.sf-container
.sf-heading
.sf-button

/* Component specific */
.sf-hero-section
.sf-card-grid
```

### 5.2 Responsive Approach
```css
/* Breakpoints */
Desktop: 1280px
Tablet: 768px
Mobile: 375px

/* Container widths */
Desktop: 1200px
Tablet: 720px
Mobile: 100%
```

### 5.3 Performance Guidelines
- Optimize images before upload
- Minimize custom CSS
- Use Bricks built-in features
- Leverage caching

## 6. Example Prompts for Claude.ai

### 6.1 Theme Setup
```plaintext
"Based on SmoothFlowBase-Template.html and these screenshots, please:
1. Generate the theme settings JSON
2. Create the basic style.css
3. List required custom classes"
```

### 6.2 Component Creation
```plaintext
"Looking at this hero section screenshot, please provide:
1. Bricks builder structure
2. Custom classes needed
3. Responsive adjustments
4. Interactive elements"
```

### 6.3 Style Refinement
```plaintext
"Please analyze these hover states and provide:
1. CSS transitions
2. Interactive properties
3. Accessibility considerations"
```

## 7. Troubleshooting

### 7.1 Common Issues
1. Spacing inconsistencies
2. Responsive breakpoints
3. Typography scaling
4. Color inheritance

### 7.2 Solutions Approach
```plaintext
"I'm seeing [specific issue] with [component].
Screenshots attached. Please suggest:
1. Potential causes
2. Solution approaches
3. Prevention methods"
```

## 8. Documentation

### 8.1 Component Library
Document each component:
```markdown
# Component Name
- Purpose
- Usage
- Variations
- Responsive behavior
- Custom classes
- Dependencies
```

### 8.2 Style Guide
Maintain living documentation:
```markdown
# Style Guide
- Colors
- Typography
- Spacing
- Components
- Patterns
```

## 9. Version Control

### 9.1 Commit Structure
```bash
feat: add hero section
style: update primary colors
fix: responsive issues in navigation
```

### 9.2 Branch Strategy
```bash
main
├── feature/theme-setup
├── feature/components
└── feature/templates
```

## 10. Resources

### 10.1 Reference Files
- SmoothFlowBase-Template.html
- SF Home.jpg
- Current theme settings

### 10.2 Tools
- Bricks Builder
- Local by Flywheel
- Chrome DevTools
- Claude.ai
- Cursor.ai