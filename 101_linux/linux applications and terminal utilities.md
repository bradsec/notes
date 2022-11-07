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

```bash
# Fix for bat command not found
mkdir -p ~/.local/bin
ln -s /usr/bin/batcat ~/.local/bin/bat
```

**yt-dlp**
- A youtube-dl fork with additional features and fixes
- Written in Python
- Source: https://github.com/yt-dlp/yt-dlp
```bash
# Option 1 - Install using Python pip
pip install yt-dlp

# Option 2 - Install latest version from developer using curl
sudo curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/youtube-dl

# Option 3 - 
sudo wget https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -O /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp

# Check installation and version
yt-dlp --version

# Fix for /usr/bin/env: ‘python’: No such file or directory
sudo ln -s /usr/bin/python3 /usr/bin/python

# Usage examples

# List available formats
yt-dlp --list-formats https://thisvideourl

# Get link with best video and audio stream. Name file with video id and extension.
yt-dlp -f 'bv*+ba' https://www.youtube.com/watch?v=aPlC-RXq-dk -o '%(id)s.%(ext)s'

# Best audio only into mp3 file.  Name file with video id and extension.
yt-dlp -f 'ba' -x --audio-format mp3 https://source-url -o '%(id)s.%(ext)s'
```

**youtube-dl** 
- Not as up to date as yt-dlp
- Slower than yt-dlp when tested on 16 Oct 2022
- Command-line program to download videos from YouTube.com and other video sites
- Written in Python
- Source: https://github.com/ytdl-org/youtube-dl/
```bash
# Option 1 - using apt install (not latest version)
sudo apt install youtube-dl

# Option 2 - Install latest version from developer using curl
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl

# Option 3 - Install latest version from developer using wget
sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl

# Check installation and version
youtube-dl --version

# Fix for /usr/bin/env: ‘python’: No such file or directory
sudo ln -s /usr/bin/python3 /usr/bin/python
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
```bash
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
```bash
# Check install command at https://www.rust-lang.org/tools/install
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
"$HOME/.cargo/env"
```


