# gif2ascii

Play GIF animations as ASCII art in your terminal.

---

<!-- demo: replace with actual recording -->
<!-- side-by-side: original GIF | ascii terminal playback -->
![demo](jim.gif)

---

## Dependencies

Only a C99 compiler and standard POSIX libraries — no external libraries required.

| Requirement | Notes |
|-------------|-------|
| `gcc` / `clang` | C99 support |
| `make` | GNU Make or compatible |
| POSIX libc | `nanosleep`, `ioctl`, `write` — present on any Linux/macOS |

On Debian/Ubuntu: `sudo apt install build-essential`

## Build

```sh
make
```

## Usage

```sh
# basic playback at terminal width
./gif2ascii input.gif

# 120 columns wide, 24-bit colour, loop forever
./gif2ascii -w 120 --color -l 0 input.gif

# half speed
./gif2ascii -w 80 -s 0.5 input.gif
```

## Options

| Flag | Description |
|------|-------------|
| `-w, --width <cols>` | Target character width (default: terminal width) |
| `-c, --color` | Enable ANSI 24-bit colour output |
| `-l, --loop <n>` | Loop count — `0` = infinite, default = GIF value |
| `-s, --scale <f>` | Timing scale — `>1` faster, `<1` slower |
