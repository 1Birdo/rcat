# rcat 🚀

If you'd like to contribute, you can either fork the repo or suggest improvements.
## Currently in Dev 🚧

A modern, memory-safe Netcat altercative written in Rust, featuring TLS encryption and proxy support.

## 📖 Overview

rcat reimagines the classic Netcat tool with modern features and robust security. Built with Rust's safety guarantees and async runtime, it provides a reliable solution for network operations, debugging, and data transfer.

## ✨ Key Features

- 🔌 High-performance TCP/UDP client and server implementations
- ⚡ Asynchronous I/O powered by Tokio for optimal resource utilization
- 🔒 Strong TLS encryption using Rustls
- 🌐 Comprehensive proxy support (SOCKS5 and HTTP)
- 💻 Cross-platform compatibility (Windows, Linux, macOS)
- 🚄 Zero-copy data transfer for maximum efficiency
- 🛑 Clean shutdown handling with Ctrl+C
- 🛡️ Memory-safe implementation with Rust's guarantees

## 🚀 Quick Start

### 📥 Installation

Ensure you have Rust installed through [rustup](https://rustup.rs/):

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Build and install from source:

```sh
git clone https://github.com/Birdo1221/rcat
cd rcat
cargo install --path .
```
Compiling for Linux and Windows (Cross-Platform)
```sh

  Linux Build 
cargo build --release

  Cross-Compiling - Linux and Windows
cargo build --target=x86_64-unknown-linux-gnu

  Windows Build
rustup target add x86_64-pc-windows-gnu
cargo build --target=x86_64-pc-windows-gnu
```

### 📝 Common Usage Examples

**🔷 TCP Operations:**
```sh
# Start TCP server
rcat -l -p 8080

# Connect to server
rcat example.com 8080

# Transfer file
rcat -l -p 8080 > received_file
cat file_to_send | rcat example.com 8080
```

**🔶 UDP Operations:**
```sh
# Start UDP server
rcat -l -p 9000 --udp

# Send UDP datagram
echo "Hello" | rcat --udp localhost 9000
```

**🔐 Secure Communications:**
```sh
# TLS server
rcat -l -p 443 --ssl --cert cert.pem --key key.pem

# TLS client
rcat --ssl example.com 443
```

**🧑‍💻 MitM (Man-In-The-Middle) Proxy:**
```sh
rcat -l -p 8080 --mitm example.com
```


**🌍 Proxy Usage:**
```sh
# Connect through SOCKS5
rcat --proxy socks5://proxy:1080 example.com 80

# Connect through HTTP proxy
rcat --proxy http://proxy:8080 example.com 80
```

## ⚙️ Command Line Reference

| Option | Description | Example |
|--------|-------------|---------|
| `-l, --listen` | Start server mode | `rcat -l -p 8080` |
| `-p, --port PORT` | Specify port number | `rcat -p 8080` |
| `--udp` | Use UDP instead of TCP | `rcat --udp` |
| `--ssl` | Enable TLS encryption | `rcat --ssl` |
| `--cert FILE` | Specify TLS certificate | `rcat --ssl --cert cert.pem` |
| `--key FILE` | Specify TLS private key | `rcat --ssl --key key.pem` |
| `--proxy URL` | Use proxy server | `rcat --proxy socks5://proxy:1080` |
| `-v, --verbose` | Enable detailed logging | `rcat -v` |
| `-h, --help` | Show help message | `rcat --help` |

## 🔒 Security Best Practices

1. **🛡️ TLS Usage:**
   - Always use `--ssl` when transmitting sensitive data
   - Verify certificate validity in production environments
   - Keep TLS certificates and private keys secure

2. **🌐 Proxy Configuration:**
   - Prefer SOCKS5 over HTTP proxies for enhanced security
   - Verify proxy server trustworthiness
   - Use encrypted proxy connections when possible

3. **🚨 General Security:**
   - Avoid running with root/administrator privileges
   - Use firewall rules to restrict access when running servers
   - Monitor connections in verbose mode when debugging

## ⚡ Performance Considerations

- Zero-copy data transfer minimizes memory usage
- Async I/O reduces system resource consumption
- Efficient handling of multiple concurrent connections
- Minimal overhead compared to traditional Netcat

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments
- Original Netcat tool by Hobbit
- Nmap Project's Ncat implementation
- Tokio async runtime maintainers
- Rustls TLS library contributors
- The Rust community for crates and tools
---

*For bug reports and feature requests, please open an issue on GitHub.* 🐛
