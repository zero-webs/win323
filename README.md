# Win323 - Windows Virtual Machine Platform

A powerful, feature-rich virtual machine platform for launching and managing Windows 10 and Windows 11 instances with advanced capabilities.

## Features

✨ **Core Capabilities**
- Full Windows 10 & Windows 11 support
- Hardware acceleration and GPU passthrough
- Memory management optimization
- Multi-core CPU configuration
- Snapshot and restore functionality
- Live migration support

🎯 **Great Features**
- **Auto-Scaling**: Automatically allocate resources based on workload
- **Network Bridging**: Seamless networking with multiple interface modes
- **Storage Management**: Dynamic disk expansion and compression
- **Performance Monitoring**: Real-time CPU, RAM, and disk metrics
- **Security Sandbox**: Isolated VM environments
- **Backup & Recovery**: Automated backup scheduling and recovery
- **Desktop Sharing**: Remote desktop access and VNC support
- **Quick Clone**: Rapid VM duplication from templates

## Project Structure

```
win323/
├── core/               # Core VM engine
├── ui/                 # Web and desktop UI
├── cli/                # Command-line interface
├── drivers/            # VM drivers and hypervisor integration
├── plugins/            # Extensible plugin system
├── docs/               # Documentation
├── tests/              # Test suite
└── examples/           # Example configurations
```

## Quick Start

### Installation

```bash
git clone https://github.com/zero-webs/win323
cd win323
npm install
```

### Create a VM

```bash
npm run cli -- create-vm --name "Windows11-Dev" --os windows11 --cpu 4 --memory 8gb
```

### Launch VM

```bash
npm run cli -- launch --name "Windows11-Dev"
```

## Requirements

- Host OS: Windows, macOS, or Linux
- CPU: Multi-core processor with virtualization support
- RAM: Minimum 8GB (16GB recommended)
- Storage: 50GB+ free space for VM images
- Hypervisor: KVM (Linux), Hyper-V (Windows), or VirtualBox compatible

## Technology Stack

- **Backend**: Node.js with TypeScript
- **Hypervisor Integration**: QEMU, KVM, Hyper-V, VirtualBox
- **UI**: React + Electron for desktop, Vue.js for web
- **Database**: SQLite for local storage
- **CLI**: Commander.js

## API Documentation

See [docs/API.md](docs/API.md) for complete API reference.

## Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## License

MIT

## Support

- 📖 [Documentation](docs/)
- 🐛 [Report Issues](https://github.com/zero-webs/win323/issues)
- 💬 [Discussions](https://github.com/zero-webs/win323/discussions)
