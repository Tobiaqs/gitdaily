# GitDaily 0.4
This is a bash shell script that allows you to easily see the status of all of your Git repositories. If you're like me, and you keep every single project in a different repository, it can be very useful to see on which repositories you need to work.

```
$ gitdaily
```
```
───────────────────────────────────────────────────────────
  GitDaily
───────────────────────────────────────────────────────────
  dirtyrepo is not clean
    Changes not staged for commit:
      modified:   .bashrc
───────────────────────────────────────────────────────────
  66% of 3 repos clean
───────────────────────────────────────────────────────────
```

```
$ gitdaily --all --compact
```
```
───────────────────────────────────────────────────────────
  GitDaily
───────────────────────────────────────────────────────────
  dotfiles is clean
  gitdaily is clean
  dirtyrepo 1 file changed, 0 insertions(+), 0 deletions(-)
───────────────────────────────────────────────────────────
  66% of 3 repos clean
───────────────────────────────────────────────────────────
```

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
$ gitdaily --local
```

When you're in a folder and you want to see the statuses of its subdirectories (will skip non-Git folders):
```
$ gitdaily -s
$ gitdaily --subdir
```

When you just want a compact list of which repositories aren't clean:
```
$ gitdaily -c
$ gitdaily --compact
```

When you want to know where the repository resides:
```
$ gitdaily -p
$ gitdaily --parent
```

When you want to see the help:
```
$ gitdaily -h
$ gitdaily --help
```

When you need to check the version of gitdaily:
```
$ gitdaily -v
$ gitdaily --version
```

Add a custom message to the newspaper, it will display just above the footer:
```
$ gitdaily "Hello world"
$ gitdaily "$(fortune)"
```

> The flags `-l` and `-s` are mutually exclusive. `-c` can be used together with `-l` or `-s`.

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