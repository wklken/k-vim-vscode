# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 

## Current Version

**1.0.5**


## vscode settings.json

```javascript
{
    // ## Explorer
    // - hide open editors, use leader-p to choose
    "explorer.openEditors.visible": 0,
    "explorer.confirmDragAndDrop": false,
    // ## Editor
    // from: https://github.com/Microsoft/vscode/blob/master/src/vs/editor/common/config/commonEditorConfig.ts
    "editor.fontSize": 16,
    "editor.fontFamily": "Menlo",
    "editor.wordWrapColumn": 120,
    "editor.dragAndDrop": false,
    "editor.minimap.enabled": false,
    "editor.glyphMargin": false,
    // - active suggestion in comments and string
    "editor.quickSuggestions": {
      "other": true,
      "comments": true,
      "strings": true
    },
    // - a lot of noisy
    "editor.parameterHints.enabled": false,
    "editor.rulers": [120],
    "editor.tokenColorCustomizations": {
        "textMateRules": [
        ]
    },
    // - prevent the editor from scrolling beyond the last line.
    "editor.scrollBeyondLastLine": false,
    // ## Workbench
    "workbench.colorTheme": "Darcula",
    "workbench.iconTheme": "vscode-great-icons",
    "workbench.tips.enabled": false,
    "workbench.colorCustomizations": {
        "editorWarning.foreground": "#a3b3d1"
    },
    "workbench.statusBar.feedback.visible": false,
    // ## Terminal
    "terminal.integrated.fontSize": 14,
    "terminal.integrated.scrollback": 2000,
    "terminal.integrated.shell.osx": "zsh",
    "terminal.external.osxExec": "iTerm.app",
    "debug.console.fontSize": 14,
    "files.trimTrailingWhitespace": true,
    "files.autoSave": "onFocusChange",
    "files.exclude": {
        ".vscode":true,
        "**/.classpath": true,
        "**/.factorypath": true,
        "**/.project": true,
        "**/.coverage": true,
        "**/*.pyc": true,
        "**/__pycache__": true,
        "node_modules/":true,
        "templates_module/":true,
        "**/.settings": true
    },
    "files.autoGuessEncoding": true,
    "search.location": "panel",
    "search.showLineNumbers": true,
    "search.smartCase": true,
    // ## Extension: scrolloff
    "scrolloff.scrolloff": 7,
    // ## Extension: bracket-pair-colorizer-2
    "bracket-pair-colorizer-2.showHorizontalScopeLine": false,
    "bracket-pair-colorizer-2.showVerticalScopeLine": false,
    "bracket-pair-colorizer-2.colorMode": "Independent",
    // ## Extension: sync
    "sync.gist": "",
    // ## Extension: vim
    "vim.leader": ",",
    "vim.hlsearch": true,
    "vim.textwidth": 120,
    "vim.visualstar": true,
    "vim.insertModeKeyBindings": [
        // - k-j to ESC
        {
            "before": ["k", "j"],
            "after": ["<Esc>"]
        }
    ],
    // - references: https://code.visualstudio.com/docs/getstarted/keybindings#_default-keybindings
    "vim.normalModeKeyBindingsNonRecursive": [
        // - leader-q to quit
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
        // - leader-w to save
        {
            "before": ["leader", "w"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                }
            ]
        },
        // - leader-gd to goToDefinition
        {
            "before": ["leader", "g", "d"],
            "after": ["g", "d"]
        },
        // - leader-jd to goToDefinition
        {
            "before": ["leader", "j", "d"],
            "after": ["g", "d"]
        },
        // - leader-gh show help-tip-def
        {
            "before": ["leader", "g", "h"],
            "after": ["g", "h"]
        },
        // - leader-h show help-tip-def
        {
            "before": ["leader", "h"],
            "after": ["g", "h"]
        },
        // - leader-cc comment
        {
            "before": ["leader", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // - leader-cu uncomment
        {
            "before": ["leader", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // - switch # and *
        {
            "before": ["*"],
            "after": ["#"]
        },
        {
            "before": ["#"],
            "after": ["*"]
        },
        // - show the command palette
        {
            "before": [";"],
            "commands": [
                "workbench.action.showCommands",
            ]
        },
        // - leader-p to all opened editors
        {
            "before": ["leader", "p"],
            "commands": [
                "workbench.action.openNextRecentlyUsedEditorInGroup"
            ]
        },
        // - leader-f: go to file
        {
            "before": ["leader", "f"],
            "commands": [
                "workbench.action.quickOpen",
            ]
        },
        // - leader-g go to symbol
        {
            "before": ["leader", "g"],
            "commands": [
                "workbench.action.gotoSymbol",
            ]
        },
        // - leader-s show problems
        {
            "before": ["leader", "s"],
            "commands": [
                "workbench.actions.view.problems"
            ]
        },
        // - leader-en Go to Next Error or Warning
        {
            "before": ["leader", "e", "n"],
            "commands": [
                "editor.action.marker.nextInFiles"
            ]
        },
        // - leader-ep Go to Previous Error or Warning
        {
            "before": ["leader", "e", "p"],
            "commands": [
                "editor.action.marker.prevInFiles"
            ]
        },
        // - leader-/ to turn-off highlight
        {
            "before":["leader", "/"],
            "commands": [
                ":nohl",
            ]
        },
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
        // - leader-cc comment
        {
            "before": ["<leader>", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // - leader-cu uncomment
        {
            "before": ["<leader>", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // - indent/outdent lines (repeatable)
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
    // - auto switch input. detail https://github.com/VSCodeVim/Vim#input-method
    "vim.autoSwitchInputMethod.enable": true,
    "vim.autoSwitchInputMethod.defaultIM": "com.apple.keylayout.ABC",
    "vim.autoSwitchInputMethod.obtainIMCmd": "/usr/local/bin/im-select",
    "vim.autoSwitchInputMethod.switchIMCmd": "/usr/local/bin/im-select {im}",
    // - easymotion. detail https://github.com/VSCodeVim/Vim#vim-easymotion
    "vim.easymotion": true,
    "vim.easymotionMarkerFontFamily": "Menlo",
    "vim.easymotionMarkerFontSize": "16",
    "vim.easymotionMarkerHeight": 24,
    "vim.easymotionMarkerBackgroundColor": "#f44242",
    // ## Extension: go
    "go.useCodeSnippetsOnFunctionSuggest": true,
    "go.formatTool": "goimports",
    "go.formatFlags": ["-local", "apigateway/"],
    "go.lintTool": "golangci-lint",
    "go.lintFlags": [
        "--fast",
        "--disable go-lint",
        "--enable gocyclo",
    ],
    "go.lintOnSave": "file",
    // ## Extension: python
    "python.testing.nosetestsEnabled": true,
    "python.linting.flake8Enabled": true,
    "python.linting.flake8Args": [
        "--max-line-length=120",
        "--max-complexity=12",
        "--format=pylint"
    ],
    "python.linting.pylintEnabled": false,
    // ## Extension: cSpell
    "cSpell.ignoreWords": [
        "logrus",
        "bkauth",
        "BKAPI",
        "APIGW"
    ],
    "cSpell.userWords": [
        "apiid",
        "debugf",
        "healthz",
        "infof",
        "stretchr",
        "uuid"
    ],
}
```

## vscode keybindings.json

```javascript
[
    // ! double click can't select one world
    // add vscode to popclip exclude apps if you installed one on your mac!

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
