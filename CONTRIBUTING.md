# Contributing to N8N Workshop

## Development Workflow

### 1. Setup Development Environment
```bash
git clone git@github.com:imam/n8n-workshop.git
cd n8n-workshop
npm install
```

### 2. Start Development Server
```bash
# Option 1: Standard server (manual refresh)
npm start

# Option 2: Live-reload server (auto refresh)
npm run dev
```

### 3. Making Changes

#### Create Feature Branch
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
# or
git checkout -b docs/documentation-update
```

#### Make Your Changes
- Edit slides in `day-1/slides.md`
- Add images to `day-1/images/`
- Update styles in `assets/css/custom.css`
- Test changes with `npm start`

#### Commit Changes
```bash
git add .
git diff --cached  # Review changes
git commit -m "feat: add new slide about advanced triggers"
```

### 4. Create Pull Request

#### Push Branch
```bash
git push -u origin feature/your-feature-name
```

#### Create PR with GitHub CLI
```bash
gh pr create --title "feat: add advanced triggers section" --body "$(cat <<'EOF'
## Description
Added new section covering advanced N8N triggers including:
- File system triggers
- Email triggers
- Custom webhook configurations

## Changes Made
- Added 3 new slides to day-1/slides.md
- Added placeholder images for trigger examples
- Updated navigation flow

## Testing
- ✅ Tested locally with npm start
- ✅ All slides render correctly
- ✅ Navigation works smoothly
EOF
)"
```

## Commit Message Convention

Use conventional commit format:

### Types
- `feat:` New features or enhancements
- `fix:` Bug fixes
- `docs:` Documentation updates
- `style:` Formatting, no code logic change
- `refactor:` Code refactoring
- `test:` Adding or updating tests
- `chore:` Maintenance tasks

### Examples
```bash
feat: add webhook trigger configuration slides
fix: correct markdown formatting in introduction
docs: update README with new setup instructions
style: improve slide typography and spacing
refactor: reorganize slide sections for better flow
chore: update dependencies to latest versions
```

## Branch Naming

### Prefixes
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation
- `refactor/` - Code refactoring
- `hotfix/` - Critical fixes

### Examples
```bash
feature/day2-content
fix/slide-navigation-bug
docs/api-integration-guide
refactor/css-structure
hotfix/image-loading-issue
```

## Code Review Process

1. **Self Review**: Review your own changes before creating PR
2. **Automated Checks**: Ensure all checks pass
3. **Peer Review**: Wait for code review approval
4. **Testing**: Verify changes work in development environment
5. **Merge**: Squash and merge when approved

## File Structure Guidelines

```
├── day-X/
│   ├── slides.md          # Main content
│   └── images/            # Section-specific images
├── assets/
│   ├── css/
│   │   └── custom.css     # Styling
│   └── images/
│       └── common/        # Shared images
├── .github/
│   ├── workflows/         # CI/CD
│   └── pull_request_template.md
└── docs/                  # Additional documentation
```

## Content Guidelines

### Slide Content
- Keep slides concise and visual
- Use bullet points for key concepts
- Include practical examples
- Add speaker notes for context

### Images
- Use descriptive filenames
- Optimize for web (< 2MB per image)
- Maintain consistent resolution (1920x1080 recommended)
- Add meaningful alt text in markdown

### Code Examples
```markdown
# Good
```bash
npm install
npm start
```

# Better with context
```bash
# Install dependencies
npm install

# Start development server with live reload
npm run dev
```
```

## Testing Your Changes

### Local Testing
```bash
# Start server
npm start

# Test in browser
open http://localhost:8080

# Check different slides
# Test navigation
# Verify images load
# Test responsive design
```

### Pre-commit Checklist
- [ ] All slides render correctly
- [ ] No broken images or links
- [ ] Navigation works smoothly
- [ ] Content is accurate and helpful
- [ ] Spelling and grammar checked
- [ ] Code examples tested

## Getting Help

- 📖 Check existing issues and PRs
- 💬 Start a discussion for questions
- 🐛 Report bugs with detailed reproduction steps
- 💡 Suggest features with use cases

## Resources

- [Reveal.js Documentation](https://revealjs.com/)
- [Markdown Guide](https://www.markdownguide.org/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub CLI Documentation](https://cli.github.com/)