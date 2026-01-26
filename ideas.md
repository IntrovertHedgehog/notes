contribution:
- bpython: choosing python path and libraries, or use the (which python) command to find python. [](https://stackoverflow.com/questions/11172379/python-and-bpython-using-different-pythonpaths-in-virtualenv)
- bpython: able to fuzzy find the var
- bpython: ^w delete until non-alphanum, not whitespace
- flameshot: custom command after saving to send via kdeconnect to phone
- cpplint: when include <bits/stdc++.h> other #include warning still show up
- cpplint: always recommend using const ref parameter when make functions, even in case mutation is used in func body
- calcurse: lunar dates
- dunst: reply to msg from text app
- whatsapp/telegram cli client
- [x] florisboard: telex fix accent putting and capitalization logic (porting from unikey?)
- [x] florisboard: suggestion and shit
- file viewing mode that divides screen to see as much log as possible
- okular: pinching gesture, font size for anno while editing
- xremap: vim-like macro support
- git: when remove .gitignore, there's no way to remove the ignore on the previously ignored files

configs nvim:
- lspsaga: outline (fixbug when switch file with outline opened). Fixbug when nav to call-hierachy
- lspsaga: peek definition
- mapping: remove diagnostic text
- tmux attach: when use lock selection send, if the above line is longer and press $, the thing so short for the long line
- recognizing string literals as programming script (and attach lsp client)
- making profiles for using on termux and over connection (slow shit, mostly coloring is expensive formatting data)
- dap: temporary disable all breakpoints (or run til last)
- dap: jump to line
- nvim: search in command mode output (like :highlight or smt)
- nvim: float buffer <M--> to be able to split (by create another one and resize)
    - and maintain jump stack instead of resetting like now

engineering:
- geolocation by starwatching (not possible due to unclear sky)
- starwatching with auto starnaming
- implements SLAM on robots = make a roomba
- automatic landing unit (illegal)
- socket prog how to partially desrialize a long message 

projects:
- chatcurse
- krapka
- personal website
  - terminal on the web
- dev events calendar customizeable to interest
- scrabble solver
  - taking account of used letters, remaining letter and possible next letters
- algos:
  - efficient deletion for bin heap
- ipython and vim integration:
  - a background server to run the python shell and spit output
  - use pseudo tty to send input to the shell
  - client to received and display result
  - cmd or rpc interface for api
- wm switcher:
  - switching from i3 to plasma (kwin) without killing the open windows
  - might need to do word with display manager
  - assume they run on X11
- wikipedia:
    - cli to browse wikipedia on TUI or `-c` mode for simple intro retrieval
    - get relationship map of a person (oppenheimer -> McMahon, Acheson, Lilienthal, etc.)

learn:
- remote controls desktop, how it works
- awk scripting and history | fzf | execute chain
- cache coherence
- how does fcm work

write:
- why cache need to be small (not only econ, but phys)
- memory sharing (e.g. code sharing, might be lib call (.so))

## softwares to try out:
httpie - http client
kwrite - doc editor
lazygit - ncurses git, pretty cool
calcurse
making gtk application more presentable (okular, kwrite)
ncspot - spotify on term
netdiscover - arp discovery tools
nethogs - watch net packages from local
netcat - port scanning ig
nmap - another net tools
inetutils (pkg)
imagemagick
perl-rename
pipewire and audio systems, alsa, pulse
scrcpy - display and control android devices (i installed that, lol)
speech-dispatcher - speech synthesis
sshfs - mounting ssh into local
vifm - vi-like file manager, make it better to view images and formatted files
wireless_tools (pkg) - manipulate wireless interface
xinit
zram
dejagnu - testing other program
dex - 
apache arrow
tectonic - modern latex typsetting engine, auto download pkg when compile
trivy to scan code vuln
learn more about static code analysis, ast-grep and treesitter tooling
valgrind - debugging and profiling program. helgrind is a tool for finding thread bug
xremap - remapping keys on x, support specific application
