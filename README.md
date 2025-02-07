# rncat - Rust Netcat Alternative

A modern, memory-safe netcat implementation with TLS/proxy support.

Features:
 ```
- TCP/UDP client/server
- Async I/O (Tokio)
- TLS encryption (Rustls)
- SOCKS5/HTTP proxies
- Cross-platform (Windows/Linux/macOS)
- Zero-copy data transfer
- Graceful Ctrl+C handling
 ```
Installation:
1. Install Rust: https://rustup.rs/
2. Build from source:
   git clone https://github.com/Birdo1221/rncat
   cd rncat
   cargo install --path .

Basic Usage:
   ```bash
   TCP Server:    rncat -l -p 8080
   TCP Client:    rncat example.com 8080
   UDP Server:    rncat -l -p 9000 --udp
   UDP Client:    echo "Hello" | rncat --udp localhost 9000
   TLS Server:    rncat -l -p 443 --ssl
   TLS Client:    rncat --ssl example.com 443
   SOCKS5 Proxy:  rncat --proxy socks5://proxy:1080 example.com 80
   HTTP Proxy:    rncat --proxy http://proxy:8080 example.com 80
   ```
Command Options:
-l/--listen  - Server mode
-p PORT      - Port number
--udp        - Use UDP
--ssl        - Enable TLS
--proxy URL  - Proxy address
-v           - Verbose output
-h           - Show help

Security Notes:
- Always use --ssl for sensitive data
- Verify certificates in production
- Prefer SOCKS5 over HTTP proxies
- Avoid running as root

Development:
Build: cargo build --release
Test: cargo test -- --test-threads=1
Contribute: Fork repo → Create branch → PR

License: MIT

Acknowledgments:
- Original Netcat by Hobbit
- Nmap Project's Ncat
- Tokio & Rustls maintainers
