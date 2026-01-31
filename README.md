# httpfuzz(beta)

Lightweight HTTP content discovery tool written in Bash.

The project focuses on understanding and automating common web enumeration techniques used during reconnaissance and CTF-style assessments. It is intentionally minimalistic and relies only on standard Unix tools.

---

## Features

* Concurrent HTTP requests using Bash job control
* Graceful shutdown with signal handling (CTRL+C)
* Custom wordlist support
* Basic argument validation
* Colored and readable output
* Works with both HTTP and HTTPS targets

---

## Usage

```bash
./httpfuzz.sh -u <url> -w <wordlist>
```

### Arguments

* `-u` — target base URL (e.g. `https://example.com`)
* `-w` — path to wordlist file

Example:

```bash
./httpfuzz.sh -u https://example.com -w common.txt
```

---

## How it works

* Reads entries line-by-line from the provided wordlist
* Appends each entry to the target URL
* Sends HTTP requests using `curl`
* Prints HTTP status codes for discovered paths
* Limits the number of parallel requests to avoid overwhelming the target

The tool is designed to keep logic transparent and easy to audit.

---

## Requirements

* Bash (tested on GNU Bash)
* curl
* Unix-like environment (Linux / macOS)

---
