<h1 align="center"><code>bsymlink</code></h1>
<p align="center">Batch symlink tool that <i>SuperB</i></p>
<p align="center"><a href="https://github.com/NNBnh/bsymlink/blob/main/LICENSE"><img src="https://img.shields.io/github/license/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=for-the-badge" alt="License: GPL-3.0"></a> <a href="https://gist.github.com/NNBnh/9ef453aba3efce26046e0d3119dab5a7#development-completed"><img src="https://img.shields.io/badge/development-completed-%234EAA25.svg?labelColor=073551&style=for-the-badge&logoColor=FFFFFF" alt="Development completed"></a></p>
<p align="center"><a href="https://github.com/NNBnh/bsymlink/watchers"><img src="https://img.shields.io/github/watchers/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"></a> <a href="https://github.com/NNBnh/bsymlink/stargazers"><img src="https://img.shields.io/github/stars/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"></a> <a href="https://github.com/NNBnh/bsymlink/network/members"><img src="https://img.shields.io/github/forks/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"></a> <a href="https://github.com/NNBnh/bsymlink/issues"><img src="https://img.shields.io/github/issues/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"></a></p>

## 💡 About
`bsymlink` is a *SuperB* batch symlink tool written in  [`portable sh`](https://github.com/dylanaraps/pure-sh-bible). But unlike [**Stow**](https://www.gnu.org/software/stow), it can handle conflict files like move it to the trash or delete it.

## 🚀 Setup
### 🧾 Dependencies
- [Unix commands](https://en.wikipedia.org/wiki/List_of_Unix_commands) to process

### 📥 Installation
#### 🔧 Manually
Option 1: using `curl`
```sh
curl https://raw.githubusercontent.com/NNBnh/bsymlink/main/bin/bsymlink > ~/.local/bin/bsymlink
chmod +x ~/.local/bin/bsymlink
```

Option 2: using `git`
```sh
git clone https://github.com/NNBnh/bsymlink.git ~/.local/share/bsymlink
ln -s ~/.local/share/bsymlink/bin/bsymlink ~/.local/bin/bsymlink
```

#### 📦 Package manager
For [`bpkg`](https://github.com/bpkg/bpkg) user:
```sh
bpkg install NNBnh/bsymlink
```

For [Basher](https://github.com/bpkg/bpkg) user:
```sh
basher install NNBnh/bsymlink
```

> *If you can and want to port Bsymlink to other package managers, feel free to do so.*

## ⌨️ Usage
Run `bsymlink` in the terminal:
```sh
bsymlink path/to/directory path/to/target [path/to/trash]
```

## ⚙️ Configuration
This is the default handle conflict command:
```sh
BSYMLINK_HANDLE="handle_conflict \"\$target\""
```

it's use this builtin `handle_conflict` function:
```sh
BSYMLINK_TRASH_PATH="${BSYMLINK_TRASH_PATH:-${XDG_DATA_HOME:-$HOME/.local/share}/Trash/files}"

handle_conflict() {
	mkdir -p "$TRASH_PATH"
	rm -rf "$TRASH_PATH/$(basename "$target")" 2>&-
	mv -f "$target" "$TRASH_PATH/"
}
```

> *The default trash's path is `~/.local/share/Trash/files`*

You can change it through environment variables: `export BSYMLINK_HANDLE="<command>"`

> *Keep in mind that the `<method>` will be run through `eval` (e.g: `// => /`)*

Examples:

Delete conflict files:
```sh
BSYMLINK_HANDLE="rm -rf \"\$target\""
```

Using [Trash-CLI](https://github.com/andreafrancia/trash-cli):
```sh
BSYMLINK_HANDLE="trash \"\$target\""
```

## 💌 Credits
Special thanks to:
- [**Stow**](https://www.gnu.org/software/stow) by [GNU](https://www.gnu.org)

<br><br><br><br>

---

> <h1 align="center">Made with ❤️ by <a href="https://github.com/NNBnh"><i>NNB</i></a></h1>
>
> <p align="center"><a href="https://www.buymeacoffee.com/nnbnh"><img src="https://img.shields.io/badge/buy_me_a_coffee%20-%23F7CA88.svg?logo=buy-me-a-coffee&logoColor=333333&style=for-the-badge" alt="Buy Me a Coffee"></a></p>
