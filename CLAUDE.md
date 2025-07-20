# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a study repository containing:
- **Main project**: A study project focused on various web technologies (Vue 3, Express, Tailwind CSS, etc.)
- **Template admin**: A Mosaic HTML admin template from Cruip.com using Tailwind CSS 4.0

## Development Commands

### Template Admin (template-admin/)
- `npm install` - Install dependencies 
- `npm run dev` - Watch mode: rebuild CSS when HTML/JS files change
- `npm run build` - Build production CSS from source

The template uses Tailwind CSS 4.0 with the CLI tool to compile `css/style.css` → `style.css`.

## Project Structure

### Main Repository
- `README.md` - Contains technology stack overview (Japanese)
- `docs/` - Empty documentation directory
- `template-admin/` - Complete HTML admin template

### Template Admin Architecture
- **Static HTML pages**: Complete admin dashboard with 40+ pages (analytics, billing, users, etc.)
- **CSS Architecture**: 
  - `css/style.css` - Source Tailwind CSS with custom theme variables
  - `style.css` - Compiled output
  - Custom color palette (violet, sky, gray variants)
  - Form plugin integration
- **JavaScript**: Vanilla JS with Alpine.js and Chart.js for interactivity
- **Assets**: Comprehensive image library and icon set

## Technology Stack (from main README)
- **Frontend**: Vue 3, Pinia, Axios, Tailwind CSS
- **Backend**: Express, openapi-backend, Jest, Supertest
- **Database**: Prisma ORM, SQLite
- **Infrastructure**: Ansible, Terraform
- **Utilities**: dotenv, cors

## Development Notes
- Template is designed for WSL Ubuntu environment
- No test framework or linting commands identified
- Template uses modern Tailwind CSS 4.0 syntax with custom variants and theme configuration