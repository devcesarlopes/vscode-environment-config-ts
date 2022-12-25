# vscode-environment-config-ts

This is a tutorial to help begginners on how to configure Visual Studio Code environment for TS developers.

## Git Shortcuts

First of all, Let's start with git. It is so boring to keep writing everytime the 3 git commands to commit you changes on repo:

* `git add .`
* `git commit -m ""`
* `git push`

Instead let's compress all that in a single command: 

` git c "comments"`

To do that, we can create an `[ALIAS]` to create a custom command on git, so, go to the global `gitconfig` file.

* Windows : `C:\Git\etc\gitconfig`
* Linux: `cd ~ | ls -alrt | open .gitconfig`
* Mac : `/usr/local/git/etc/Gitconfig`

The file will look like this:

```
[diff "astextplain"]
	textconv = astextplain
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
[http]
	sslBackend = openssl
	sslCAInfo = D:/Git/mingw64/ssl/certs/ca-bundle.crt
[core]
	autocrlf = true
	fscache = true
	symlinks = false
[pull]
	rebase = false
[credential]
	helper = manager-core
[credential "https://dev.azure.com"]
	useHttpPath = true
[init]
	defaultBranch = master
```

Then we add the alias at the end of the file: 

```
[diff "astextplain"]
	textconv = astextplain
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
[http]
	sslBackend = openssl
	sslCAInfo = D:/Git/mingw64/ssl/certs/ca-bundle.crt
[core]
	autocrlf = true
	fscache = true
	symlinks = false
[pull]
	rebase = false
[credential]
	helper = manager-core
[credential "https://dev.azure.com"]
	useHttpPath = true
[init]
	defaultBranch = master
[alias]
    c = "!f() { git add -A && git commit -m \"$@\" && git push; }; f"
```

now we can type `git c "message"` for our commits.

## Important Shortcuts

### Windows

* `(F1 or Ctrl + Shift + P)` - Open the command palette
* `(Ctrl+D)` - selects the word at the cursor, or the next occurrence of the current selection.
* `(Shift + Alt + Up/Down)` - Copy line up/down
*  `(Shift + Alt + Left/Right)` - Select the whole line.

