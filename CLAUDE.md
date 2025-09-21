# CLAUDE.md - Repository Context for Claude Code

This file provides essential context for Claude Code instances working in this repository.

## Repository Overview

**N8N Tutorial Slides** - A comprehensive tutorial presentation system for teaching N8N automation to business users, built with Reveal.js.

### Target Audience
- Business professionals (marketing, sales, startup founders)
- Non-technical users new to automation
- People who have never coded before
- Focus on practical business value over technical implementation

## Project Structure

```
├── day-1/
│   ├── slides.md          # Day 1 tutorial content (business-focused basics)
│   └── images/            # Day 1 specific images
├── day-2/
│   ├── slides.md          # Day 2 tutorial content (advanced workflows & LLM)
│   └── images/            # Day 2 specific images
├── assets/
│   ├── css/
│   │   └── custom.css     # Custom styling for presentations
│   └── images/
│       └── common/        # Shared images across days
├── node_modules/          # Dependencies (Reveal.js)
├── index.html             # Main presentation entry point
├── package.json           # Project dependencies and scripts
├── README.md              # Setup and development instructions
└── CONTRIBUTING.md        # Development workflow guidelines
```

## Key Development Commands

### Starting Development
```bash
# Standard server (manual refresh)
npm start

# Live-reload server (auto refresh) - PREFERRED for development
npm run dev

# Access presentation at: http://localhost:8080
```

### Dependencies
- **reveal.js**: ^4.6.1 (presentation framework)
- **http-server**: ^14.1.1 (development server)
- **live-server**: ^1.2.2 (live-reload server)

## Content Guidelines

### Content Philosophy
- **Business-first language**: Avoid technical jargon, focus on business value
- **Practical examples**: Use real business scenarios (customer service, sales, marketing)
- **Progressive learning**: Start simple, build complexity gradually
- **Visual approach**: Emphasize diagrams and screenshots over text

### N8N-Specific Terminology (Keep Unchanged)
- "Node" - core N8N concept, keep as-is
- "Execution" - N8N workflow run, keep as-is
- "Workflow" - central concept, keep as-is

### Business-Friendly Triggers (Preferred)
- Google Sheets (for team data input)
- Telegram (for customer communication)
- Google Calendar (for meeting automation)
- Avoid: Manual, Webhook, Schedule, Polling triggers

### Slide Structure Pattern
```markdown
# Section Title

---

## Slide Title

![Image Description](path/to/image.png)
<!-- Placeholder: Image description for missing images -->

- Bullet point with business value
- Real-world example
- Practical benefit

Note:
Speaker notes for context and additional explanation

---
```

## Git Workflow

### Branch Naming
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation updates
- `refactor/` - Content reorganization

### Commit Messages (Conventional Commits)
```bash
feat: add webhook trigger configuration slides
fix: correct markdown formatting in introduction
docs: update README with new setup instructions
refactor: reorganize slide sections for better flow
```

### Current Branch Context
- Main development happens on `docs/add-n8n-tutorial-slides`
- Repository: https://github.com/imam/n8n-workshop
- Always commit and push changes when tasks are complete

## File Modification Guidelines

### slides.md Files
- Use business scenarios over technical examples
- Include placeholder comments for missing images
- Add speaker notes for additional context
- Keep sections focused and concise

### Image Management
- Add descriptive filenames
- Optimize for web (< 2MB per image)
- Use 1920x1080 resolution for consistency
- Include meaningful alt text

### HTML/CSS Changes
- Minimal changes to index.html unless necessary
- Custom styling goes in assets/css/custom.css
- Preserve Reveal.js configuration settings

## Common Tasks

### Adding New Content
1. Edit appropriate day-X/slides.md file
2. Add images to day-X/images/ directory
3. Test with `npm run dev`
4. Follow commit conventions
5. Push changes

### Troubleshooting
- **Slides not updating**: Check cache busting in index.html
- **Images not loading**: Verify path in markdown and file existence
- **Navigation issues**: Check slide separator syntax (`---`)

## Business Context

### Day 1 Focus
- Introduction to automation benefits
- Basic workflow concepts
- Simple triggers (Google Sheets, Telegram, Calendar)
- Credential management (simplified as "connecting apps")
- First automation exercise (newsletter signup)

### Day 2 Focus
- Data flow and transformation
- Conditional logic and branching
- Popular business nodes
- LLM/AI integration for business automation
- Advanced exercises (customer support, e-commerce)

### Content Evolution
Recent major refactor moved content from developer-focused to business-focused based on PR feedback. Always maintain this business-first approach in future modifications.

## Technical Architecture

### Reveal.js Configuration
- Markdown-driven slides with external file loading
- Cache busting for development
- Plugin support: Notes, Highlight, Zoom, Markdown
- PDF export capability (1920x1080)
- Touch and navigation controls enabled

### Development Server
- Port 8080 default
- Live-reload capability with live-server
- Manual refresh option with http-server
- Cross-platform compatibility

This context should provide sufficient information for effective collaboration on the N8N tutorial slides project.