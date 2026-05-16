# rgrep

A simple grep-like CLI tool written in Rust that recursively searches files using regex patterns.

## Features

- Recursive directory traversal
- Regex-based search
- Invert match (`-v`)
- Count matches (`-c`)
- Print matching filenames only (`-l`)
- Displays filename and line number

---

## Dependencies

Add to `Cargo.toml`:

```toml
[dependencies]
regex = "1"
walkdir = "2"
```

---

## Usage

```bash
cargo run -- [OPTIONS] <pattern> <path>
```

### Options

| Flag | Description |
|------|-------------|
| `-v` | Invert match |
| `-c` | Show match count |
| `-l` | Show matching filenames only |

---

## Examples

### Basic Search

```bash
cargo run -- hello .
```

### Invert Match

```bash
cargo run -- -v hello .
```

### Count Matches

```bash
cargo run -- -c error .
```

### Print Matching Filenames

```bash
cargo run -- -l TODO .
```

---

## Example Output

```text
src/main.rs:42: let regex = Regex::new(pattern);
src/lib.rs:15: println!("match found");
```

---

## Build Release Binary

```bash
cargo build --release
```

Run binary:

```bash
./target/release/rgrep error .
```
  
