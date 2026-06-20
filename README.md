# git-log-osc8

Make commit hashes in `git log` clickable as OSC 8 hyperlinks. Following a
link in `less` opens `git show` for that commit.

## Install

```sh
./install
```

Then add to your shell profile or rc:

```sh
export LESS_OSC8_git='echo "handle-git-uri %o"'
```

## How it works

Two pieces, with one extra environment variable:

1. `bin/git-log-pager`: wraps commit hashes into OSC8 links.

2. `bin/handle-git-uri`: opens the OSC8 link with `git show`.

3. `LESS_OSC8_git`: tells `less` to read this value and execute its stdout as a command on `Ctrl-O Ctrl-O`.

## Navigate links

Inside `less`:

- `Ctrl-O Ctrl-N`: jump to next hyperlink
- `Ctrl-O Ctrl-P`: jump to previous hyperlink
- `Ctrl-O Ctrl-O`: open the selected hyperlink
