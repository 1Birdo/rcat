# rncat - A Rust-Based Netcat Alternative

**A modern, memory-safe Netcat implementation with TLS and proxy support.**

## Features
- **TCP/UDP client & server**
- **Asynchronous I/O** (Powered by Tokio)
- **TLS encryption** (via Rustls)
- **SOCKS5 & HTTP proxy support**
- **Cross-platform compatibility** (Windows, Linux, macOS)
- **Zero-copy data transfer** for efficiency
- **Graceful termination** with `Ctrl+C`

## Installation

### Prerequisites
Ensure you have Rust installed:
- Install Rust via [rustup](https://rustup.rs/):
  ```sh
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
  ```

### Build from Source
```sh
# Clone the repository
📌 git clone https://github.com/Birdo1221/rncat
cd rncat

# Install rncat globally
cargo install --path .
```

## Basic Usage

### TCP Mode
```sh
# Start a TCP server on port 8080
rncat -l -p 8080

# Connect to a TCP server
rncat example.com 8080
```

### UDP Mode
```sh
# Start a UDP server on port 9000
rncat -l -p 9000 --udp

# Send a UDP message
echo "Hello" | rncat --udp localhost 9000
```

### TLS Mode
```sh
# Start a TLS-encrypted server
rncat -l -p 443 --ssl

# Connect with TLS encryption
rncat --ssl example.com 443
```

### Proxy Support
```sh
# Use a SOCKS5 proxy
rncat --proxy socks5://proxy:1080 example.com 80

# Use an HTTP proxy
rncat --proxy http://proxy:8080 example.com 80
```

## Command Options
| Option       | Description                  |
|-------------|------------------------------|
| `-l, --listen` | Run in server mode          |
| `-p PORT`     | Specify the port number      |
| `--udp`       | Enable UDP mode              |
| `--ssl`       | Enable TLS encryption        |
| `--proxy URL` | Specify a proxy address      |
| `-v`         | Enable verbose output        |
| `-h`         | Show help information        |

## Security Notes
- **Always use `--ssl` for sensitive data.**
- **Verify TLS certificates** before using in production.
- **Prefer SOCKS5 over HTTP proxies** for security.
- **Avoid running as root** to minimize risk.

## Development
```sh
# Build the project
cargo build --release

# Run tests
cargo test -- --test-threads=1

# Contribute
# 1. Fork the repo
# 2. Create a feature branch
# 3. Submit a Pull Request
```

## License
This project is licensed under the **MIT License**.

## Acknowledgments
- **Original Netcat** by Hobbit
- **Nmap Project’s Ncat**
- **Tokio & Rustls maintainers**

