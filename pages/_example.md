---
# ============================================
# EXAMPLE PAGE - All Available Block Types
# ============================================
# This file documents all available blocks and their options.
# Copy sections as needed for your pages.
# Delete this file or rename with underscore prefix to exclude from build.

title: Example Page Title
description: SEO description for the page (appears in search results)

blocks:

  # ==========================================
  # HERO BLOCK
  # ==========================================
  # Use for page headers/banners
  - type: hero
    badge: Optional Badge Text          # Small label above headline
    headline: "Main <span class='gradient-text'>Headline</span>"  # Supports HTML for styling
    subheadline: Supporting text that appears below the headline
    image: /uploads/hero-image.png      # Optional background/side image
    primaryCta:                         # Optional primary button
      text: Get Started
      link: /contact
    secondaryCta:                       # Optional secondary button
      text: Learn More
      link: /about
    stats:                              # Optional stats bar
      align: center                     # left, center, or right
      items:
        - value: "500+"
          label: Implementations
        - value: "98%"
          label: Satisfaction
        - value: "15+"
          label: Years Experience

  # ==========================================
  # FEATURES BLOCK
  # ==========================================
  # Grid of feature cards with icons
  - type: features
    badge: Why Choose Us                # Optional badge above title
    title: "Our"                        # Required - first part of title
    titleHighlight: "Features"          # Optional - highlighted part of title
    description: Optional description text below the title
    columns: 3                          # 2, 3, or 4 columns (default: 3)
    items:                              # Required - array of features
      - icon: chart                     # Icon name (see icon list below)
        title: Feature One
        description: Description of this feature
        link: /learn-more               # Optional link
        linkText: Learn more            # Optional link text
      - icon: shield
        title: Feature Two
        description: Another feature description
      - icon: zap
        title: Feature Three
        description: Third feature description

  # ==========================================
  # SPLIT BLOCK
  # ==========================================
  # Two-column layout with image and content
  - type: split
    image: /uploads/split-image.png     # Required - image path
    imageAlt: Description of image      # Optional alt text
    imagePosition: right                # left or right (default: right)
    title: "Section <span class='gradient-text'>Title</span>"
    description: "Main description text. Can be multiple paragraphs.\n\nUse \\n\\n for paragraph breaks."
    features:                           # Optional bullet points
      - First feature or benefit
      - Second feature or benefit
      - Third feature or benefit
    cta:                                # Optional call-to-action button
      text: Learn More
      link: /contact

  # ==========================================
  # CTA BLOCK
  # ==========================================
  # Call-to-action section (usually at bottom of page)
  - type: cta
    title: Ready to Get Started?
    description: Contact us today to learn how we can help transform your business.
    primaryCta:
      text: Contact Us
      link: /contact
    secondaryCta:                       # Optional second button
      text: View Solutions
      link: /solutions

  # ==========================================
  # TEAM BLOCK
  # ==========================================
  # Team member grid
  - type: team
    title: "Meet the <span class='gradient-text'>Team</span>"  # Optional title
    members:
      - name: John Smith
        role: CEO & Founder
        image: /uploads/john-smith.png  # Optional photo
        description: Brief bio or description
      - name: Jane Doe
        role: CTO
        image: /uploads/jane-doe.png
        description: Another team member bio

  # ==========================================
  # ACCORDION BLOCK
  # ==========================================
  # Expandable FAQ-style sections
  - type: accordion
    title: Frequently Asked Questions   # Optional title
    items:
      - title: What is your first question?
        content: The answer to the first question goes here. Can include multiple sentences.
      - title: How does this work?
        content: Explanation of how it works.
      - title: What are your pricing options?
        content: Details about pricing and plans.

  # ==========================================
  # CONTACT BLOCK
  # ==========================================
  # Contact form with company info
  - type: contact
    title: Get in Touch                 # Optional title
    description: We'd love to hear from you  # Optional description
    email: info@example.com             # Optional email
    phone: +1-555-123-4567              # Optional phone
    location: 123 Main St, City, State  # Optional address
    quickLinks:                         # Optional quick links
      - text: View Our Solutions
        link: /solutions
      - text: Meet Our Team
        link: /who-we-are

  # ==========================================
  # IMAGE BLOCK
  # ==========================================
  # Single image with optional caption
  - type: image
    src: /uploads/my-image.png          # Required - image path
    alt: Description of the image       # Required - alt text
    caption: Optional caption below image
    size: large                         # small, medium, large, or full (default: large)

  # ==========================================
  # CONTENT BLOCK
  # ==========================================
  # Renders markdown content from below the frontmatter
  - type: content

  # ==========================================
  # SOLUTIONS LIST BLOCK
  # ==========================================
  # Auto-renders all solutions from /solutions/*.md
  - type: solutions-list

  # ==========================================
  # INDUSTRIES LIST BLOCK
  # ==========================================
  # Auto-renders all industries from /industries/*.md
  - type: industries-list

  # ==========================================
  # SECTION BLOCK
  # ==========================================
  # Regular section with white background
  # Use instead of hero for smaller page sections
  - type: section
    badge: Optional Badge                # Optional badge above headline
    headline: "Section <span class='gradient-text'>Headline</span>"
    subheadline: Optional supporting text below the headline
    align: center                        # left, center, or right (default: center)
    height: medium                       # small, medium, or large (default: medium)
    primaryCta:                          # Optional primary button
      text: Learn More
      link: /contact
    secondaryCta:                        # Optional secondary button
      text: View Details
      link: /about

  # ==========================================
  # SECTION-ALT BLOCK
  # ==========================================
  # Section with gradient background (slate/blue)
  # Same options as section, different styling
  - type: section-alt
    badge: Featured                      # Optional badge above headline
    headline: "Alternate <span class='gradient-text'>Section</span>"
    subheadline: This section has a gradient background with decorative blurs
    align: center                        # left, center, or right (default: center)
    height: large                        # small, medium, or large (default: medium)
    primaryCta:
      text: Get Started
      link: /contact

---

# Markdown Content Section

This content appears when you use `type: content` block above.

You can write **bold**, *italic*, and [links](https://example.com).

## Subheadings work too

- Bullet lists
- Are supported
- Like this

1. Numbered lists
2. Also work
3. Like this

```
Code blocks are supported
```

---

# ==========================================
# AVAILABLE ICONS
# ==========================================
# Use these names in the `icon` field:
#
# General:
#   chart, shield, zap, target, lightbulb, star, award,
#   check, clock, globe, heart, home, mail, phone,
#   user, users, settings, search, link, download
#
# Business:
#   briefcase, building, calendar, credit-card, dollar,
#   file, folder, inbox, lock, map, package,
#   pie-chart, printer, server, shopping-cart, truck
#
# Arrows:
#   arrow-right, arrow-left, arrow-up, arrow-down,
#   chevron-right, chevron-left, chevron-up, chevron-down
#
# If icon doesn't exist, it will show a default icon.
