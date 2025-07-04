---
theme: ./mathema-2023
defaults:
  layout: "default-with-footer"
title: 'modern linux cli tools'
occasion: "CodeBuzz 2025"
## must be a relative path
occasionLogoUrl: "./images/logo-codebuzz.png"
company: "MATHEMA GmbH"
presenter: "Patrick Drechsler"
contact: "patrick.drechsler@mathema.de"
info: |
  ## modern linux cli tools
layout: cover
transition: slide-left
mdc: true
download: true
addons:
  - fancy-arrow

src: ./00-title.md
---

---
src: ./pages/01-intro.md
---

---
layout: two-cols
---

## "modern" is relative...

Douglas Adams

I've come up with a set of rules that describe our reactions to technologies:

<v-clicks>

- Anything that is in the world **when you're born** is normal and ordinary and is just a natural part of the way the world works.
- Anything that's invented **between when you're fifteen and thirty-five** is new and exciting and revolutionary and you can probably get a career in it.
- Anything invented **after you're thirty-five** is against the natural order of things.

</v-clicks>

::right::

<img
  class="absolute top-0 rounded-full"
  src="/images/kids-tablet-unsplash.jpg"
/>
<img
  class="absolute bottom-0 rounded-full"
  src="/images/telephone-old-unsplash.jpg"
/>

<style>
h1 {
    font-size: 26px;
}
li {
  line-height: 130% !important;
  margin: 10px 0;
}
strong {
  background-color: lightgrey;
}
img {
  width: 350px;
}

.slidev-vclick-target {
  transition: all 500ms ease;
}

.slidev-vclick-hidden {
  transform: scale(0);
}
</style>

---

## Target audience

- linux desktop CLI users
- linux admins
- docker users
- devops/cloud users
- ...

