# SillyPort

> **A Chrome Extension Migration of SillyTavern**  
> LLM Frontend for Power Users - Reimagined for the Browser

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Project Status: In Development](https://img.shields.io/badge/Project%20Status-In%20Development-yellow.svg)]()

## 🚧 **Current Status: Codebase Hollowing Phase**

**⚠️ IMPORTANT NOTICE:** This repository is currently undergoing a major architectural transformation. We are systematically converting the original SillyTavern Node.js server application into a Chrome browser extension.

### What's Happening Now
- 🔄 **Phase 1: Codebase Hollowing** - Removing server-side dependencies
- 📋 **Documentation-Driven Removal** - Each removed component is documented with replacement plans
- 🏗️ **Architecture Redesign** - Transitioning from client-server to extension-only architecture
- 💾 **Complete Backup Available** - Original codebase preserved in `.project/sillytavern-backup/`

## 📖 Project Overview

**SillyPort** is a Chrome extension adaptation of [SillyTavern](https://github.com/SillyTavern/SillyTavern), designed to bring powerful LLM interaction capabilities directly to your browser without requiring a local server.

### Key Differences from SillyTavern
| Feature | SillyTavern | SillyPort |
|---------|-------------|-----------|
| **Architecture** | Node.js Server + Web Frontend | Chrome Extension Only |
| **Installation** | Local server setup required | Simple browser extension install |
| **Data Storage** | File system | Chrome extension storage |
| **API Access** | Server-side proxy | Direct API calls with CORS handling |
| **Portability** | Requires Node.js environment | Runs anywhere Chrome runs |

## 🎯 Project Goals

1. **Zero-Setup Experience** - Install and use immediately, no server configuration
2. **Full Portability** - Works on any device with Chrome browser
3. **Core Feature Preservation** - Maintain 80%+ of SillyTavern's functionality
4. **Enhanced Security** - Leverage Chrome's security model
5. **Simplified Distribution** - Chrome Web Store deployment

## 🏗️ Migration Architecture

### Current Phase: Hollowing Out
We are systematically removing server-side components while documenting replacement strategies:

```
Original SillyTavern          →    SillyPort Extension
├── src/ (Node.js server)     →    🗑️  REMOVED → Direct API calls
├── public/ (Frontend)        →    ✅  ADAPTED → Extension UI
├── Server endpoints          →    🗑️  REMOVED → Chrome storage + APIs
├── File system storage       →    🔄  MIGRATING → chrome.storage.*
├── Express.js middleware     →    🗑️  REMOVED → Extension permissions
└── Plugin system            →    🔄  REDESIGNING → Built-in modules
```

### Target Extension Structure
```
extension/
├── manifest.json             # Extension configuration
├── background.js             # Service worker
├── popup/                    # Quick access UI
├── options/                  # Main application UI
├── lib/                      # Core libraries
│   ├── extension-storage.js  # Chrome storage wrapper
│   ├── api-client.js         # Direct API client
│   └── utils.js              # Utility functions
├── scripts/                  # Adapted frontend scripts
└── assets/                   # UI resources
```

## 📚 Documentation & Planning

### Key Documents
- 📋 **[Migration Analysis](.project/chrome-extension-migration.md)** - Comprehensive migration strategy
- 🔧 **[Hollowing Plan](.project/codebase-hollowing-plan.md)** - Step-by-step removal process
- 💾 **[Backup Info](.project/backup-info.md)** - Original codebase preservation details

### Removal Documentation
As we remove components, we create detailed documentation explaining:
- **What was removed** and why
- **Original functionality** and purpose
- **Replacement strategy** for Chrome extension
- **Contribution opportunities** for developers

## 🤝 Contributing

### Current Contribution Opportunities
1. **Review Migration Plans** - Provide feedback on architectural decisions
2. **API Integration** - Help implement direct API clients for LLM providers
3. **Storage Migration** - Assist with Chrome storage implementation
4. **UI Adaptation** - Help adapt the interface for extension context
5. **Testing** - Test functionality as features are migrated

### Development Setup
```bash
# Clone the repository
git clone https://github.com/ZillyOS/SillyPort.git
cd SillyPort

# Install dependencies (client-side only)
npm install

# Access original codebase for reference
cd .project/sillytavern-backup/
```

### Contribution Guidelines
- 📖 Read the migration documentation before contributing
- 🔍 Check existing removal documentation for context
- 💬 Discuss major changes in issues before implementation
- ✅ Follow the established documentation-driven removal process

## 🗺️ Roadmap

### Phase 1: Core Hollowing (Weeks 1-2) - **IN PROGRESS**
- [x] Create comprehensive backup
- [x] Document migration strategy
- [ ] Remove server infrastructure
- [ ] Clean up dependencies
- [ ] Create removal documentation

### Phase 2: Frontend Adaptation (Weeks 3-4)
- [ ] Implement Chrome storage system
- [ ] Create direct API clients
- [ ] Adapt UI for extension context
- [ ] Build basic extension manifest

### Phase 3: Feature Migration (Weeks 5-8)
- [ ] Migrate character management
- [ ] Migrate chat system
- [ ] Migrate settings system
- [ ] Implement core extensions

### Phase 4: Polish & Release (Weeks 9-10)
- [ ] Optimize bundle size
- [ ] Implement error handling
- [ ] Add extension-specific features
- [ ] Prepare Chrome Web Store submission

## ⚠️ Important Notes

### For Users
- **This is not ready for use yet** - We're in active development
- **Original SillyTavern** - Use the [official SillyTavern](https://github.com/SillyTavern/SillyTavern) for production needs
- **Follow Development** - Watch this repo for updates on progress

### For Developers
- **Backup Available** - Complete original codebase in `.project/sillytavern-backup/`
- **Git Tag** - `pre-extension-backup` marks the pre-migration state
- **Documentation First** - All removals are documented before deletion
- **Incremental Process** - Changes are made systematically with full documentation

## 📄 License

This project is licensed under the GNU Affero General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **SillyTavern Team** - For creating the amazing original application
- **Contributors** - Everyone helping with the Chrome extension migration
- **Community** - For feedback and support during the transition

---

**🔗 Links:**
- [Original SillyTavern](https://github.com/SillyTavern/SillyTavern)
- [Migration Documentation](.project/)
- [Issue Tracker](https://github.com/ZillyOS/SillyPort/issues)

*Last Updated: December 2024* 