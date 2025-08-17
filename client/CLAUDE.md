# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Dojo by Example is a documentation and learning platform for the Dojo Engine framework, providing practical examples for building fully on-chain games and provable applications on Starknet. This client directory contains a Vocs-based documentation site.

## Development Commands

```bash
# Install dependencies (using pnpm)
pnpm install

# Start development server on port 5174
pnpm dev

# Build production site
pnpm build

# Preview production build
pnpm preview
```

## Architecture

### Core Technologies
- **Vocs**: Static site generator for documentation (v1.0.0-alpha.62)
- **React**: UI framework (v19.0.0)
- **TypeScript**: Type safety
- **Tailwind CSS**: Styling framework
- **PostCSS**: CSS processing

### Directory Structure
- `pages/`: Documentation content in Markdown format
  - `getting-started/`: Basic Dojo concepts and setup
  - `deployments/`: Deployment guides for different networks
  - `integrations/`: Integration guides (React, Unity, AI agents)
  - `advanced-concepts/`: Advanced topics and optimizations
  - `starters/`: Starter templates documentation
- `components/`: React components for the documentation site
- `public/`: Static assets (logos, SVG files)
- `routes.ts`: Sidebar navigation configuration with automatic route-based collapsing
- `vocs.config.ts`: Main Vocs configuration file

### Key Configuration Files
- `vocs.config.ts`: Site configuration, theme, sponsors, and markdown processing
- `routes.ts`: Dynamic sidebar generation with section-specific collapse states
- `tailwind.config.js`: Tailwind CSS configuration
- `tsconfig.json`: TypeScript configuration

## Routing System

The routing system (`routes.ts`) implements:
- Hierarchical sidebar navigation
- Automatic route-based section collapsing
- Dynamic sidebar configuration generation based on current route
- Helper functions: `getTopLevelRoutes()`, `generateSidebarConfig()`, `sidebarFocusOn()`

## Content Organization

Documentation follows this hierarchy:
1. Introduction
2. Getting Started (environment setup, Dojo basics)
3. Deployments (Katana, Slot, Sepolia, Mainnet)
4. Starters & Templates
5. Advanced Concepts
6. Dojo Integrations (React, Unity, AI Agents)
7. Use Cases (placeholder)
8. Best Practices (placeholder)

## Important Notes

- The project uses a patched version of Vocs (see `patches/vocs.patch`)
- Custom Shiki version constraints are applied for Cairo syntax highlighting
- Math rendering is enabled using remark-math and rehype-katex
- The site is configured with GitHub integration for edit links and contributions