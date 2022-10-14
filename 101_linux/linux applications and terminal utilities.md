## linux applications and terminal utilities

Topics: [[linux]] [[terminal]] [[applications]] [[tools]] [[debian]]

---

Other applications/utilities already included in [debian setup notes](debian%20setup%20notes.md)

## General System Utilities

**gdu**
- Fast disk usage analyzer with console interface
- Written in Go
- Source: https://github.com/dundee/gdu
- `sudo apt install gdu`  

**lnav**
- Log file navigator
- Coloured output
- Source: https://github.com/tstack/lnav
- `sudo apt install lnav  

**ripgrep**
- Recursively searches directories for a regex pattern
- Written in Rust
- Source: https://github.com/BurntSushi/ripgrep
- `sudo apt install ripgrep`
- Note: command to run is `rg` not `ripgrep`  

**fzf**
- Terminal command line fuzzy finder
- Written in Go
- Source: https://github.com/junegunn/fzf
- `sudo apt install fzf`  

**ranger**
- Terminal filemanager
- Written in Python
- Source: https://github.com/ranger/ranger
- `sudo apt install ranger`  

**bat**
- cat command clone with wings
- syntax highlighting and line numbering 
- Written in Rust
- Source: https://github.com/sharkdp/bat
- `sudo apt install bat`  

```terminal
# Fix for bat command not found
mkdir -p ~/.local/bin
ln -s /usr/bin/batcat ~/.local/bin/bat
```

**timeshift**
- Backup restore snapshots
- Source original (no longer updated): https://github.com/teejee2008/timeshift
- Source fork maintained: https://github.com/linuxmint/timeshift
- `sudo apt install timeshift`  

**lsd**
- Enhanced next-gen ls command
- Written in Rust
- Source: https://github.com/Peltoche/lsd
- Installation using cargo (requires Rust installed)
- `cargo install lsd`  

## Random Utilities

**cointop**
- Terminal based application for tracking cryptocurrencies
- Written in Go
- Source: https://github.com/cointop-sh/cointop
- `go install github.com/cointop-sh/cointop@latest`  

## Graphics and Video Utilities

**ffmpeg**
- Video and audio conversation
- `sudo apt install ffmpeg`  

**ascii-image-converter**
- A cross-platform command-line tool to convert images into ascii art and print them on the console
- Written in Go
- Source: https://github.com/TheZoraiz/ascii-image-converter
- Installation:
```terminal
echo 'deb [trusted=yes] https://apt.fury.io/ascii-image-converter/ /' | sudo tee /etc/apt/sources.list.d/ascii-image-converter.list
sudo apt update
sudo apt install -y ascii-image-converter
```


## Programming

**Go**
- Go Programming Language
- Source: https://go.dev
- Installation as per: https://go.dev/doc/install  

**Rust**
- Rust Programming Language
- Source: https://www.rust-lang.org
- Installation:
```terminal
# Check install command at https://www.rust-lang.org/tools/install
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
"$HOME/.cargo/env"
```