```txt
  __________________________________________
 / This is the year of linux on the desktop \
|                                            |
|          ...Windows10 has WSL ;-)          |
 \                                          /
  ------------------------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

---

## Linux tooling philosophy

- **do one thing (and only one thing!) well**
- **chaining**
- _sound familiar? (hint: functional programming...)_

---

## Why? Improvements to...

- **productivity**
  - one cli command is better than multiple clicks in a GUI
  - cli commands are reproducible and easier to document (no screenshots: remember IIS?)
- **optics**
  - "unix porn" (`PS1`, `ls`, ...)

---

## Learn the basics

VS Code is cool, but it is not a CLI tool

<div grid="~ cols-2 gap-4">
<div>

- **Emacs** and **Vim**:
  - navigation within file
  - cut, copy & paste
  - navigation between files
  - and how to exit
  - pick one and become fluent
- Learn basic cli commands: `cd`, `ls`, `cat`, `less`, `find`, `grep`, `sed`, `tail`, `awk`, `dd`, `rsync`, ...
- Combine using pipes and redirection

</div>
<div>
<div grid="~ cols-2 gap-4">
<img src="/images/emacs.png"/>
<img src="/images/Vimlogo.svg" width="120" />
</div>
</div>
</div>

<img
  class="absolute bottom-10 right-40 w-75"
  src="/images/comic-awk-grep-sed.png" />

---

## Disclaimer

.

<img
  class="absolute top-20 right-4 w-220"
  src="/images/pets-vs-cattle.png" />

---

## terminal and shell: what's the difference?

<div grid="~ cols-4 gap-4">
<div>

```sh
+--------------------+
|     "terminal"     |
+--------------------+
|                    |
|  +--------------+  |
|  |              |  |
|  |    "shell"   |  |
|  |              |  |
|  +--------------+  |
|                    |
+--------------------+
```

</div>
<div class="col-span-3">

**terminal**

- **colors** (16 or more),
- **fonts** (utf8, ligatures, emojis, ...)
- **interactions**
  - keyboard shortcuts
  - mouse interaction (copy & paste, scrolling, selection, ...)

**shell**

- **everything else** (f.ex. **`PS1`**, scripting language)

</div>
</div>

---

## terminal

**What is the best terminal?**

- start by using your default terminal

**but think about enriching your output!**

- Emojis: 👍 ✅ 💥 ✌️ 💩 € ★
- Unicode, Emojis, Fonts, Image support (!)

<img
  class="absolute bottom-20 right-4 w-130 image-with-border "
  src="/images/terminal-with-icons.png"
/>
<img
  class="absolute top-20 right-4 w-130 image-with-border "
  src="/images/terminal-with-image-support.png"
/>

---

## terminal - Retro style 🦄

- cool-retro-term: <gh-stars count="18k"/> <https://github.com/Swordfish90/cool-retro-term>

<img
  class="absolute bottom-50 left-10"
  src="/images/retro-terminal1.gif"
/>

<img
  class="absolute bottom-25 left-80"
  src="/images/retro-terminal2.gif"
/>

<img
  class="absolute bottom-5 right-5"
  src="/images/retro-terminal3.gif"
/>

---

## terminals

modern alternatives

not the topic of this talk, but...

- kitty: <gh-stars count="20k"/> <https://github.com/kovidgoyal/kitty>
- alacritty <gh-stars count="49k"/> <https://github.com/alacritty/alacritty>
- wezterm <gh-stars count="10k"/> <https://github.com/wez/wezterm>

---

## Popular shells

- bash
- zsh
- fish
- dash (embedded)

---

## nushell: The new kid on the block

Everything is data

- keep an eye on it!
  - <gh-stars count="26k"/> <https://github.com/nushell/nushell>
- 100% **NOT** POSIX conform
- category: experimental

<img
  class="absolute bottom-5 right-5 w-120"
  src="/images/nushell.gif"
/>

---

## PS1

PS1: alias for "prompt string 1"

- default: `username@machinename:~/some/location $`
- `$PWD` present working directory

Extra, nice-to-have information

- only show relevant parts (hide user/machine name on local machine)
- compact location (`$PWD`)
- git status
- environment infos (node / .NET / Java / Python / etc version)

---

## PS1: Starship

the new kid on the block

- <gh-stars count="33k"/> <https://github.com/starship/starship>
- cross-plattform, cross-shell (even Windows cmd.exe)
- stylish
- great defaults for many environments
- easy to configure
- can look like powerline
- category: unix-porn

<img
  class="absolute top-10 right-0 w-100"
  src="/images/starship-prompt.png"
/>
<img
  class="absolute bottom-10 right-5 w-100"
  src="/images/starship.gif"
/>

---

## tmux

terminal-independent shell UI

- <gh-stars count="28k"/> <https://github.com/tmux/tmux>
- terminal multiplexer
- "tabs" and "split screen" features: terminal independent
- detachable sessions
- plugin system & package manager (of course)
- customizable
- scriptable: f. ex. `tmuxinator`

---

## byobu

`tmux`-wrapper for non-vim users

- (mirrored repo: ~1k stars) <https://www.byobu.org/>
- Keybindings `F1` - `F12`
- Sensible defaults (layout, info line)
- category: productivity

---

## ⚠️ Warning about tiling everything ⚠️

don't forget about all the fun keybindings

Nesting can become a challenge...

| Abstraction level | Keybinding Brain Overload |
|-------------------|---------------------------|
| tiling **window manager** like `i3` or `sway` | 🤯 |
| tiling **terminal** like `kitty` | 🤯🤯 |
| tiling **shell** like `nushell` or `tmux` | 🤯🤯🤯 |
| **application** like `emacs` or `vim` | 🤯🤯🤯🤯 |

---

## mob 💡

Smooth git handover

- <gh-stars count="1k"/> <https://mob.sh/>
- remote ensemble or pair programming using screen sharing

<img
  class="absolute top-20 right-20 w-50"
  src="/images/mob-logo.svg"
/>

```sh
## first user
mob start 5
mob next

## second user
mob start 5
mob next

