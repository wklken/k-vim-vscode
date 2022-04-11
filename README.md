# k-vim-vscode

vscode settings with vim key-bindings just like k-vim(https://github.com/wklken/k-vim)! Happy Coding! 

## ChangeLog

###  2022-03-17 v2.0.0

> 疫情, 远程办公已三周, 重新捡回了VSCode(Jetbrains系 IDE 远程开发过于拉垮); 重新做了一批定制, 同使用k-vim配置体验更一致

### 2019-04-13 v1.0.5 

> 第一个版本


## vscode plugins

- MagicPython
- auto-close-tag
- auto-rename-tag
- autodocstring
- better-comments
- better-toml
- code-runner
- code-settings-sync
- code-spell-checker
- color-highlight
- copilot
- copilot
- django-html
- errorlens
- githistory
- gitignore
- gitlens
- gitlink
- go
- jinja
- lua
- markdown-all-in-one
- markdown-preview-github-styles
- multi-command
- output-colorizer
- path-intellisense
- polacode
- prettier-vscode
- prettify-json
- project-manager
- python
- rainbow-csv
- remote-containers
- remote-ssh
- remote-ssh-edit
- rust
- scrolloff
- shell-format
- tabnine-vscode
- test-adapter-converter
- theme-monokai-pro-vscode
- todo-tree
- trailing-spaces
- unique-window-colors
- vim
- vscode-dash
- vscode-django
- vscode-docker
- vscode-eslint
- vscode-great-icons
- vscode-kubernetes-tools
- vscode-mysql
- vscode-open-in-github
- vscode-pull-request-github
- vscode-pylance
- vscode-python-test-adapter
- vscode-python-typehint
- vscode-test-explorer
- vscode-theme-darcula
- vscode-wakatime
- vscode-yaml
- vscodeintellicode


## vscode settings.json

```javascript
{
    // date: 2022-03-17 20:43

    // ## window
    // 窗口放大0.5 (explorer font-size无法自定义, 太小了)
    "window.zoomLevel": 0.5,

    // ## Editor
    "editor.fontSize": 14,
    "editor.fontFamily": "‘Fira Code’,Menlo, Monaco, 'Courier New', monospace",
    // 开启花括号颜色
    "editor.bracketPairColorization.enabled": true,
    // 禁止编辑区滚动到最后一行下面 prevent the editor from scrolling beyond the last line.
    "editor.scrollBeyondLastLine": false,
    // 查找框展示导致鼠标能往上滚动一行
    "editor.find.addExtraSpaceOnTop": false,
    // 显示 120 字符竖线 the 120 characters line
    "editor.rulers": [120],
    // 关闭小地图 disable the minimap
    "editor.minimap.enabled": false,
    // 设置注释的颜色 以及斜体展示 set comment italic
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                // comments color, like jetbrains
                "scope": [
                    "comment",
                    "comment.line",
                    "comment.block",
                    "comment.block.documentation",
                    "string.quoted.docstring.multi.python",
                    "punctuation.definition.comment",
                    "punctuation.definition.comment.begin.documentation",
                    "punctuation.definition.comment.end.documentation",
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#808080",
                }
            },
        ]
    },
    // 提示相关 suggestion
    // "editor.suggestSelection": "recentlyUsedByPrefix",
    "editor.suggestSelection": "first",
    "editor.quickSuggestions": {
      "other": true,
      "comments": true,
      "strings": true,
    },
    // "editor.acceptSuggestionOnEnter": "smart", // "on", "off", "smart"
    // Enable parameter hints => 默认开启的, 觉得信息过多的话, 关闭
    "editor.parameterHints.enabled": false,
    "editor.inlineSuggest.enabled": true,


    // ## workbench
    "workbench.colorTheme": "Darcula",
    "workbench.iconTheme": "vscode-great-icons",
    // 编辑区域配色 color like jetbrains
    "workbench.colorCustomizations": {
        "editor.background": "#2b2b2b",
        "editorGutter.background": "#313335",
        "activityBar.background": "#4d5254",
        "sideBarSectionHeader.background": "#4d5254",
        "sideBar.background": "#3b3f41",
        "statusBar.background": "#00605f",

        "terminal.foreground": "#678046",
        "terminal.ansiBrightBlue": "#2F7ECD",
        "terminal.ansiBrightGreen": "#d37e02",
        "terminal.background": "#242424",
    },
    // 高亮显示被修改的tab
    "workbench.editor.highlightModifiedTabs": true,

    // ## Terminal
    "terminal.integrated.fontSize": 14,
    "terminal.integrated.scrollback": 20000,
    // 终端选中即拷贝
    "terminal.integrated.copyOnSelection": true,
    "terminal.external.osxExec": "iTerm.app",

    // ## files
    // 隐藏哪些文件
    "files.exclude": {
        ".idea": true,
        ".vscode": true,
        "**/__pycache__": true,
        "**/*.pyc": true,
        "node_modules/": true,
        "templates_module/": true,
        "**/.project": true,
        ".mypy_cache/": true,
        //     "**/.classpath": true,
        //     "**/.coverage": true,
        //     "**/.factorypath": true,
        //     "**/.settings": true,
    },
    "files.autoSave": "onWindowChange",
    "files.trimTrailingWhitespace": true,

    // ## search
    // 显示检索到的位置的行号
    "search.showLineNumbers": true,
    // 是否智能大小写
    "search.smartCase": true,

    // ## Extension: vim
    "vim.leader": ",",
    "vim.incsearch": true,
    "vim.useCtrlKeys": true,
    "vim.hlsearch": true,
    "vim.highlightedyank.enable": true,
    // "vim.textwidth": 120,
    // "vim.visualstar": true,

    // - references: https://code.visualstudio.com/docs/getstarted/keybindings#_default-keybindings
    // shortcut: kj
    // 退出编辑模式
    "vim.insertModeKeyBindings": [
        // - k-j to ESC
        {
            "before": ["k", "j"],
            "after": ["<Esc>"]
        }
    ],
    "vim.normalModeKeyBindingsNonRecursive": [
        // shortcut: leader-q
        // quit 关闭文件
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
        // shortcut: leader-w
        // save 保存文件
        {
            "before": ["leader", "w"],
            "commands": [
                {
                    "command": "workbench.action.files.save",
                    "args": []
                }
            ]
        },
        // shortcut: leader-gd
        // goToDefinition 跳转到定义处
        {
            "before": ["leader", "g", "d"],
            "after": ["g", "d"]
        },
        // shortcut: leader-jd
        // goToDefinition 跳转到定义处
        {
            "before": ["leader", "j", "d"],
            "after": ["g", "d"]
        },
        // shortcut: leader-gi
        // goToImplementation 跳转到实现处
        {
            "before": ["leader", "g", "i"],
            "commands": [
                {
                    "command": "editor.action.goToImplementation",
                }
            ]
        },
        // shortcut: leader-gh
        // show help-tip-def 展示提示
        {
            "before": ["leader", "g", "h"],
            "after": ["g", "h"]
        },
        // shortcut: leader-h
        // show help-tip-def 展示提示
        {
            "before": ["leader", "h"],
            "after": ["g", "h"]
        },
        // shortcut: leader-d
        // show dash 当前关键字查询dash
        {
            "before": ["leader", "d"],
            "commands": ["extension.dash.specific"]
        },
        // shortcut: leader-cc
        // comment 注释
        {
            "before": ["leader", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // shortcut: leader-cu
        // uncomment 解开注释
        {
            "before": ["leader", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // shortcut: leader-rn
        // rename symbol 重命名
        {
            "before": ["leader", "r", "n"],
            "commands": ["editor.action.rename"]
        },
        // shortcut: leader-space
        // trailing space
        {
            "before": ["leader", "space"],
            "commands": ["editor.action.trimTrailingWhitespace"]
        },
        // shortcut: # and *
        // - switch # and *
        {
            "before": ["*"],
            "after": ["#"]
        },
        {
            "before": ["#"],
            "after": ["*"]
        },
        // shortcut: ;
        // show the command palette 展示command palette
        {
            "before": [";"],
            "commands": [
                "workbench.action.showCommands",
            ]
        },
        // shortcut: leader-p
        // show the command palette 展示command palette
        {
            "before": ["leader", "p"],
            "commands": [
                "workbench.action.showCommands",
            ]
        },
        // shortcut: leader-z
        // trigger editor size 当前编辑区域宽度变大变小
        {
            "before": ["leader", "z"],
            "commands": [
                "workbench.action.toggleEditorWidths",
            ]
        },

        // - leader-p to all opened editors
        // {
        //     "before": ["leader", "p"],
        //     "commands": [
        //         "workbench.action.openNextRecentlyUsedEditorInGroup"
        //     ]
        // },

        // shortcut: leader-f
        // go to file 跳转到文件
        {
            "before": ["leader", "f"],
            "commands": [
                "workbench.action.quickOpen",
            ]
        },
        // shortcut: @
        // go to symbol 跳转到当前文件的symbol位置(变量/函数/类等特征位置), k-vim中 leader-fu
        {
            // "before": ["leader", "s"],
            "before": ["@"],
            "commands": [
                "workbench.action.gotoSymbol",
            ]
        },
        // shortcut: leader-s
        // show problems 展示当前编辑文件的问题
        {
            "before": ["leader", "s"],
            "commands": [
                "workbench.actions.view.problems"
            ]
        },
        // shortcut: leader-en
        // Go to Next Error or Warning 下一个错误点
        {
            "before": ["leader", "e", "n"],
            "commands": [
                "editor.action.marker.nextInFiles"
            ]
        },
        // shortcut: leader-ep
        // Go to Previous Error or Warning 前一个错误点
        {
            "before": ["leader", "e", "p"],
            "commands": [
                "editor.action.marker.prevInFiles"
            ]
        },
        // shortcut: leader-/
        // turn-off highlight 关闭vim search高亮选中
        {
            "before":["leader", "/"],
            "commands": [
                ":nohl",
            ]
        },
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
        // shortcut: leader-cc
        // add comment 加注释
        {
            "before": ["<leader>", "c", "c"],
            "commands": ["editor.action.addCommentLine"]
        },
        // shortcut: leader-cu
        // uncomment 解开注释
        {
            "before": ["<leader>", "c", "u"],
            "commands": ["editor.action.removeCommentLine"]
        },
        // shortcut: > / <
        // indent/outdent lines (repeatable) 左右移动代码块
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

    // ## Extension: python
    // "python.linting.flake8Enabled": true,
    // "python.linting.pylintEnabled": false,
    "python.linting.flake8Args": [
        "--max-line-length=120",
        "--max-complexity=12"
    ],
    "python.linting.mypyEnabled": true,
    "python.formatting.provider": "black",


    // ## Extension: go
    // https://github.com/mvdan/gofumpt
    "go.useLanguageServer": true,
    "gopls": {
        "ui.semanticTokens": true,
        // https://github.com/golang/tools/blob/master/gopls/doc/settings.md#formatting
        "formatting.gofumpt": true,
        // TODO: how to change it for each project
        "formatting.local": "iam",
        // https://github.com/golang/tools/blob/master/gopls/doc/settings.md#importshortcut-enum
        // import package don't show as link
        "ui.navigation.importShortcut": "Definition",
        // when mouse hover only show struct, without document
        "ui.documentation.hoverKind": "NoDocumentation",
        // add parameter placeholders when completing a function
        "ui.completion.usePlaceholders": true,
    },
    "go.lintTool": "golangci-lint",
    "go.lintFlags": [
        "--fast"
    ],
    "go.testFlags": [
        "-mod=vendor",
        "-gcflags=all=-l",
        "-covermode=count",
        // "-coverprofile .coverage.cov",
    ],
    // https://dev.to/vuong/golang-in-vscode-show-code-coverage-of-after-saving-test-8g0
    "go.coverageDecorator": {
        "type": "gutter",
        // "coveredHighlightColor": "rgba(64,128,128,0.5)",
        // "uncoveredHighlightColor": "rgba(128,64,64,0.25)",
        "coveredGutterStyle": "blockgreen",
        "uncoveredGutterStyle": "blockred"
    },
    "go.coverOnSingleTest": true,
    "go.toolsManagement.autoUpdate": true,
    "[go]": {
        // "editor.snippetSuggestions": "top",
        // "editor.snippetSuggestions": "none",
        "editor.formatOnSave": true,
        "editor.codeActionsOnSave": {
            "source.organizeImports": true
        }
    },

    // ## Extension: scrolloff
    "scrolloff.scrolloff": 7,

    // ## Extension: markdown
    "markdown.preview.fontSize": 16,
    "markdown-preview-github-styles.colorTheme": "light",

    // ## Extension: errorLens
    "errorLens.statusBarColorsEnabled": true,
    "errorLens.margin": "6ch",
    "errorLens.fontWeight": "100",
    "errorLens.fontStyleItalic": true,
    "errorLens.fontSize": "13",
    "errorLens.followCursor": "closestProblem",
    "errorLens.gutterIconsEnabled": true,
    "errorLens.excludeBySource": [
        "cSpell"
    ],
    // not show in real
    "errorLens.onSave": true,

    // ## Extension: todo-tree
    "todo-tree.highlights.enabled": false,
    // ## Extension: cSpell
    "cSpell.ignoreRegExpList": [
        "github.com.*"
    ],
    "cSpell.userWords": [
        "funcs",
        "healthz",
        "Infof"
    ],
    // ## Extension: better-comments
    // ignore multiline comments, while the license with * will render to green
    "better-comments.multilineComments": false,
    // add more keyword to highlight, like fixme/note
    "better-comments.tags": [
        {
            "tag": "fixme",
            "color": "#FF2D00",
            "strikethrough": false,
            "underline": false,
            "backgroundColor": "transparent",
            "bold": false,
            "italic": false
        },
        {
            "tag": "note",
            "color": "#3498DB",
            "strikethrough": false,
            "underline": false,
            "backgroundColor": "transparent",
            "bold": false,
            "italic": false
        },
    ],
    // ## Extension: vsintellicode
    "vsintellicode.modify.editor.suggestSelection": "choseToUpdateConfiguration",
    // ## Extension: tabnine
    "tabnine.experimentalAutoImports": true,
}
```

## vscode keybindings.json

```javascript
[
    // ! double click can't select one world
    // add vscode to popclip exclude apps if you installed one on your mac!

    // shortcut: ctrl+j/k
    // for choose suggestion
    // ctrl+j/k 选择提示候选
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
    // shortcut: ctrl+j/k
    // for quick open choose
    // ctrl+j/k 选择quickopen文件列表
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
    // shortcut: cmd+enter
    // rename a file in explorer, same to mac finder
    // 在explorer中重命名文件
    {
        "key": "cmd+enter",
        "command": "renameFile",
        "when": "explorerViewletVisible && filesExplorerFocus"
    },
    // shortcut disable: enter 重命名文件, 避免冲突
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
    // shortcut: ctrl+h/j/k/l
    // ctrl+h/j/k/l to the between groups
    // ctrl+h/j/k/l 在group之间移动
    {
        "key": "ctrl+h",
        "command": "workbench.action.focusLeftGroup"
    },
    {
        "key": "ctrl+l",
        "command": "workbench.action.focusRightGroup"
    },
    {
        "key": "ctrl+k",
        "command": "workbench.action.focusAboveGroup",
        "when": "!inQuickOpen && !suggestWidgetVisible"
    },
    {
        "key": "ctrl+j",
        "command": "workbench.action.focusBelowGroup",
        "when": "!inQuickOpen && !suggestWidgetVisible"
    },
    // shortcut: cmd+h/l
    // cmd+h/l to the next/previous eeditor tab
    // cmd+h/l 切换前一个/后一个tab
    {
        "key": "cmd+h",
        "command": "workbench.action.previousEditor"
    },
    {
        "key": "cmd+l",
        "command": "workbench.action.nextEditor"
    },
    // shortcut: cmd+1
    // trigger sidebar and activity bar visibility
    // 展示/隐藏左侧 sidebar和activity bar
    // NOTE: 本来应该是切换到第一个tab的; 注意需要安装multiCommand插件
    {
        "key": "cmd+1",
        "command": "extension.multiCommand.execute",
        "args": {
            "sequence": [
                "workbench.action.toggleActivityBarVisibility",
                "workbench.action.toggleSidebarVisibility",
            ]
        }
        // "command": "workbench.action.openEditorAtIndex1",
        // "command": "workbench.action.toggleSidebarVisibility",
        // "command": "workbench.action.toggleActivityBarVisibility",
    },
    // shortcut: cmd+number (>=2)
    // cmd+number to switch to tab N
    // cmd+数字切换到第 N 个tab
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
    // shortcut: ctrl+1/2
    // switch group between first and second
    // 切换到第一个group或第二个group
    {
        "key": "ctrl+1",
        "command": "workbench.action.focusFirstEditorGroup",
    },
    {
        "key": "ctrl+2",
        "command": "workbench.action.focusSecondEditorGroup",
    },
    // shortcut: cmd+j
    // trigger the visibility of panel
    // 展示/隐藏 panel

    // shortcut: ctrl+`
    // active between editor and terminal
    // 在termianl和编辑框之间切换
    {
        "key": "ctrl+`",
        "command": "workbench.action.focusActiveEditorGroup",
        "when": "terminalFocus"
    },
    // shortcut: cmd+\
    // move current tab into next group
    // 将当前正在编辑的tab 竖直切分成group
    {
        "key": "cmd+\\",
        "command": "-workbench.action.splitEditor"
    },
    {
        "key": "cmd+\\",
        "command": "workbench.action.moveEditorToNextGroup"
    },

    // shortcut: escape
    // back to explorer when search done
    // 全局搜索后, esc切换到explorer
    // TODO: 如何focus在editor上面?
    {
        "key": "Escape",
        "command": "workbench.view.explorer",
        "when": "searchViewletVisible"
    },
    // shortcut: ctrl+w ctrl+hjkl
    // ctrl+w ctrl+hjkl move group
    // ctrl+w ctrl+hjkl 挪动group
    {
        "key": "ctrl+w shift+j",
        "command": "workbench.action.moveActiveEditorGroupDown"
    },
    {
        "key": "cmd+k down",
        "command": "-workbench.action.moveActiveEditorGroupDown"
    },
    {
        "key": "ctrl+w shift+h",
        "command": "workbench.action.moveActiveEditorGroupLeft"
    },
    {
        "key": "cmd+k left",
        "command": "-workbench.action.moveActiveEditorGroupLeft"
    },
    {
        "key": "ctrl+w shift+l",
        "command": "workbench.action.moveActiveEditorGroupRight"
    },
    {
        "key": "cmd+k right",
        "command": "-workbench.action.moveActiveEditorGroupRight"
    },
    {
        "key": "ctrl+w shift+k",
        "command": "workbench.action.moveActiveEditorGroupUp"
    },
    {
        "key": "cmd+k up",
        "command": "-workbench.action.moveActiveEditorGroupUp"
    },
    // shortcut: cmd+r
    // do replace
    // 替换, same as intellij
    {
        "key": "cmd+r",
        "command": "editor.action.startFindReplaceAction",
        "when": "editorFocus || editorIsOpen"
    },
    {
        "key": "alt+cmd+f",
        "command": "-editor.action.startFindReplaceAction",
        "when": "editorFocus || editorIsOpen"
    },
    // others
    // shortcut disable: zoom
    {
        "key": "cmd+=",
        "command": "-workbench.action.zoomIn"
    },
    {
        "key": "cmd+-",
        "command": "-workbench.action.zoomOut"
    },
]
```


------

wklken 于深圳
