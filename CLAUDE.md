# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains the source code and materials for "Understanding Astro" - a comprehensive book about the Astro web framework. The repository is structured as a learning resource with practical examples and complete projects demonstrating Astro concepts.

## Repository Structure

- **Root Level**: Contains chapter markdown files (ch1.md through ch8.md), conclusion.md, preface.md, and README.md
- **Chapter Directories**: Each `ch{N}/` directory contains complete working projects that accompany the corresponding chapter
- **Images Directory**: Contains all screenshots, diagrams, and visual assets referenced in the book chapters

### Key Chapter Projects

- **ch1/astro-beginner-project/**: Basic Astro application demonstrating components, layouts, and theming
- **ch2/test-react-app/**: React application for comparison with Astro architecture
- **ch5/react.dev-astro/**: React documentation site clone built with Astro, showcasing content collections and MDX
- Other chapters contain additional example projects

## Development Commands

### Astro Projects (ch1, ch5)
```bash
# Start development server
npm run dev
# or
astro dev

# Build for production  
npm run build
# or
astro build

# Preview production build
npm run preview
# or  
astro preview
```

### React Project (ch2)
```bash
# Start development server
npm run start

# Build for production
npm run build

# Run tests
npm run test
```

## Common Development Workflows

### Working with Astro Projects
1. Navigate to the specific chapter directory (e.g., `cd ch1/astro-beginner-project/`)
2. Install dependencies: `npm install`
3. Start development server: `npm run dev`
4. Access the application at `http://localhost:4321` (default Astro port)

### Key Astro Concepts Demonstrated

- **Components**: Located in `src/components/` - reusable `.astro` files
- **Layouts**: Located in `src/layouts/` - page structure templates  
- **Pages**: Located in `src/pages/` - file-based routing with `.astro` and `.md` files
- **Styles**: Component-scoped CSS with global styles in `src/styles/`
- **Content Collections**: Used in ch5 project (`src/content/`) for managing blog content with type safety

### Development Tools and Integrations

- **Tailwind CSS**: Used in ch5 project with custom configuration
- **MDX**: For enhanced markdown with component support
- **TypeScript**: Configured across projects with proper type definitions
- **Content Collections**: Astro's solution for type-safe content management

## Architecture Notes

### Astro's Core Philosophy
- **Islands Architecture**: Interactive components are "islands" of interactivity in otherwise static HTML
- **Zero JavaScript by Default**: Only ships JavaScript when explicitly needed via client directives
- **Multi-Framework Support**: Can use React, Vue, Svelte, etc. components within the same project

### File Conventions
- `.astro` files contain both server-side script (in frontmatter fences) and template markup
- Component names should be PascalCase
- Pages use file-based routing where file structure determines URL structure
- Dynamic routes use bracket notation (e.g., `[slug].astro`)

### Best Practices Demonstrated
- Component composition using slots
- CSS scoping to prevent style conflicts
- Proper use of client directives for hydration (`client:load`, `client:visible`, etc.)
- Content collections for type-safe content management
- Environment variable handling for different deployment targets

## Testing and Building

- Most projects use standard npm scripts for building and development
- The ch2 React project includes Jest testing setup
- Production builds create static assets in `dist/` directory by default
- Use `astro sync` to manually update type definitions when needed

## Deployment Considerations

- Projects are designed to be deployed as static sites by default
- Server-side rendering (SSR) concepts are covered in later chapters
- Static builds can be deployed to any static hosting provider
- Assets are optimized and fingerprinted during build process