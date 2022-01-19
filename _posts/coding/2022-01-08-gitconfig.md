---
layout: coding_post
title: My .gitconfig
category: [Coding]
tags: [git, config, productivity]
description: my .gitconfig settings for subcommand aliases, git lfs, line ending and ignoring files.
unsplash: UT8LMo-wlyk
---

To keep it short, use cases aren't included in this post.

### Ignore files for all repos

1. Create a `~/.gitignore_global` file with these contents:
    
```bash
*~
.DS_Store
```
    
2. run `git config --global core.excludesfile ~/.gitignore_global`

### Line ending

On a **Windows** machine, set `core.autocrlf` to `true` – this converts LF endings into
CRLF when you check out code:

```bash
git config --global core.autocrlf true
```

On a **Linux** or **Mac** system that uses LF line endings, then you don’t want Git to automatically convert them when you check out files; however, if a file with CRLF endings accidentally gets introduced, then you may want Git to fix it. You can tell Git to convert CRLF to LF on commit but not the other way around by setting `core.autocrlf` to `input`:

```bash
git config --global core.autocrlf input
```

### Git LFS

```bash
git lfs install

# For repo with filesize > 128MB
git config http.version HTTP/1.1
```

There are some drawbacks on performance if `HTTP/1.1` is applied to global config.

`git config --global --add http.version HTTP/1.1`

ref:

[HTTP/2 vs. HTTP/1.1: How do they affect web performance?](https://www.cloudflare.com/en-gb/learning/performance/http2-vs-http1.1/)

### Git Aliases

- Run e.g. `git config --global alias.co checkout` to add `co` as an alias for `checkout` 
- Or edit the `~.gitconfig` file directly
    
    ```bash
    [filter "lfs"]
    	process = git-lfs filter-process
    	required = true
    	clean = git-lfs clean -- %f
    	smudge = git-lfs smudge -- %f
    [user]
    	name = Yulin Wu
    	email = darkato@icloud.com
    [alias]
    	st = status
    	co = checkout
    	br = branch
    	unstage = reset HEAD --
    	last = log -1 HEAD
    	# adds all modified files to staging and allows you to type a commit message, e.g. git ac "updated README"
    	ac = !git add -A && git commit -m
    ```
    

To run an external command, rather than a Git subcommand. In that case, you start the command with a `!` character. This is useful if you write your own tools that work with a Git repository. We can demonstrate by aliasing git visual to run `gitk`:

```bash
$ git config --global alias.visual "!gitk"
```

### My MacOS .gitconfig

```bash
[filter "lfs"]
	process = git-lfs filter-process
	required = true
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
[user]
	name = Yulin Wu
	email = darkato@icloud.com
[alias]
	st = status
	co = checkout
	br = branch
	unstage = reset HEAD --
	last = log -1 HEAD
	# adds all modified files to staging and allows you to type a commit message, e.g. git ac "updated README"
	ac = !git add -A && git commit -m
[core]
	autocrlf = input
```
