# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 


## vscode settings.json

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
    "sync.gist": "",
    // extension: vim
    "vim.leader": ",",
    "vim.hlsearch": true,
    "vim.textwidth": 120,
    "vim.visualstar": true,
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
            "commands": ["editor.action.addCommentLine"]
        },
        // leader-cu comment / uncomment
        {
            "before": ["leader", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
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
        // comment with leader cc/cu
        {
            "before": ["<leader>", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        {
            "before": ["<leader>", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
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
    // extension: go
    "go.useLanguageServer": true,
    "go.autocompleteUnimportedPackages": true,
    "go.useCodeSnippetsOnFunctionSuggest": true,
    "go.lintOnSave": "file",
    // - https://github.com/golangci/golangci-lint
    "go.lintTool": "golangci-lint",
    // extension: python
    "python.unitTest.nosetestsEnabled": true,
    "python.linting.flake8Enabled": true,
    "python.linting.flake8Args": [
        "--max-line-length=120",
        "--max-complexity=12",
        "--format=pylint"
    ],
    "python.linting.pylintEnabled": false,
}
```

## vscode keybindings.json

```javascript
// Place your key bindings in this file to override the defaultsauto[]
[
    // add vscode to popclip if you installed one on your mac!
    // ! double click can't select one world

    // ctrl+j/k for choose suggestion
    {
        "key": "ctrl+j",
        "command": "selectNextSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    {
        "key": "ctrl+k",
        "command": "selectPrevSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    // ctrl+j/k for quick open choose
    {
        "key": "ctrl+j",
        "command": "workbench.action.quickOpenSelectNext",
        "when": "inQuickOpen"
    },
    {
        "key": "ctrl+k",
        "command": "workbench.action.quickOpenSelectPrevious",
        "when": "inQuickOpen"
    },

    // cmd + enter, rename
    {
        "key": "cmd+enter",
        "command": "renameFile",
        "when": "explorerViewletVisible && filesExplorerFocus"
    },
    // enter, open
    {
        "key": "enter",
        "command": "-renameFile",
        "when": "explorerViewletVisible && filesExplorerFocus"
    },
    {
        "key": "enter",
        "command": "list.select",
        "when": "listFocus && !inputFocus"
    },
    // ctrl+l/h to the next/previous edirot
    {
        "key": "ctrl+l",
        "command": "workbench.action.nextEditor"
    },
    {
        "key": "ctrl+h",
        "command": "workbench.action.previousEditor"
    },
    // cmd+number to change editor, swith with ctrl+number
    {
        "key": "cmd+1",
        "command": "workbench.action.openEditorAtIndex1",
    },
    {
        "key": "cmd+2",
        "command": "workbench.action.openEditorAtIndex2",
    },
    {
        "key": "cmd+3",
        "command": "workbench.action.openEditorAtIndex3",
    },
    {
        "key": "cmd+4",
        "command": "workbench.action.openEditorAtIndex4",
    },
    {
        "key": "cmd+5",
        "command": "workbench.action.openEditorAtIndex5",
    },
    {
        "key": "cmd+6",
        "command": "workbench.action.openEditorAtIndex6",
    },
    {
        "key": "cmd+7",
        "command": "workbench.action.openEditorAtIndex7",
    },
    {
        "key": "cmd+8",
        "command": "workbench.action.openEditorAtIndex8",
    },
    {
        "key": "cmd+9",
        "command": "workbench.action.openEditorAtIndex9",
    },
    // change group, swith with cmd+number
    {
        "key": "ctrl+1",
        "command": "workbench.action.focusFirstEditorGroup",
    },
    {
        "key": "ctrl+2",
        "command": "workbench.action.focusSecondEditorGroup",
    },
    // active between editor and terminal
    {
        "key": "ctrl+`",
        "command": "workbench.action.focusActiveEditorGroup",
        "when": "terminalFocus"
    },
    {
        "key": "ctrl+`",
        "command": "workbench.action.terminal.focus",
        "when": "!terminalFocus"
    },
]
```


------

wklken

2019-04-13
