# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal resume website project with Chinese content. The main resume is a single-page application built with Webpack, Less/CSS, and minimal JavaScript. The project is designed to be printable as a PDF resume.

## Development Commands

### Setup and Development
```bash
# Install dependencies
npm i

# Start development server with live reload
npm run dev

# Build for production
npm run build
```

### Viewing the Resume
- Development: After running `npm run dev`, the resume is available at the local development server URL
- Production: Open `/index.html` in the browser after running `npm run build`
- PDF Export: Use Chrome's print functionality → "Save as PDF" → "More settings" → "Margins: None"

## Architecture and Structure

### Build System
- **Webpack 4**: Main build tool with development and production configurations
- **Entry Point**: `src/entry.js` (simply imports CSS)
- **Template**: `src/index.html` contains the main resume content
- **Output**: Built files go to `static/` directory with hash names

### Styling Architecture
- **Less**: Main CSS preprocessor located in `src/css/`
- **Key CSS files**:
  - `index.less`: Main entry point for styles
  - `style.less`: Component-specific styles
  - `print.less`: Print-specific styles for PDF generation
  - `base.less`: Base styles and utilities
  - `reset.css`: CSS reset

### Content Structure
The resume (`src/index.html`) is organized into:
- **Header**: Personal info, name, job title, contact details
- **Main Content**: Split into left and right columns
  - Left: Work experience and projects
  - Right: Skills, personal projects, and personal traits
- **Footer**: PDF download link

### Asset Processing
- Images: Processed with `url-loader` (8KB limit) and `image-webpack-loader` for optimization
- Fonts: Processed with `url-loader` for embedding
- Icons: Uses iconfont CSS for social and contact icons

## Code Style and Standards

- **EditorConfig**: Configured for 4-space indentation, UTF-8, LF line endings
- **Line Length**: Max 100 characters for JS/TS/Vue files
- **File Encoding**: UTF-8 across all files

## Development Notes

- The project uses Chinese language throughout
- No JavaScript framework - pure HTML/CSS with minimal JS
- Designed for both web viewing and PDF printing
- Webpack dev server provides live reload during development
- All styling is done with Less preprocessor for maintainability