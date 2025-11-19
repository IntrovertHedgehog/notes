## system & util
`gdu` scan disk space from cwd
`du -d 1` scan dir space with depth 1
`df` check disk space
`wc -l <file or pipe>` count number of line
`lspci` list PCI (peripheral component interconnect) - devices connected to PIC slots
`free -h` check free ram
`cat /etc/os-release` check distro info
`cat /sys/class/power_supply/BAT0/power_now` power consumption in microwatt
`sudo powertop` to measure power consumption, need to be off AC. `--calibrate` to cali, `--auto-tune` to turn all option to good, see more in wiki
`tee <file>` read from stdin and write to file and stdout (better than redir)
`iftop -P -i wlan0` see wifi (wlan0) traffic, showing local ports (-P)
`watch -c -n 0.5 command` -c for color, -n for time
`find dir -name pattern -type d -depth 12`
`top -b` batch mode for top 
`pactl set-default-sink <sink-name>` set playing sound device 
`bluetoothctl pair/connect <shit>` turn on bluetooth first
`xrandr --output HDMI --mode 1920x1080 --right-of eDP` turn on HDMI device
`compgen -c` list all available command, `-abk -A function` alias, builtins, keyword, functions
`compgen -A function -abck` list all thing can run
`udunits2` unit conversions
`xev` read input keys
`xeyes` eyes
`xclock` clock
`dex` generate execute/autostart desktop entry files (for desktop env)
`evtest` device testing, events may not show when it's grabbed by other processes, go to tty helps
`inxi -exz` display system info, expanded, extra info, z filter private info
`inxi -b` basic info
`lsblk` list block device
`blkid` get block id
`fsck` check filesystem
`tar -zxfv file -C dest` gzip, xtract, file, verbose, dest
`tar -zcf`gzip, create, file
`tar -af` append, file
`tar -df` delete, file
`disown` detach process
`sensors` cpu temphttps://wiki.archlinux.org/title/Power_management/Suspend_and_hibernate#Hibernation
`nice CMD` modify scheduling priority 
`uname -a` kernel version
`chattr` modify file attributes
`brightnessctl` brightness (backlight) adjustment
`pmap <pid>` see virtual memory mapping
`wmctrl -x -l` check application name

## docker
`docker stop $(docker ps -a -q -f status=exited)` stop docker container
`docker rmi -f $(docker images -f dangling=true -q)`rm docker images
`docker system prune` clean total
`docker image save <name> > file.tar` save image
`docker image load -i file.tar` load image
`docker run -d empower-plus/dep:latest tail -f /dev/null` spawn a container from image with no exec
`docker exec -it <container> <cmd>` run cmd in container

`gzip -dk file` -d to decompress and delete .gz, -k to keep

## packages, check out more on wiki
`pkgfile name` to find which package contains the file with that name
`pacman -Sy --noconfirm name` to update db file and install package, no confirmation
`pacman -Rs name` remove recursive (dependencies not depended on by other pkg)
`paccache -rk1` rm cached pkgs, keeping only 1 old version
`pacman -Sc` clean cache of uinstalled pkg
`sudo pacman -Rsn $(pacman -Qdtq)` remove orphans (uneeded deps)
`pacman -Qi pkg` info 
`pacman -Qe` explicitly installed pkg
`pacman -Qs pattern` search
`pacman -F file` query the file database

## tmux
`tmux send-keys -t "side:5.3" echo somthing`
`tmux set-buffer`
`tmux capture-pane -e -p -t {pane_name}`
`tmux join-pane -s sess:win.pane` move src pane to this pane (join, not replace)
`tmux join-pane -t sess:win.pane` same except move this pane to target
`tmux break-pane` put pane into a new window

`pgrep -P pid` to get child process of pid

## git
`git reset` unstage all changes
`git reset HEAD~n` undo the commit but don't change files on disk
`git reset --hard HEAD` undo commit and remove changes
`git restore .` discard unstaged files
`git clean` remove untracked files, `-f -d -x -X`: force, rmdir, rm ignored, only rm ignored
`git gc && git count-objects` gc to do maintenance, count-objects does what it says
`git checkout branch/commit -- path/to/file` checkout file from...

# devel
`cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=1` generate support files for clangd from cmake
`vcpkg new --application` init 
`vcpkg add port <pkg>` project's manifest
`vcpkg install <pkg>` install to local


# utils
`netstat -lnp` find process bound to a port, add `-t` to find tcp only
`ps -p<pid>` to find command initiated process with pid
`ps -d` list all process except session leader
`pgrep <command>` get process with name
`kill -TERM <pid>` kill proc with pid
`fuser PORT/tcp` kill proc bound to port (tcp or udp)
`sed -E -i "<first>,<last>s/pattern/replacement" **/*.py` replace (i)nplace the file by substitute pattern in the range for all python files, `-E` for extended regex
  - `sed --separate -n -E -e "s/pattern/subtitute/;p" **/*.py -i`: separate files, do not print lines (so it doesn't print original lines), use extended regex, script attempts subtitute then print result for all python files, in place. Use for final
  - `sed --separate -n -E -e "s/pattern/subtitute/p" **/*.py`: sep file, no print, extended regex, subtitute and print **only when matched**. Use for preview

## music
`spotdl <sync> url` download or sync playlist
`kew` play music

## others
`calcurse` calendar
`newsboat` news from rss
`pdftk` tinkering with pdf files (black magic)
`pdftk input_pdf input_pw <pwd> output out.pdf` - remove pwd from pdf
`perl-rename` rename multiple files perl regex

## network
### client
`eval $(ssh-agent)` + `ssh-add` to add identity
`ssh username@host` options: `-A` auth forward `-X` x11 forward `-L local:port:host:port` connection to (local) addr1 is forwarded to (host) addr2
`curl -O link` download and save content to same file name as remote
`curl link -D file` dump header
`wget -b url -O file`, download file, background, name `file`
`wget -i input`, input is list of url, `-` for stdin,
    + `--force-html` retrieves resources. add `<base href=url>` to html to fix relative links
`sshfs usr@host mountpoint` mounting ssh fs

### nettools
`nbtscan <ip>/xx` scan netBIOS info
`arp` address resolution protocol, private ip -> mac
`nethogs` watch process network activity
`ip route` find network route, can find router ip

### protonvpn
all following is prepended by `protonvpn`
`c -r -f --p2p` connect random | fastest | fastest p2p
`configure` change credentials
`refresh` does that
`status` exactly what it says

## texlive
`tlmgr` set up instruction on arch wiki
`latexmk -pdf -f shit.tex` gen pdf
`latexmk -c shit.tex` clean up
when package/file is missing: either `pacman -F file.sty` to find the arch pkg to intall the group with the pack or `tlmgr` to only install the package. 

## shell
`export HISTTIMEFORMAT="%d/%m/%y %T "` for history with time
`set -x` turn on tracing for bash/zsh, `set +x` turn it off
`bash -x file.sh` with `-x` is the same thing from `set`
`dirname <path>` strip last component of path

## names
mpris - media control
iptv - internet tv
m3u - media playlist format
repology - finding software version avail on distro pkg repo

kill process by name
find pid by port listening to
clean docker images
delete cache

development: c++ compiling command, docker compose running, docker run container without dockerfile and spawn a shell, nginx commands, pacman manage stuff, systemd, common directories, conda (not rlly needed), ssh stuff (port forwarding, authentication forwarding, x11), networking, disk management, chmod stuff, adb

app/screens/More/GoalSetting/index.tsx
