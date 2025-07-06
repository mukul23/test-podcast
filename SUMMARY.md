# Podcast Project Summary

## Project Overview
Created a self-hosted podcast website with RSS feed and episode management functionality, deployed on GitHub Pages.

## Current Status
- **Website URL**: https://mukul23.github.io/test-podcast/
- **RSS Feed URL**: https://mukul23.github.io/test-podcast/podcastv3.xml
- **Podcast Name**: "Manik Private Podcast"
- **Current Version**: v9.1

## Architecture
- **Frontend**: HTML/CSS/JavaScript hosted on GitHub Pages
- **RSS Feed**: XML file compliant with Apple Podcasts 2025 specification
- **Audio Hosting**: Dropbox for large files, GitHub for smaller files
- **Repository**: https://github.com/mukul23/test-podcast

## Key Features Implemented

### 1. RSS Feed (podcastv3.xml)
- Apple Podcasts 2025 compliant with all required namespaces
- iTunes tags: author, summary, image, category, episodeType, explicit
- Proper GUID format with isPermaLink="false"
- XML character encoding (&apos; for apostrophes)
- Self-referencing atom:link

### 2. Website (index.html)
- Responsive design with audio players
- Password protection overlay (password: 'dada', hash: '2eedba')
- Episode management interface with Add/Remove tabs
- Progress indicators and status messages
- Version tracking in footer

### 3. Episode Management System
- **Add Episodes**: 
  - Convert Dropbox/OneDrive URLs to direct links
  - Generate updated RSS XML and HTML
  - Download files for manual upload
- **Remove Episodes**:
  - Select episode from dropdown
  - Safety confirmation checkbox
  - Generate cleaned RSS without selected episode

### 4. Current Episodes
1. **Dada Bhagwan - Gyanvani 3** (700MB, Dropbox hosted)
   - URL: https://www.dropbox.com/scl/fi/opo4yekjw91hzsn437or9/Dada-Bhagwan-Gyanvani-3.mp3?rlkey=229392mnemsivnamoxrir9zpn&st=1y6n15rx&dl=1
   - Duration: 72:15:30
   - Has embedded chapters (works in Overcast app)

2. **History of Apple's Command Key** (17MB, GitHub hosted)
   - Local file: apple-command-key.mp3
   - Duration: 00:18:07

## Security Implementation
- **Password Protection**: Hash-based authentication (currently weak)
- **Session Storage**: Remembers auth during browser session
- **Basic Dev Tools Protection**: F12 and right-click disabled
- **Note**: Current hash is easily crackable - needs improvement

## Technical Specifications

### RSS Feed Compliance
- RSS 2.0 with iTunes, Podcast, Atom, and Content namespaces
- Required Apple Podcasts tags implemented
- GUID uniqueness enforced
- Proper enclosure tags with file size and type

### Cloud Storage Integration
- **Dropbox**: Converts dl=0 to dl=1 for direct downloads
- **OneDrive**: Adds &download=1 parameter
- **URL Validation**: Frontend checks and converts sharing URLs

### File Structure
```
/Users/mukulishwar/Documents/test podcast/
├── index.html (main website)
├── podcastv3.xml (RSS feed)
├── apple-command-key.mp3 (local audio file)
└── SUMMARY.md (this file)
```

## Workflow for Adding Episodes
1. Upload MP3 to cloud storage (Dropbox/OneDrive recommended)
2. Get sharing URL from cloud provider
3. Use website's "⚙️ Manage Episodes" → "➕ Add Episode"
4. Fill form with title, description, and cloud URL
5. System generates updated RSS and HTML files
6. Download and upload files to GitHub repository

## Known Issues & Future Improvements
1. **Security**: Password hash is easily crackable - needs proper encryption
2. **Cloud Storage**: Google Drive links don't work reliably
3. **File Sizes**: GitHub has 100MB limit, large files need external hosting
4. **Chapters**: Only work in some podcast apps (Overcast works, Apple Podcasts doesn't)

## App Compatibility
- ✅ **Overcast**: Excellent (chapters, streaming, RSS)
- ⚠️ **PocketCasts**: Good (streaming, RSS) - chapters don't show
- ❌ **Apple Podcasts**: Issues with Dropbox links and chapters

## Development History
- Started as simple RSS feed for GitHub Pages hosting
- Added episode management frontend tools
- Implemented password protection for privacy
- Updated to Apple Podcasts 2025 specification
- Switched from podcast.xml to podcastv3.xml
- Rebranded from "Tech History Podcast" to "Manik Private Podcast"

## Commands for Development
```bash
# Navigate to project
cd "/Users/mukulishwar/Documents/test podcast"

# Check git status
git status

# Commit changes
git add .
git commit -m "Description"
git push origin main

# View current files
ls -la
```

## Next Steps Suggestions
1. **Improve Security**: Implement proper password hashing
2. **Add Artwork**: Replace placeholder with actual 1400x1400px image
3. **Episode Durations**: Add actual duration calculation
4. **Backup Strategy**: Document cloud storage backup plan
5. **Analytics**: Consider adding basic usage tracking

## Context for New Claude Instance
The project is fully functional with password protection and episode management. Main remaining concern is the weak password security that should be addressed. All core podcast functionality works correctly across different apps with varying levels of compatibility.