## any user, wanting to make a normal commit
mob done
```

---

## ranger

file explorer / manager

- <gh-stars count="13k"/> <https://ranger.github.io>
- 2 layout options
  - miller columns ("mac" style)
  - multipane (similar to Midnight commander)
- powerful preview mode and program launcher (word, music, ...)
  - with image support for certain terminals (`iterms2`, `urxvt`, `kitty`) not `gnome-terminal` (!)
- key bindings: see `~/.config/ranger/rc.conf` starting at line ~300...
- category: navigation, file system

---
layout: two-cols
---

## clifm

another terminal file manager

> Most terminal file managers out there (if not all) are built using the TUI design principles, much like the superb `Midnight Commander` and `Ranger`. But clifm is built rather having the CLI design principles in mind: do not navigate through a big menu of files, just type it!, exactly as you do in your regular shell, but easier and faster.
>
> For this reason, clifm does not need to be better: it's just different!

- <gh-stars count="1.1k"/> <https://github.com/leo-arch/clifm>
- `ranger` alternative
- category: navigation, file system

::right::

<img
  src="/screencasts/clifm.gif"
/>

---

## nnn

another terminal file manager

> nnn (n³) is a full-featured terminal file manager. It's tiny, nearly 0-config and incredibly fast.

- `ranger` alternative
- category: navigation, file system

<img
  class="absolute bottom-10 right-5 w-130"
  src="/screencasts/nnn.gif"
/>

---
layout: two-cols
---

## Yazi

fast terminal file manager

> Yazi ("duck" in Chinese) is a terminal file manager written in Rust, based on non-blocking async I/O. It aims to provide an efficient, user-friendly, and customizable file management experience.

- <gh-stars count="3k"/> <https://github.com/sxyazi/yazi>
- `ranger` alternative
- category: navigation, file system

::right::

<img
  class="absolute bottom-0 right-0 w-120"
  src="/images/yazi.gif"
/>

---
layout: two-cols
---

## tldr 💡

man pages can be difficult

- <gh-stars count="44k"/> <https://tldr.sh/>
- clients implemented in many languages
  - js, ruby, python, perl, haskell, etc.
- shared user-contributed knowledge-base

## Tealdeer

- <gh-stars count="2k"/> <https://github.com/dbrgn/tealdeer>
- ...in rust

::right::

<v-click>
<img
  class="absolute top-20 right-5 w-120"
  src="/images/tldr-ln.png"
/>
</v-click>
<v-click>
<img
  class="absolute top-20 right-5 w-120"
  src="/images/tldr-tar.png"
/>
</v-click>
<v-click>
<img
  class="absolute top-20 right-5 w-120"
  src="/images/tldr-scp.png"
/>
</v-click>

<style>
.slidev-code * {
    font-size: x-small
}
</style>

---

## atuin

magic shell history

- <gh-stars count="23k"/> <https://github.com/atuinsh/atuin>
- powerful history search (`ctrl+r`)
- uses SQLite under the hood
- also allows synchronizing between machines
- cross-shell
- Example: `dotnet tool`

<img
  class="absolute top-20 right-5 w-120"
  src="/images/atuin.gif"
/>

---

## zoxide

a smarter cd command, inspired by z and autojump.

- <gh-stars count="26k"/> <https://github.com/ajeetdsouza/zoxide>
- cross-shell
- interactive mode
- integrates nicely with other tools such as `fzf`, `ranger`, `yazi`, `atuin`

---

## bat 💡

`cat` & `less` with syntax highlighting

- <gh-stars count="40k"/> <https://github.com/sharkdp/bat>
- hint: can be used as preview by `ranger`...
- category: file preview

---

## ripgrep 💡

very fast `grep` replacement

- <gh-stars count="37k"/> <https://github.com/BurntSushi/ripgrep>
- `ripgrep` **recursively** searches directories for a regex pattern
- sensible defaults: respect `.gitignore`, ignores hidden files & folders
- command: `rg`
- category: search
- use `rg --hidden -g '!.git' "your search"` to search all hidden folder except `.git`
  - create an alias (maybe `rgh`?)...

---

## ripgrep-all

ripgrep, but also search in PDFs, E-Books, Office documents, zip, tar.gz, sqlite (!), etc

- <gh-stars count="5k"/> <https://github.com/phiresky/ripgrep-all>
- command: `rga`
- faster than `pdfgrep` (see website for a benchmark)
- category: search
- Demo: search in Manning books folder

---

## fd 💡

simple alternative to `find`

- <gh-stars count="27k"/> <https://github.com/sharkdp/fd>
- "The command name is 50% shorter than `find`"
- Convenient syntax `fd PATTERN` (instead of `find -iname '*PATTERN*'`)
- Sensible defaults: `.gitignore`, ignore hidden files/folders
- fast
- category: search

---

## fzf 💡

interactive fuzzy search

- <gh-stars count="51k"/> <https://github.com/junegunn/fzf>
- excellent integration with other tools: Install it and it will be used by many other tools
- `Alt+c`: quick `cd` navigation
- nice helper methods. `<cmd> **<TAB>`, for example:
  - `cd **<TAB>`
  - `ssh **<TAB>`
  - `unset **<TAB>`, `export **<TAB>`, `unalias **<TAB>`
  - `kill -9 <TAB>` careful..
- Things you can do with fzf: <https://andrew-quinn.me/fzf>
- category: search

---
layout: two-cols
---

## jq & Co

"sql for json" (and other data formats)

### jq

- lightweight and flexible command-line JSON processor
- <gh-stars count="26k"/> <https://github.com/jqlang/jq>

### jqp

- TUI for `jq`
- <gh-stars count="1.8k"/> <https://github.com/noahgorstein/jqp>

::right::

### miller

- similar to `jq`, but also for CSV, TSV, JSON, etc.
- <gh-stars count="8k"/> <https://github.com/johnkerl/miller>

### fq

- `jq`, but for binary data
- <gh-stars count="8k"/> <https://github.com/wader/fq>
- for example: audio, video, images, etc.

---
layout: image-left
image: '/images/yaml-meme.jpg'
---

### yq

- `jq`, but for YAML
- <gh-stars count="13k"/> <https://github.com/mikefarah/yq>

---
layout: screencast
image: './screencasts/out2c.gif'
---

## hyperfine

benchmarking tool

- <gh-stars count="15k"/> <https://github.com/sharkdp/hyperfine>

```sh
## comparing `fd` with `find`
hyperfine --warmup 3 \
    'fd -e jpg -uu' \
    'find -iname "*.jpg"' 
