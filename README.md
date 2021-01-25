<h1 align="center"><code>bsymlink</code></h1>
<p align="center">Batch symlink tool that <i>SuperB</i></p>
<p align="center"><img src="https://img.shields.io/github/license/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=for-the-badge" alt="License: GPL-3.0"> <img src="https://img.shields.io/github/languages/top/NNBnh/bsymlink?logo=gnu-bash&labelColor=073551&color=4EAA25&logoColor=FFFFFF&style=for-the-badge" alt="Shell: 100%"> <img src="https://img.shields.io/badge/development-completed-%234EAA25.svg?labelColor=073551&style=for-the-badge&logoColor=FFFFFF" alt="Development completed"></p>
<p align="center"><img src="https://img.shields.io/github/watchers/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"> <img src="https://img.shields.io/github/stars/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"> <img src="https://img.shields.io/github/forks/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"> <img src="https://img.shields.io/github/issues/NNBnh/bsymlink?labelColor=073551&color=4EAA25&style=flat-square"></p>

## About
`bsymlink` is *SuperB* batch symlink tool. But unlike [**Stow**](https://www.gnu.org/software/stow), it can move conflict files to the trash.

## Contents
- [About](#about)
- [Contents](#contents)
- [Setup](#setup)
  - [Dependencies](#dependencies)
  - [Installation](#installation)
- [Usage](#usage)

## Setup
### Dependencies
- `sh` to process

### Installation
#### Manually
- Option 1: using `curl`

```sh
curl https://raw.githubusercontent.com/NNBnh/bsymlink/main/bsymlink > ~/.local/bin/bsymlink
chmod +x ~/.local/bin/bsymlink
```

- Option 2: using `git`

```sh
git clone https://github.com/NNBnh/bsymlink.git ~/.local/share/bsymlink
ln -s ~/.local/share/bsymlink/bsymlink ~/.local/bin/bsymlink
```

#### Package manager
`#TODO`

## Usage
Run `bsymlink` in the terminal:

```sh
bsymlink path/to/directory path/to/target [path/to/trash]
```

###### The default trash's path is `~/.local/share/Trash/files`

<br><br><br><br>

---

> <h1 align="center">Made with :heart: by <a href="https://github.com/NNBnh"><i>NNB</i></a></h1>
>
> <p align="center"><a href="https://www.buymeacoffee.com/nnbnh"><img src="https://img.shields.io/badge/buy_me_a_coffee%20-%23F7CA88.svg?logo=buy-me-a-coffee&logoColor=333333&style=for-the-badge" alt="Buy Me a Coffee"></p>
