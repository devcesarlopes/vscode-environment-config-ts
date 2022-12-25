<link rel="stylesheet" href="./styles.css">

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
* `(Ctrl + Shift + X)` - Open Extensions Tab
* `(Ctrl+D)` - selects the word at the cursor, or the next occurrence of the current selection.
* `(Shift + Alt + Up/Down)` - Copy line up/down
* `(Shift + Alt + Left/Right)` - Select the whole line.

## Configurations File - config.json

The main file of VsCode that allows us to customize our editor is the config.json, to open it, we just have to `Open the command palette`, then type `">json"`, then select `"Preferences: Open User Settings (JSON)"`.

Probably the default `config.json` will be empty: `{}`.

## Theming

One of my favorite themes for Vscode is dracula. To download it, <abbr title="Ctrl + Shift + X">`Open Extensions Tab`</abbr>, then type the dracula extension id: 

`dracula-theme.theme-dracula`

 Then set color theme for dracula or dracula-soft. I personally prefer dracula.

## Fonts

When I'm programming I like to show the boolean conditions in a special formatting. 

<img src="./firacode.svg" alt="drawing" width="500"/>

To do that we can download the Firacode Fonts, made by tonsky.

[Download Firacode Fonts](https://github.com/tonsky/FiraCode)

Download the zip file, unpack, go to `ttf` folder and install the fonts on your system.

Then, open the `Config.json` file. It is going to look like this:

```
{
    "workbench.colorTheme": "Dracula"
}
```

Replace by this code:

```
{
    "workbench.colorTheme": "Dracula",
    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,
}
```

Now, whenever we write `==, ===, !=, !==, >=, >, <>` and others, they will be pretty formated. 

## Color Highlight

Let's say that we write a color hex or rgb in our code. Sometime we can get lost on which color is which, so, to make our life easier, we can just use the Color Highlight extension. This extension will highlight the colors in the #hex codes so we can know which color we are dealing with in our css or styled-components.

To download it, <abbr title="Ctrl + Shift + X">`Open Extensions Tab`</abbr>, then type the Color Highlight extension id: 

`naumovs.color-highlight`

## Env files

To highlight `.env` files and see better the variables we can use DotENV extension.

To download it, <abbr title="Ctrl + Shift + X">`Open Extensions Tab`</abbr>, then type the DotENV extension id: `mikestead.dotenv`, download it.

## Editor Config

When developing code in teams, it is possible that people use different editors to develop the code. So, to keep a default formatting and make sure that the identation_size, identation_style, charset, and other properties that we can't see are the same along the team we can use this extension make sure the problem "in my machine works" is not going to be told.

To download it, <abbr title="Ctrl + Shift + X">`Open Extensions Tab`</abbr>, then type the Editor Config extension id:

 `EditorConfig.EditorConfig`


To Use it, go to your main project folder, In the Explorer tab, right click and select `[generate .editorconfig]`. It is going to be the last option.

