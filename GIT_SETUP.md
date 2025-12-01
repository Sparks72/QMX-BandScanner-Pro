# Git Repository Setup Guide

This guide will help you set up your QMX BandScanner Pro as a Git repository and optionally push it to GitHub.

## Initial Repository Setup

### 1. Initialize Git Repository

Open a terminal in your project directory and run:

```bash
git init
git add .
git commit -m "Initial commit: QMX BandScanner Pro v1.0.0"
```

### 2. Add Remote Repository (GitHub)

If you want to publish on GitHub:

```bash
# Create a new repository on GitHub (via web interface), then:
git remote add origin https://github.com/yourusername/qmx-bandscanner-pro.git
git branch -M main
git push -u origin main
```

### 3. Add a Git Tag for Version

```bash
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin v1.0.0
```

## Repository Structure

```
qmx-bandscanner-pro/
├── QMX_BandScanner_Enhanced_Layout__8_.html    # Main application
├── README.md                                     # Documentation
├── CHANGELOG.md                                  # Version history
├── LICENSE                                       # License file
├── .gitignore                                    # Git ignore rules
└── GIT_SETUP.md                                 # This file
```

## Recommended .gitattributes (Optional)

Create a `.gitattributes` file for consistent line endings:

```
* text=auto
*.html text eol=lf
*.md text eol=lf
*.js text eol=lf
*.css text eol=lf
```

## Common Git Workflows

### Making Changes

```bash
# Make your changes to the HTML file
git add QMX_BandScanner_Enhanced_Layout__8_.html
git commit -m "Description of changes"
git push
```

### Creating a New Version

```bash
# Update CHANGELOG.md with new version info
git add CHANGELOG.md QMX_BandScanner_Enhanced_Layout__8_.html
git commit -m "Version 1.1.0: Added feature X"
git tag -a v1.1.0 -m "Release version 1.1.0"
git push origin main
git push origin v1.1.0
```

### Branching for Features

```bash
# Create a new feature branch
git checkout -b feature/new-band-support
# Make changes...
git add .
git commit -m "Add support for 4m band"
git checkout main
git merge feature/new-band-support
git push
```

## GitHub Repository Settings

### Recommended Topics (for discoverability)
- amateur-radio
- ham-radio
- qmx
- band-scanner
- web-serial-api
- javascript
- radio-control
- spectrum-analyzer

### Repository Description
"Web-based band scanner for QMX transceivers with real-time spectrum analysis, waterfall display, and audio monitoring using Web Serial API"

### About Section
- Website: [Your personal site or QRZ page]
- Topics: amateur-radio, ham-radio, qmx, web-serial-api
- Include your callsign in the description

## Release Management

### Creating a GitHub Release

1. Go to your repository on GitHub
2. Click "Releases" → "Create a new release"
3. Choose tag version (e.g., v1.0.0)
4. Add release title: "QMX BandScanner Pro v1.0.0"
5. Copy relevant section from CHANGELOG.md
6. Attach the HTML file as a downloadable asset
7. Click "Publish release"

## Collaboration

If others want to contribute:

```bash
# They fork your repository, then:
git clone https://github.com/theirusername/qmx-bandscanner-pro.git
cd qmx-bandscanner-pro
# Make changes...
git add .
git commit -m "Fix: Improved signal detection"
git push origin main
# Then create a Pull Request on GitHub
```

## Backup and Sync

### Daily Backup
```bash
git add .
git commit -m "Daily backup: $(date +%Y-%m-%d)"
git push
```

### Clone to Another Machine
```bash
git clone https://github.com/yourusername/qmx-bandscanner-pro.git
```

## Tips

1. **Commit Often**: Make small, focused commits with clear messages
2. **Use Tags**: Tag each release version for easy rollback
3. **Update CHANGELOG**: Document all changes in CHANGELOG.md
4. **Write Good Messages**: Use descriptive commit messages
   - Good: "Fix: Correct frequency calculation for 6m band"
   - Bad: "Fixed stuff"

5. **Branch for Experiments**: Use branches for testing new features
6. **Keep README Updated**: Update documentation as features change

## License Note

Don't forget to add a LICENSE file! Common options:
- MIT License (permissive, allows commercial use)
- GPL v3 (copyleft, derivatives must be open source)
- Apache 2.0 (permissive with patent grant)
- BSD 3-Clause (permissive, simple)

Choose one that matches your goals for the project.

---

**73 and good DX!**  
Paul Mitchell - VK2AAQ
