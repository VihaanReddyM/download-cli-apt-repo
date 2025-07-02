# Download-CLI APT Repository

Welcome to the official APT repository for **Download-CLI**.

---

## Project Overview

**Download-CLI** is a fast, multi-connection command-line file downloader inspired by aria2c. It is designed for users who need efficient, reliable, and resumable downloads directly from the terminal. This repository provides a convenient way to install and update Download-CLI on Debian and Ubuntu-based systems using the APT package manager.

---

## Features

- **HTTP/HTTPS downloads** with browser-like headers
- **Segmented/multi-connection downloads** for improved speed
- **Resume support** (Range requests)
- **Real-time progress bar**
- **Custom headers** via CLI
- **Graceful interruption handling**
- **Easy installation and updates** via APT

---

## Installation

To add this repository and install Download-CLI, run:

```bash
echo "deb [trusted=yes] https://vihaanreddym.github.io/download-cli-apt-repo stable main" | sudo tee /etc/apt/sources.list.d/download-cli.list
sudo apt update
sudo apt install python3-download-cli
```

After installation, you can use the downloader:

```bash
download-cli "https://example.com/file.zip" -o file.zip -x 8 -H "User-Agent: Custom" --summary
```

---

## Usage Example

- **Basic download:**
  ```bash
  download-cli https://example.com/file.zip
  ```
- **Specify output filename:**
  ```bash
  download-cli https://example.com/file.zip -o myfile.zip
  ```
- **Use multiple connections:**
  ```bash
  download-cli https://example.com/large-file.iso -x 8
  ```
- **Add custom headers:**
  ```bash
  download-cli https://example.com/file.exe -H "User-Agent: Custom-Agent/1.0"
  ```
- **Show download summary:**
  ```bash
  download-cli https://example.com/file.dat --summary
  ```

---

## Repository Structure

- `pool/main/` — Contains all available `.deb` packages.
- `dists/stable/main/binary-amd64/Packages.gz` — APT package index for amd64 architecture.
- `README.md` — This documentation.

---

## Author & Maintainer

**Vihaan Reddy**  
GitHub: [VihaanReddyM](https://github.com/VihaanReddyM)  
Project Repository: [Download-CLI](https://github.com/VihaanReddyM/Download-CLI)

---

## Updates & Support

This APT repository will be **actively updated** with new releases, bug fixes, and feature enhancements.  
Stay tuned for improvements and additional features in future versions.

If you encounter issues or have suggestions, please open an issue or pull request on the [main project repository](https://github.com/VihaanReddyM/Download-CLI).

---

## License

Download-CLI is released under the MIT License.

---

*Thank you for using Download-CLI! Efficient downloads, right from your terminal.*