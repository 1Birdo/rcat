# 🦀 rncat - Modern Netcat Replacement in Rust

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Crates.io](https://img.shields.io/crates/v/rncat)](https://crates.io/crates/rncat)
[![CI Status](https://github.com/Birdo1221/rncat/actions/workflows/ci.yml/badge.svg)](https://github.com/Birdo1221/rncat/actions)

A memory-safe, feature-rich alternative to netcat with modern protocol support, built with Rust.

## Features ✨

- **Secure Communication**
  - TLS 1.2/1.3 encryption via Rustls
  - Certificate verification with OS root certificates
  - Chacha20/Poly1305 cipher support
- **Network Protocols**
  - TCP/UDP client and server modes
  - IPv4/IPv6 dual-stack support
  - SOCKS5 (with authentication) and HTTP proxy support
- **Performance**
  - Async I/O using Tokio runtime
  - Zero-copy data transfer between connections
  - Efficient memory management
- **Usability**
  - Cross-platform (Windows/Linux/macOS)
  - Graceful shutdown with Ctrl+C handling
  - Verbose logging (-v/-vv flags)
  - Interactive mode with line buffering

## Installation 📦

### Pre-built Binaries
Download latest release from [GitHub Releases](https://github.com/Birdo1221/rncat/releases)

### From Source
```bash
# Install Rust (via rustup)
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Build and install
cargo install --git https://github.com/Birdo1221/rncat