```

- category: benchmarking

---

## progress

monitor any kind of "copy"

- <gh-stars count="6k"/> <https://github.com/Xfennec/progress>
- attach to any kind of copy, even after the fact (!)
- category: monitoring

``` bash
No command currently running: cp, mv, dd, tar, cat, rsync, grep, fgrep, egrep, cut, sort, md5sum,
sha1sum, sha224sum, sha256sum, sha384sum, sha512sum, adb, gzip, gunzip, bzip2, bunzip2, xz,
unxz, lzma, unlzma, 7z, 7za, zcat, bzcat, lzcat, split, gpg, or wrong permissions.
```

---

## lolcat 🦄

Rainbows and unicorns

- <gh-stars count="5k"/> <https://github.com/busyloop/lolcat>
- category: fun, unix porn

<img
  class="absolute bottom-20 right-20 w-150"
  src="/images/lolcat-screenshot.png"
/>

---

## no-more-secrets 🦄

when the tv team comes in your office

- <gh-stars count="5k"/> <https://github.com/bartobri/no-more-secrets>
- pipe something to `nms` or just run `sneakers`
- category: fun, unix porn

<Youtube id="F5bAa6gFvLs" />

<img
  class="absolute top-5 right-0 w-100"
  src="/images/nms.gif"
/>
<img
  class="absolute top-65 right-5 w-100"
  src="/images/nms-sneakers.gif"
/>

---

## sl 🦄

- <gh-stars count="3k"/> <https://github.com/mtoyoda/sl>
- typo `sl` (instead of `ls`) -> show steam locomotive
- can we pipe it to `lolcat`? of course
- category: fun, unix porn

<img
  class="absolute bottom-0 right-0 w-130"
  src="/images/sl-demo.gif"
/>

---

## gh

GitHub CLI

- <gh-stars count="32k"/> <https://github.com/cli/cli>
- Example: push current git folder to new private github repo:
  - `gh repo create --source . --push --private`
- create PRs
- view issues

---

## ShellCheck

static analysis tool for shell scripts

- <gh-stars count="37k"/> <https://github.com/koalaman/shellcheck>
- plugins available for most IDEs
- written in Haskell ;-)

---
layout: two-cols
---

## task

- <gh-stars count="12k"/> <https://github.com/go-task/task>
- task runner / simpler Make alternative
- single binary
- cross-platform
- written in Go

::right::

```yaml
version: '3'

vars:
  GREETING: Hello, World!

tasks:
  default:
    cmds:
      - echo "{{.GREETING}}"
    silent: true

  test:
    cmds:
      - dotnet test
