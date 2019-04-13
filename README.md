# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 


## vscode settings

```javascript
{
    "editor.fontSize": 16,
    "editor.fontFamily": "Menlo",
    "editor.wordWrapColumn": 120,
    "editor.dragAndDrop": false,
    "editor.minimap.enabled": false,
    "editor.glyphMargin": false,
    "workbench.tips.enabled": false,
    "workbench.colorTheme": "Darcula",
    "workbench.iconTheme": "vscode-great-icons",
    "workbench.colorCustomizations": {
        "editorWarning.foreground": "#a3b3d1"
    },
    "workbench.statusBar.feedback.visible": false,
    "debug.console.fontSize": 14,
    "terminal.integrated.fontSize": 14,
    "terminal.integrated.scrollback": 2000,
    "terminal.integrated.shell.osx": "zsh",
    "terminal.external.osxExec": "iTerm.app",
    "files.trimTrailingWhitespace": true,
    "files.autoSave": "onFocusChange",
    "search.location": "panel",
    "search.showLineNumbers": true,
    "search.smartCase": true,
    "scrolloff.scrolloff": 7,
    // extension: bracket-pair-colorizer-2
    "bracket-pair-colorizer-2.showHorizontalScopeLine": false,
    "bracket-pair-colorizer-2.showVerticalScopeLine": false,
    "bracket-pair-colorizer-2.colorMode": "Independent",
    // extension: sync
    "sync.gist": "7e7efe82ce6252439e93303696a10433",
    // extension: go
    "go.useLanguageServer": true,
    "go.autocompleteUnimportedPackages": true,
    "go.useCodeSnippetsOnFunctionSuggest": true,
    "go.lintOnSave": "file",
    // - https://github.com/golangci/golangci-lint
    "go.lintTool": "golangci-lint",
    // extension: vim
    "vim.leader": ",",
    "vim.hlsearch": true,
    "vim.textwidth": 120,
    "vim.insertModeKeyBindings": [
        // k-j to ESC
        {
            "before": ["k", "j"],
            "after": ["<Esc>"]
        }
    ],
    "vim.normalModeKeyBindingsNonRecursive": [
        // leader-q to quit
        {
            "before": ["leader", "q"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                },
                {
                    "command": "workbench.action.closeActiveEditor",
                    "args": []
                }
            ]
        },
        // leader-w to save
        {
            "before": ["leader", "w"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                }
            ]
        },
        // ctrl-m to multi-cursor select
        {
            "before": ["<C-m>"],
            "after": ["g", "b"]
        },
        // leader-gd to goToDefinition
        {
            "before": ["leader", "g", "d"],
            "after": ["g", "d"]
        },
        // leader-jd to goToDefinition
        {
            "before": ["leader", "j", "d"],
            "after": ["g", "d"]
        },
        // leader-gh show help-tip-def
        {
            "before": ["leader", "g", "h"],
            "after": ["g", "h"]
        },
        // leader-h show help-tip-def
        {
            "before": ["leader", "h"],
            "after": ["g", "h"]
        },
        // leader-cc comment / uncomment
        {
            "before": ["leader", "c", "c"],
            "after": ["g", "c", "c"]
        },
        // leader-cu comment / uncomment
        {
            "before": ["leader", "c", "u"],
            "after": ["g", "c", "c"]
        },
        // leader-vp vsp
        {
            "before": ["leader", "v", "p"],
            "commands": [
                {
                    "command": "workbench.action.splitEditorDown"
                }
            ]
        },
        // leader-sp sp
        {
            "before": ["leader", "s", "p"],
            "commands": [
                {
                    "command": "workbench.action.splitEditorRight"
                }
            ]
        },
        // switch # and *
        {
            "before": ["*"],
            "after": ["#"]
        },
        {
            "before": ["#"],
            "after": ["*"]
        },
        // show the command palette
        {
            "before": [":"],
            "commands": [
                "workbench.action.showCommands",
            ]
        },
        // turn-off highlight
        {
            "before":["leader", "/"],
            "commands": [
                ":nohl",
            ]
        },
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
        // multi-cursor
        {
            "before": ["<C-m>"],
            "after": ["g", "b"]
        },
        // indent/outdent lines (repeatable)
        {
            "before": [
                ">"
            ],
            "commands": [
                "editor.action.indentLines"
            ]
        },
        {
            "before": [
                "<"
            ],
            "commands": [
                "editor.action.outdentLines"
            ]
        },
    ],
    // auto switch input, detail https://github.com/VSCodeVim/Vim#input-method
    "vim.autoSwitchInputMethod.enable": true,
    "vim.autoSwitchInputMethod.defaultIM": "com.apple.keylayout.ABC",
    "vim.autoSwitchInputMethod.obtainIMCmd": "/usr/local/bin/im-select",
    "vim.autoSwitchInputMethod.switchIMCmd": "/usr/local/bin/im-select {im}",
    // easymotion, detail https://github.com/VSCodeVim/Vim#vim-easymotion
    "vim.easymotion": true,
    "vim.easymotionMarkerFontFamily": "Menlo",
    "vim.easymotionMarkerFontSize": "16",
    "vim.easymotionMarkerHeight": 24,
    "vim.easymotionMarkerBackgroundColor": "#f44242",
}

```

#### vscode key-maps

```javascript
{
  "key": "ctrl+j",
  "command": "selectNextSuggestion",
  "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
},
{
  "key": "ctrl+k",
  "command": "selectPrevSuggestion",
  "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
}
```


### Donation

如果你认为对你有所帮助, You can Buy me a coffee:)


![donation](https://raw.githubusercontent.com/wklken/gallery/master/donation/donation_w.jpg)

wklken

2019-04-13
