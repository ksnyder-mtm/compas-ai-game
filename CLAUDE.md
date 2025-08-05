# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the COMPAS Learning Journey, an interactive web-based educational game that teaches the COMPAS framework for systematic problem-solving through two engaging scenarios. The application is a single-file HTML game that demonstrates how to approach challenges (including AI implementation) without "reaching for the flamethrower."

**Live Game:** https://joshuamtm.github.io/compas-ai-game/

## Architecture

### Technology Stack
- **Frontend:** Pure HTML/CSS/JavaScript (no frameworks)
- **Styling:** Embedded CSS with mobile-responsive design
- **Deployment:** Static hosting via GitHub Pages
- **No build process or dependencies required**

### Single-File Architecture
The entire application is contained in `index.html` with:
- **HTML Structure:** Game containers, scenario selection, progress tracking
- **CSS Styling:** Comprehensive styling including animations, responsive design, and theme colors
- **JavaScript Logic:** Game state management, scenario data, user interactions

### Key Components

#### Game Flow
1. **Initial Selection:** Users choose between "Moth Infestation" or "Nonprofit AI Panic" 
2. **Six COMPAS Steps:** Context → Objective → Method → Performance → Assessment → Super You
3. **Interactive Choices:** Multiple choice questions with immediate feedback
4. **Progress Tracking:** Visual progress bar and step indicators
5. **Completion Summary:** Personalized achievements and insights
6. **Extended Learning:** After completing "Nonprofit AI Panic," users can access 4 additional nonprofit-focused scenarios
7. **Exit Options:** Users can return to home page or continue with additional scenarios

#### Data Structure
- `scenarios` object contains all game content
- Each scenario has 6 steps corresponding to COMPAS framework
- Feedback system provides correct/incorrect responses with detailed explanations
- Progress tracking through `currentStep` and `selectedChoices`

## Common Development Tasks

### Local Development
```bash
# Clone and run locally
git clone https://github.com/ksnyder-mtm/compas-ai-game.git
cd compas-ai-game

# Option 1: Open directly in browser
open index.html

# Option 2: Use local server for testing
python -m http.server 8000
# Then visit http://localhost:8000
```

### Testing Changes
- No build step required - changes to `index.html` are immediately visible
- Test both scenarios completely
- Verify mobile responsiveness
- Check all choice combinations and feedback messages

### Content Updates
When updating scenario content:
- Modify the `scenarios` object in the JavaScript section (starting around line 1086)
- Each scenario contains: name, completion messages, summary content, scenarios array, and insights
- Maintain consistent structure for choices, feedback, and callouts
- Test feedback messages for both correct and incorrect responses

### Deployment
The project uses GitHub Pages for hosting:
- Changes to `main` branch automatically deploy
- No build process - direct file serving
- Custom domain configured via repository settings

## Code Style and Patterns

### CSS Organization
- Mobile-first responsive design with `@media` queries
- CSS custom properties for consistent theming
- Animation classes for smooth transitions
- Component-based class naming (`.scenario-card`, `.choice-button`, etc.)

### JavaScript Patterns
- Pure vanilla JavaScript with no external dependencies
- Event delegation for dynamic content
- State management through global variables
- Functional approach for game logic

### Content Structure
- Scenarios follow consistent six-step COMPAS framework
- Each step includes: title, icon, description, callout, question, choices, feedback
- Feedback includes both success and error messages with implementation tips
- Progressive disclosure of content based on user choices

## Key Design Principles

1. **No External Dependencies:** Self-contained application requiring no external resources
2. **Mobile-First:** Responsive design that works on all devices
3. **Accessible:** Clear navigation, readable fonts, sufficient color contrast
4. **Educational Focus:** Content emphasizes learning over entertainment
5. **Framework Agnostic:** Uses COMPAS methodology applicable to any challenge
6. **Progressive Learning:** Home page introduces concept, then nonprofit scenarios provide focused AI practice

## Important Notes

- Home page offers 2 scenarios: personal (moth) and organizational (nonprofit AI)
- After completing "Nonprofit AI Panic," users access 4 additional nonprofit scenarios:
  - Volunteer Management Crisis
  - Donor Communications Challenge  
  - Program Impact Measurement
  - Community Outreach Enhancement
- All scenarios follow identical COMPAS framework structure
- Feedback messages include practical implementation tips for nonprofit contexts
- Visual design uses compass/navigation theming throughout
- All content is embedded - no external API calls or data loading
- Exit options allow users to return to home page at any completion point