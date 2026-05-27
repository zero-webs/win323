# Building Win323 from Source

## Prerequisites

- **Node.js** 16+ (https://nodejs.org)
- **npm** 8+
- **Git**
- **Python** 3.x (for some build tools)

### System-Specific Requirements

**Windows:**
- Visual Studio Build Tools or Visual Studio Community
- Windows 10/11

**macOS:**
- Xcode Command Line Tools: `xcode-select --install`
- macOS 10.13+

**Linux:**
- Build tools: `sudo apt-get install build-essential python3`
- KVM: `sudo apt-get install qemu-kvm`

## Setup

### 1. Clone Repository

```bash
git clone https://github.com/zero-webs/win323.git
cd win323
```

### 2. Install Dependencies

```bash
npm install
```

This installs:
- Electron (desktop framework)
- React (UI framework)
- TypeScript (type safety)
- Build tools

## Development

### Run in Development Mode

```bash
npm run dev
```

This:
- Watches TypeScript files for changes
- Automatically recompiles on save
- Launches Electron with hot reload
- Opens DevTools for debugging

### Build TypeScript

```bash
npm run build
```

Compiles TypeScript to JavaScript in `dist/` directory.

### Run Tests

```bash
npm test
```

Runs Jest test suite.

### Format Code

```bash
npm run format
```

Auto-formats code with Prettier.

### Lint Code

```bash
npm run lint
```

Checks code quality with ESLint.

## Building Installers

### Windows Installer

```bash
npm run package-win
```

Creates:
- `Win323-Setup-1.0.0.exe` (NSIS installer)
- `Win323-1.0.0-portable.exe` (portable version)

Located in `dist/` directory.

### macOS Installer

```bash
npm run package-mac
```

Creates:
- `Win323-1.0.0.dmg` (DMG installer)

### Linux Package

```bash
npm run package-linux
```

Creates:
- `win323-1.0.0.AppImage` (universal executable)

### All Platforms

```bash
npm run package
```

Builds for current platform.

## Project Structure

```
win323/
├── src/
│   ├── main.ts              # Electron main process
│   ├── preload.ts           # IPC security bridge
│   ├── core/
│   │   ├── vm.ts            # VM engine
│   │   └── features.ts      # Advanced features
│   ├── services/
│   │   └── vm-service.ts    # VM operations
│   └── ui/
│       ├── app.tsx          # React app root
│       ├── index.tsx        # React entry
│       ├── index.html       # HTML template
│       ├── styles.css       # Global styles
│       └── components/
│           ├── SetupWizard.tsx
│           ├── Dashboard.tsx
│           ├── VMList.tsx
│           └── VMDetail.tsx
├── docs/
│   ├── API.md
│   ├── GETTING_STARTED.md
│   └── BUILD.md
├── dist/                    # Build output
├── package.json
├── tsconfig.json
└── .gitignore
```

## Code Organization

### Core VM Engine (`src/core/vm.ts`)
- Virtual machine lifecycle management
- VM creation, launching, stopping
- Snapshot management
- Multi-VM management

### Advanced Features (`src/core/features.ts`)
- Auto-scaling based on load
- Backup and recovery
- Performance monitoring
- Network management
- VM cloning

### VM Service (`src/services/vm-service.ts`)
- Service layer for VM operations
- Configuration persistence
- Integration with core engine

### Electron Main (`src/main.ts`)
- Window management
- IPC handler setup
- Application lifecycle
- Menu creation

### React UI (`src/ui/`)
- SetupWizard: VM creation flow
- Dashboard: Main management interface
- VMList: VM listing and selection
- VMDetail: VM controls and info

## Debugging

### Enable DevTools

In development mode (`npm run dev`), DevTools opens automatically.

### View Logs

```bash
# Windows
%APPDATA%\Win323\logs

# macOS
~/Library/Logs/Win323

# Linux
~/.config/Win323/logs
```

### Debug IPC Communication

Add to `src/main.ts`:

```typescript
ipcMain.on('ANY_CHANNEL', (event, args) => {
  console.log('IPC Event:', args);
});
```

## Performance Optimization

### TypeScript Compilation

```bash
npm run build -- --incremental
```

Faster subsequent builds using incremental compilation.

### Electron Build

For production builds:

```bash
npm run build-app
```

Creates optimized React bundle.

## Troubleshooting Build Issues

### "Module not found" Error

```bash
rm -rf node_modules
npm install
```

### Compilation Fails

Check TypeScript errors:

```bash
npm run build
```

Fix any type errors shown.

### Electron Won't Start

Ensure dependencies are installed:

```bash
npm install --save-dev electron
```

### Build Fails on Windows

Install Visual Studio Build Tools:
1. Download from https://visualstudio.microsoft.com/downloads/
2. Select "Desktop development with C++"
3. Install and restart

## Release Process

### Increment Version

Edit `package.json`:

```json
{
  "version": "1.1.0"
}
```

### Build All Platforms

```bash
npm run build
npm run package
```

### Create Release

1. Commit and push changes
2. Create GitHub release with tag `v1.1.0`
3. Upload installers from `dist/` directory

## Contributing

1. Fork repository
2. Create feature branch: `git checkout -b feature/name`
3. Make changes and test: `npm run dev`
4. Run linting: `npm run lint`
5. Commit: `git commit -m "feat: description"`
6. Push: `git push origin feature/name`
7. Create Pull Request

## Additional Resources

- [Electron Documentation](https://www.electronjs.org/docs)
- [React Documentation](https://react.dev)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Node.js API](https://nodejs.org/api/)

## Support

For build issues or questions:
- Check existing [GitHub Issues](https://github.com/zero-webs/win323/issues)
- Create new issue with:
  - Your OS and version
  - Node.js version (`node -v`)
  - npm version (`npm -v`)
  - Full error message
  - Steps to reproduce
