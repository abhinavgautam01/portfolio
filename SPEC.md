# Portfolio Template (ahmet.studio style) - SPEC.md

## Concept & Vision

An ultra-minimal, content-first portfolio inspired by ahmet.studio. The design strips away all visual noise to create a focused, professional presence. The layout feels like a well-formatted document rather than a designed website — but that's the intentional aesthetic. Clean, fast, and effortlessly professional.

## Design Language

**Aesthetic Direction:** Ultra-minimal editorial — content as design, inspired by developer resumes and documentation sites

**Color Palette:**
- Background Light: `#ffffff`
- Background Dark: `#09090b` (zinc-950 equivalent)
- Text Primary Light: `#09090b` (zinc-900)
- Text Primary Dark: `#fafafa` (zinc-50)
- Text Muted Light: `#71717a` (zinc-500)
- Text Muted Dark: `#a1a1aa` (zinc-400)
- Border Light: `#e4e4e7` (zinc-200)
- Border Dark: `#27272a` (zinc-800)

**Typography:**
- Primary: System UI stack (SF Pro, Segoe UI, etc.) — matches Geist aesthetic
- Monospace: `'Geist Mono', 'SF Mono', 'Monaco', 'Consolas', monospace`
- Sizes: 14px base, 20px headings, 12px labels/metadata

**Spatial System:**
- Max content width: 640px (max-w-xl equivalent)
- Horizontal padding: 16px
- Vertical padding: 16px
- Gap between sections: 24px
- Experience item gap: 32px

**Motion Philosophy:**
- Hover: Subtle translate-x (2-4px) on experience items
- Tab transitions: Smooth opacity fade
- Duration: 300ms for all transitions
- Easing: ease-out

## Layout & Structure

```
┌─────────────────────────────────────────┐
│  Hero: Name, Bio, Social Links          │
│  (inline, no separate header)           │
├─────────────────────────────────────────┤
│  Tabs: [Experience] [Projects]          │
├─────────────────────────────────────────┤
│  Experience Content (default visible)   │
│  - List of roles with company, dates    │
│  - Tech tags inline                     │
├─────────────────────────────────────────┤
│  Projects Content (hidden until tab)    │
│  - Grid of project cards                │
├─────────────────────────────────────────┤
│  Footer: Site name | Built with         │
└─────────────────────────────────────────┘
```

**Layout Details:**
- Container: `max-w-xl mx-auto`, flex column, `min-h-svh`, `justify-between`
- Sticky footer at bottom
- No sticky header

## Features & Interactions

**Hero:**
- Large name with greeting ("Hey, I'm [Name]")
- Bio text with one embedded link
- Horizontal row of icon links (GitHub, X, LinkedIn, Email, Instagram)
- Icons have subtle hover opacity transition

**Tab Navigation:**
- Two tabs: Experience, Projects
- Active tab: bolder font weight, primary text color
- Inactive tab: muted color
- Click switches content below

**Experience Section:**
- Vertical list of roles
- Each role: title + "at" + company, date range, description, tech tags
- Hover: entire item slides right slightly (translate-x)
- Tech tags shown inline with "/" separator

**Projects Section:**
- Grid or list of projects
- Each project: title, description, tech/links
- Cards with subtle hover effect

**Footer:**
- Two pieces of text side by side
- Site name / "Built with" message

## Component Inventory

### Social Link Icon
- Default: 60% opacity
- Hover: 100% opacity, slight scale
- SVG icons, 20x20px

### Tab Button
- Default: Light font weight, muted color
- Active: Bold font weight, primary color
- Transition: 300ms

### Experience Item
- Default: Normal position
- Hover: translate-x-1 (2px right)
- Structure: Title/company row, date below, description, tags

### Project Card
- Background: transparent
- Hover: subtle background tint
- Title with optional external link icon

## Technical Approach

- Single HTML file with embedded CSS
- CSS custom properties for light/dark theme (prefers-color-scheme)
- Vanilla JS for tab switching
- No frameworks or build tools
- System fonts for performance
- CSS Grid for projects layout
