# Download-CLI APT Repository

Welcome to the official APT repository for **Download-CLI** - a fast, multi-connection command-line file downloader with advanced background task management.

---

## Project Overview

**Download-CLI** is a comprehensive command-line file downloader inspired by aria2c, featuring multi-connection downloads, background task management, and advanced resume capabilities. This APT repository provides easy installation and automatic updates for Debian and Ubuntu-based systems.

---

## ✨ Key Features

### Core Download Features
- **Multi-connection downloads** - Use multiple simultaneous connections for faster speeds
- **Smart resume support** - Automatically resume interrupted downloads with Range requests
- **Real-time progress tracking** - Live progress bar with ETA and speed indicators
- **Browser-like headers** - Seamless compatibility with web servers
- **Custom headers support** - Add authentication tokens and custom user agents
- **SSL/TLS support** - Secure downloads with optional certificate verification

### Background Task Management
- **Background downloads** (`-bg`) - Run downloads detached from terminal
- **Task monitoring** (`--list-tasks`) - View all active background downloads
- **Progress checking** (`--task-progress <id>`) - Monitor specific download progress
- **Task control** (`--stop-task <id>`) - Stop running background downloads
- **Persistent registry** - Tasks survive across terminal sessions
- **Parallel execution** - Multiple simultaneous background downloads

### Advanced Capabilities
- **Multiple URL support** - Download several files with one command
- **Intelligent fallback** - Automatic single-connection mode for incompatible servers
- **Comprehensive logging** - Detailed logs for troubleshooting background downloads
- **Type-safe implementation** - Robust, well-tested Python codebase

---

## 🚀 Quick Installation

Add the APT repository and install Download-CLI:

```bash
# Add the repository
echo "deb [trusted=yes] https://vihaanreddym.github.io/download-cli stable main" | sudo tee /etc/apt/sources.list.d/download-cli.list

# Update package list
sudo apt update

# Install Download-CLI
sudo apt install python3-download-cli
```

Verify installation:
```bash
download-cli --version
```

---

## 📚 Usage Examples

### Basic Downloads
```bash
# Simple download
download-cli "https://example.com/file.zip"

# Multi-connection download with progress
download-cli "https://example.com/large-file.iso" -x 8 --summary

# Custom headers and output
download-cli "https://api.example.com/file.zip" \
  -H "Authorization: Bearer token123" \
  -H "User-Agent: CustomDownloader/1.0" \
  -o myfile.zip
```

### Background Downloads
```bash
# Start background download
download-cli "https://example.com/large-file.zip" -bg

# Multiple background downloads
download-cli "https://site1.com/file1.zip" "https://site2.com/file2.zip" -bg

# Monitor background tasks
download-cli --list-tasks
download-cli --task-progress 1
download-cli --stop-task 1
```

### Advanced Features
```bash
# Download with resume support
download-cli "https://example.com/huge-file.iso" -x 6
# If interrupted, run the same command to resume

# Multiple files with custom settings
download-cli \
  "https://releases.ubuntu.com/22.04/ubuntu-22.04.3-desktop-amd64.iso" \
  "https://releases.ubuntu.com/20.04/ubuntu-20.04.6-desktop-amd64.iso" \
  -x 4 -bg --summary

# Disable SSL verification for problematic sites
download-cli "https://self-signed-site.com/file.zip" --no-verify
```

---

## 🏗️ Repository Structure

```
apt-repo/
├── pool/main/           # All available .deb packages
├── dists/stable/main/   # APT metadata and indices
│   └── binary-amd64/
│       └── Packages.gz  # Package index for amd64
└── README.md           # This documentation
```

---

## 🔧 Package Information

- **Package Name**: `python3-download-cli`
- **Architecture**: `all` (platform-independent Python package)
- **Dependencies**: `python3`, `python3-requests`
- **Current Version**: `0.1.0`
- **Section**: `utils`
- **Priority**: `optional`

### Installation Locations
- **Executable**: `/usr/bin/download-cli`
- **Python Module**: `/usr/lib/python3/dist-packages/downloader_cli/`
- **Documentation**: `/usr/share/doc/python3-download-cli/`

---

## 🆕 What's New

### Version 0.1.1 Features
- ✅ **Fixed background downloads** - `-bg` flag now works correctly
- ✅ **Enhanced task management** - Robust background process tracking
- ✅ **Improved type safety** - Comprehensive type hints throughout
- ✅ **Better error handling** - Graceful handling of network and file errors
- ✅ **Advanced segmentation** - Smart multi-connection algorithm
- ✅ **Comprehensive logging** - Detailed logs for background processes

---

## 🛠️ Troubleshooting

### Common Issues

**Background tasks not working:**
```bash
# Check task registry
ls -la ~/.download-cli-tasks.json

# View background processes
ps aux | grep download-cli
```

**Downloads failing:**
```bash
# Try single connection
download-cli "URL" -x 1

# Disable SSL verification
download-cli "URL" --no-verify

# Check log files
cat filename.download.log
```

**Permission errors:**
```bash
# Ensure write permissions
chmod +w /path/to/download/directory

# Check disk space
df -h /path/to/download/directory
```

---

## 🔄 Updates & Maintenance

This APT repository is **automatically updated** via GitHub Actions CI/CD pipeline:

- ✅ **Automated builds** - New releases trigger automatic package building
- ✅ **Index generation** - `Packages.gz` files are automatically maintained
- ✅ **GitHub Pages deployment** - Repository served via reliable CDN
- ✅ **Version tracking** - Semantic versioning for easy upgrade management

### Update Schedule
- **Stable releases** - Monthly feature updates
- **Security patches** - As needed, within 48 hours
- **Bug fixes** - Weekly maintenance releases

---

## 👨‍💻 Developer Information

**Author & Maintainer**: Vihaan Reddy  
**GitHub**: [VihaanReddyM](https://github.com/VihaanReddyM)  

### Contributing
1. Fork the main repository
2. Create feature branch: `git checkout -b feature-name`
3. Submit pull request with comprehensive tests
4. Packages are automatically built and deployed

### Technical Stack
- **Language**: Python 3.6+
- **Dependencies**: `requests` library
- **Packaging**: Debian `dpkg` tools
- **CI/CD**: GitHub Actions
- **Distribution**: GitHub Pages + APT

---

## 📄 License

Download-CLI is released under the **MIT License**.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

<!-- ## 🙏 Support & Community

- **Issues & Bug Reports**: [GitHub Issues](https://github.com/VihaanReddyM/Download-CLI/issues)
- **Feature Requests**: [GitHub Discussions](https://github.com/VihaanReddyM/Download-CLI/discussions)
- **Documentation**: [Main Repository README](https://github.com/VihaanReddyM/Download-CLI#readme) -->

<!-- --- -->

*Thank you for using Download-CLI! Fast, reliable downloads with advanced task management - right from your terminal.* 🚀