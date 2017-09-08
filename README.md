# GitDaily 0.3

```
┌────────────────────────────────┐
│            GitDaily            │
├────────────────────────────────┤
│ dotfiles is not clean.
├────────────────────────────────┤
│ gitdaily is not clean.
├────────────────────────────────┤
│ Sat Sep  9 13:37:00 CEST 2017  │
└────────────────────────────────┘
```


This is a bash shell script that allows you to easily see the status of all of your Git repositories. If you're like me, and you keep every single project in a different repository, it can be very useful to see on which repositories you need to work.

## Configuration
Normally, you'd have a configuration file sitting at `~/.config/gitdaily_paths`. This file should contain the paths to the repositories that you want to track. An example:

```
$HOME/repos/*
$HOME/stuff
```

This will cause GitDaily to track `~/stuff` and any subdirectory of `~/repos` that is a Git repository.

## Usage

Run according to config file:
```
$ gitdaily
```

When you're in a Git repository and you want to see its status (kind of the same as running `git status`):
```
$ gitdaily -l
```

When you're in a folder and you want to see the statuses of its subdirectories (will skip non-Git folders):
```
$ gitdaily -ls
```

When you just want a compact list of which repositories aren't clean:
```
$ gitdaily -c
```

The flags `-l` and `-ls` are mutually exclusive. `-c` can be used together with `-l` or `-ls`.

## Installation
Navigate to a directory where you'd like to keep GitDaily.

```
git clone https://github.com/Tobiaqs/gitdaily && sudo ln gitdaily/gitdaily /usr/local/bin/gitdaily && cowsay "All done!"
```

## Updating
Navigate to the directory where you keep GitDaily.

```
git -C gitdaily pull && cowsay "Updated!"
```

## Deinstallation
Navigate to the directory where you keep GitDaily.

```
sudo rm /usr/local/bin/gitdaily && rm -rf gitdaily && cowsay "GitDaily has been removed."
```