```

---

## pay-respects 💡

Command suggestions, command-not-found and `thefuck` replacement written in Rust

- <gh-stars count="200"/> <https://github.com/iffse/pay-respects>
- category: productivity

<img
  class="absolute bottom-0 right-0 w-150"
  src="/images/pay-respects.gif"
/>

---

## ls on steroids

`ls` problem: **sort by name and time and size** at the same time...

**Use colors!**

- `colorls` ("the original" in ruby: <https://github.com/athityakumar/colorls)>
- `lsd` (in rust: <https://github.com/Peltoche/lsd>)
- ~~`exa`~~ (in rust: <https://github.com/ogham/exa>)
- `eza` (in rust: <https://github.com/eza-community/eza>)

Required: font providing all symbols

- Example: NerdFonts <https://github.com/ryanoasis/nerd-fonts>

---

## eza 💡

- <gh-stars count="7k"/> <https://github.com/eza-community/eza>
- category: unix porn

<img
  class="absolute bottom-30 right-5 w-210"
  src="/images/eza-screenshot.png"
/>

---

## lazy*

Everything lazy*

- lazydocker
  - <gh-stars count="27k"/> <https://github.com/jesseduffield/lazydocker>
- lazygit
  - <gh-stars count="35k"/> <https://github.com/jesseduffield/lazygit>

<img
  class="absolute bottom-0 left-5 w-125"
  src="/screencasts/lazydocker.gif"
/>

<img
  class="absolute top-30 right-5 w-100"
  src="/screencasts/lazygit.gif"
/>

---

## du alternatives 💡

`du` in the name

- ncdu - we all know this
  - <https://dev.yorhel.nl/ncdu>
- <gh-stars count="2k"/> [gdu: https://github.com/dundee/gdu](https://github.com/dundee/gdu)
- <gh-stars count="6k"/> [dust: https://github.com/bootandy/dust](https://github.com/bootandy/dust)

<img
  class="absolute bottom-10 right-0 w-150"
  src="/images/dust.png"
/>

---

## hollywood 🦄

- <https://github.com/dustinkirkland/hollywood>
- random crazy stuff in the terminal
- category: unix porn
- Live demo

---

## monitoring

Everything *top

- btop 😎
- apachetop
- ngxtop
- mtp
- pg_top
- powertop
- iotop
- iftop
- nethogs

---

## Why didn't I show this presentation in a shell?

I've done it 😇

- <gh-stars count="5k"/> <https://github.com/mfontanini/presenterm>

---

## Resources

<div grid="~ cols-2 gap-4">
<div>

- <mdi-mastodon class="inline"/> <https://mastodon.social/@climagic>
- <mdi-mastodon class="inline"/> <https://mastodon.social/@nixCraft>
- <mdi-reddit class="inline"/> [r/commandline](https://www.reddit.com/r/commandline/)
- <mdi-reddit class="inline"/> [r/unixporn](https://www.reddit.com/r/unixporn/)
- search for "**awesome-cli**"

This talk was inspired by Martin Leyrer's session at [Gulaschprogrammiernacht 19 (CCC)](https://www.youtube.com/watch?v=8d8-PpcLc24&t=12s).

</div>
<div>

<img
  class="absolute top-5 right-50 w-xs"
  src="/images/twitter-climagic.png"
/>
<img
  class="absolute bottom-10 right-25 w-xs"
  src="/images/twitter-nixcraft.png"
/>

</div>
</div>

---

## I forgot your favorite tool?

<div grid="~ cols-2 gap-4">
<div>

- git-fuzzy <https://github.com/bigH/git-fuzzy>
- forgit <https://github.com/wfxr/forgit>
- mosh (robust replacement for ssh) <https://mosh.org/>
- fish_config (web-based configuration tool for fish shell) <https://fishshell.com/docs/current/commands.html#fish_config>
- xclip (cli to X clipboard) 403 stars <https://github.com/astrand/xclip>
- neofetch (fancy system info in the shell) 7.7k stars <https://github.com/dylanaraps/neofetch>
- expect <https://likegeeks.com/expect-command/>
- httpie (cli http client) 45k stars <https://httpie.org/>
- http-prompt (cli http client) 7.6k stars <http://http-prompt.com/>
- pywal (color schemes for terminal) 3.4k stars <https://github.com/dylanaraps/pywal>
- ytfzf <https://github.com/pystardust/ytfzf> find YT videos and downloads them using youtube-dl
- figlet <http://www.figlet.org/> ascii art
- toilet <http://caca.zoy.org/wiki/toilet> ascii art

</div>
<div>

- apt-iselect (interactive ncurses package search for debian) <https://www.rot13.org/~dpavlin/apt-iselect.html>
- gcalcli (google calender in the shell) 2k stars <https://github.com/insanum/gcalcli>
- pastebinit (cli tool to send data to pastebin) 17 stars <https://github.com/skorokithakis/pastebinit>
- MapSCII (ascii google maps in the terminal) <https://github.com/rastapasta/mapscii>
- alwaysontop (always move prompt to top of screen) 160 stars <https://github.com/swirepe/alwaysontop>
- wttr.in (ascii weather report) <https://github.com/chubin/wttr.in>
- gpt4free <https://github.com/xtekky/gpt4free>
- Fig <https://fig.io/> Autocomplete on-steroids
- xkcd.xsh <https://gist.github.com/Lassi-Koykka/9fb934732a871ca3c8bc9396983a3310>
- fx (json cli viewer) <https://github.com/antonmedv/fx>

</div>
</div>

<style>
li {
    font-size: 0.8rem;
}
</style>

---
src: ./pages/99-end.md
---
