# GitHub Copilot Instructions for Resume Repository

## Project Overview
This repository contains a resume in the JSONResume format. It uses the resume-cli tool to generate HTML and PDF versions of the resume from the `resume.json` file.

## Technology Stack
- **Node.js**: Runtime environment (using Node 20 as specified in .nvmrc)
- **Package Manager**: Yarn (preferred) or npm
- **Resume Tool**: resume-cli with JSONResume format
- **Themes**: 
  - Kendall theme for HTML output
  - Stack Overflow theme for PDF output
- **CI/CD**: GitHub Actions for automated resume generation

## Repository Structure
- `resume.json`: The source resume data in JSONResume format
- `index.html`: Generated HTML version of the resume
- `resume.pdf`: Generated PDF version of the resume
- `.github/workflows/generate-resume.yml`: CI/CD workflow for automated generation

## Build and Development

### Installing Dependencies
```bash
yarn install --ignore-engines
# or
npm install
```

Note: The `--ignore-engines` flag is used because resume-cli has outdated engine requirements but still works with newer Node versions.

### Generating Output Files
```bash
# Generate HTML version
yarn html
# or npm run html

# Generate PDF version
yarn pdf
# or npm run pdf
```

### Testing Changes
When modifying `resume.json`:
1. Validate the JSON syntax
2. Run `yarn html` to generate HTML and verify formatting
3. Run `yarn pdf` to generate PDF (requires Chromium/Chrome for puppeteer)

## JSONResume Format
The `resume.json` file follows the JSONResume schema (https://jsonresume.org/schema/). Key sections include:
- `basics`: Personal information and contact details
- `work`: Work experience entries
- `education`: Educational background
- `skills`: Technical skills grouped by category

## Automated Workflow
The GitHub Actions workflow (`.github/workflows/generate-resume.yml`) automatically:
1. Triggers on changes to `resume.json` or the workflow file itself
2. Installs dependencies and Chrome/Chromium for PDF generation
3. Generates both HTML and PDF versions
4. Commits and pushes the updated files back to the repository

## Guidelines for AI Assistants

### When Editing resume.json
- Maintain the JSONResume schema structure
- Keep formatting consistent with existing entries
- Preserve all existing data unless explicitly asked to change it
- Validate JSON syntax before committing
- Generate updated HTML/PDF files after changes

### When Modifying Build Process
- Test changes with both yarn and npm if applicable
- Ensure compatibility with the GitHub Actions workflow
- Consider Puppeteer/Chrome requirements for PDF generation

### Code Style
- Use 2-space indentation for JSON files (consistent with existing files)
- Keep JSON properly formatted and readable
- Follow existing patterns for dates (YYYY-MM-DD format)

## Security Considerations
- Don't commit any secrets or sensitive data
- The repository contains public resume information intended for sharing
- Review personal information carefully before committing changes
