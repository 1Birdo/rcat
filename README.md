# rcat - A Modern, Memory-Safe Netcat Alternative 🦀🚀

![Rust](https://img.shields.io/badge/rust-%23000000.svg?style=for-the-badge&logo=rust&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/status-active%20development-yellow?style=for-the-badge)

A high-performance, memory-safe network utility written in Rust, combining the simplicity of classic Netcat with modern security features.

## 📦 Features

### 🔒 Security
- Memory-safe implementation (Rust)
- TLS 1.2/1.3 support via Rustls
- Certificate pinning
- Secure proxy tunneling

### ⚡ Performance
- Asynchronous I/O (Tokio runtime)
- Zero-copy data transfer
- Efficient connection handling
- Low-latency operation

### 🌐 Networking
- TCP/UDP client and server modes
- SOCKS5 and HTTP proxy support
- IPv4/IPv6 dual-stack
- Port scanning capabilities
- MITM proxy functionality

## 🚀 Installation

### Prerequisites
- Rust 1.70+ (install via [rustup](https://rustup.rs/))

### From Source
```bash
git clone https://github.com/1Birdo/rcat.git
cd rcat
```

# Install release version
```bash
cargo install --path . --locked
```

# Or build directly
```
cargo build --release
Cross-Compilation
```

# Linux target
```bash
cargo build --target=x86_64-unknown-linux-gnu --release
```
```bash
# Windows target
rustup target add x86_64-pc-windows-gnu
cargo build --target=x86_64-pc-windows-gnu --release
```

🛠️ Usage Examples
Basic Networking
```bash
# Start TCP listener
rcat -l -p 8080
```

# Connect to TCP server
```
rcat example.com 8080
```
# UDP mode
```
rcat -l -p 9000 --udp
echo "Hello" | rcat --udp localhost 9000
```

Secure Communications
# Start TLS server
```
rcat -l -p 443 --tls --cert server.pem --key server.key
```
# Connect with TLS client
```
rcat --tls example.com 443
```

Proxy Support
```bash
# SOCKS5 proxy
rcat --proxy socks5://user:pass@proxy:1080 example.com 80
```

# HTTP proxy
```
rcat --proxy http://proxy:8080 example.com 80
```

Advanced Features
# MITM proxy (transparently inspect traffic)
```bash
rcat -l -p 8080 --mitm upstream.com:443
```

# Port scanning
```
rcat --scan example.com 80-100
```
📜 Command Reference
|------------------------------|
Option	Description
-l, --listen	Listen mode (server)
-p, --port PORT	Port number
--udp	UDP mode
--tls	Enable TLS
--cert FILE	TLS certificate file
--key FILE	TLS private key
--proxy URL	Proxy server URL
--mitm HOST:PORT	MITM proxy target
--scan PORTS	Port range to scan
-v, --verbose	Verbose output
--hexdump	Show hex dump
-h, --help	Show help
|------------------------------|
