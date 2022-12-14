## vscode cheatsheet

Topics: [[vscode]] [[visual studio code]]  

---

Visual Studio Code command cheatsheet and vscode related information
## VSCode Cheatsheet (Keyboard Shortcuts)
### Commands for Windows
```terminal
General
Ctrl+Shift+P, F1   Show Command Palette
Ctrl+P             Quick Open, Go to File…
Ctrl+Shift+N       New window/instance
Ctrl+Shift+W       Close window/instance
Ctrl+,             User Settings
Ctrl+K Ctrl+S      Keyboard Shortcuts

Integrated terminal
Ctrl+`            Show integrated terminal
Ctrl+Shift+`      Create new terminal
Ctrl+C            Copy selection
Ctrl+V            Paste into active terminal
Ctrl+↑ / ↓        Scroll up/down
Shift+PgUp / PgDn Scroll page up/down
Ctrl+Home / End   Scroll to top/bottom

Navigation
Ctrl+T             Show all Symbols
Ctrl+G             Go to Line...
Ctrl+P             Go to File...
Ctrl+Shift+O       Go to Symbol...
Ctrl+Shift+M       Show Problems panel
F8                 Go to next error or warning
Shift+F8           Go to previous error or warning
Ctrl+Shift+Tab     Navigate editor group history
Alt+ ← / →         Go back / forward

Editor management
Ctrl+F4, Ctrl+W    Close editor
Ctrl+K F           Close folder
Ctrl+\             Split editor
Ctrl+ 1 / 2 / 3    Focus into 1st, 2nd or 3rd editor group
Ctrl+K Ctrl+ ←/→   Focus into previous/next editor group
Ctrl+Shift+PgUp /  Move editor left/right 
PgDn 
Ctrl+K ← / →       Move active editor group

File management
Ctrl+N             New File
Ctrl+O             Open File...
Ctrl+S             Save
Ctrl+Shift+S       Save As...
Ctrl+K S           Save All
Ctrl+F4            Close
Ctrl+K Ctrl+W      Close All
Ctrl+Shift+T       Reopen closed editor
Ctrl+K Enter       Keep preview mode editor open
Ctrl+Tab           Open next
Ctrl+Shift+Tab     Open previous
Ctrl+K P           Copy path of active file
Ctrl+K R           Reveal active file in Explorer
Ctrl+K O           Show active file in new window/instance

Debug
F9                Toggle breakpoint
F5                Start/Continue
Shift+F5          Stop
F11 / Shift+F11   Step into/out
F10               Step over
Ctrl+K Ctrl+I     Show hover

Rich languages editing
Ctrl+Space         Trigger suggestion
Ctrl+Shift+Space   Trigger parameter hints
Shift+Alt+F        Format document
Ctrl+K Ctrl+F      Format selection
F12                Go to Definition
Alt+F12            Peek Definition
Ctrl+K F12         Open Definition to the side
Ctrl+.             Quick Fix
Shift+F12          Show References
F2                 Rename Symbol
Ctrl+K Ctrl+X      Trim trailing whitespace
Ctrl+K M           Change file language

Basic editing
Ctrl+X             Cut line (empty selection)
Ctrl+C             Copy line (empty selection)
Alt+ ↑ / ↓         Move line up/down
Shift+Alt + ↓ / ↑  Copy line up/down
Ctrl+Shift+K       Delete line
Ctrl+Enter         Insert line below
Ctrl+Shift+Enter   Insert line above
Ctrl+Shift+\       Jump to matching bracket
Ctrl+] / [         Indent/outdent line
Home / End         Go to beginning/end of line
Ctrl+Home          Go to beginning of file
Ctrl+End           Go to end of file
Ctrl+↑ / ↓         Scroll line up/down
Alt+PgUp / PgDn    Scroll page up/down
Ctrl+Shift+[       Fold (collapse) region
Ctrl+Shift+]       Unfold (uncollapse) region
Ctrl+K Ctrl+[      Fold (collapse) all subregions
Ctrl+K Ctrl+]      Unfold (uncollapse) all subregions
Ctrl+K Ctrl+0      Fold (collapse) all regions
Ctrl+K Ctrl+J      Unfold (uncollapse) all regions
Ctrl+K Ctrl+C      Add line comment
Ctrl+K Ctrl+U      Remove line comment
Ctrl+/             Toggle line comment
Shift+Alt+A        Toggle block comment
Alt+Z              Toggle word wrap

Search and replace
Ctrl+F             Find
Ctrl+H             Replace
F3 / Shift+F3      Find next/previous
Alt+Enter          Select all occurences of Find match
Ctrl+D             Add selection to next Find match
Ctrl+K Ctrl+D      Move last selection to next Find match
Alt+C / R / W      Toggle case-sensitive / regex / whole word

Display
F11                Toggle full screen
Shift+Alt+0        Toggle editor layout (horizontal/vertical)
Ctrl+ = / -        Zoom in/out
Ctrl+B             Toggle Sidebar visibility
Ctrl+Shift+E       Show Explorer / Toggle focus
Ctrl+Shift+F       Show Search
Ctrl+Shift+G       Show Source Control
Ctrl+Shift+D       Show Debug
Ctrl+Shift+X       Show Extensions
Ctrl+Shift+H       Replace in files
Ctrl+Shift+J       Toggle Search details
Ctrl+Shift+U       Show Output panel
Ctrl+Shift+V       Open Markdown preview
Ctrl+K V           Open Markdown preview to the side
Ctrl+K Z           Zen Mode (Esc Esc to exit)

Multi-cursor and selection
Alt+Click          Insert cursor
Ctrl+Alt+ ↑ / ↓    Insert cursor above / below
Ctrl+U             Undo last cursor operation
Shift+Alt+I        Insert cursor at end of each line selected
Ctrl+L             Select current line
Ctrl+Shift+L       Select all occurrences of current selection
Ctrl+F2            Select all occurrences of current word
Shift+Alt+→        Expand selection
Shift+Alt+←        Shrink selection
Shift+Alt +        Column (box) selection
(drag mouse)
Ctrl+Shift+Alt     Column (box) selection
+ (arrow key)
Ctrl+Shift+Alt     Column (box) selection page up/down
+PgUp/PgDn
```
### Commands for MacOS
```terminal
⇧ = Shift 	   ⌃ = Control (or Ctrl)     ⌥ = Option (or Alt)     ⌘ = Command (or Cmd)

General
⇧⌘P, F1           Show Command Palette
⌘P                Quick Open, Go to File…
⇧⌘N               New window/instance
⌘W                Close window/instance
⌘,                User Settings
⌘K ⌘S             Keyboard Shortcuts

Integrated terminal
⌃`               Show integrated terminal
⌃⇧`              Create new terminal
⌘C               Copy selection
⌘↑ / ↓           Scroll up/down
PgUp / PgDn      Scroll page up/down
⌘Home / End      Scroll to top/bottom

Basic editing
⌘X                Cut line (empty selection)
⌘C                Copy line (empty selection)
⌥↓ / ⌥↑           Move line down/up
⇧⌥↓ / ⇧⌥↑         Copy line down/up
⇧⌘K               Delete line
⌘Enter / ⇧⌘Enter  Insert line below/above
⇧⌘\               Jump to matching bracket
⌘] / ⌘[           Indent/outdent line
Home / End        Go to beginning/end of line
⌘↑ / ⌘↓           Go to beginning/end of file
⌃PgUp / ⌃PgDn     Scroll line up/down
⌘PgUp /⌘PgDn      Scroll page up/down
⌥⌘[ / ⌥⌘]         Fold/unfold region
⌘K ⌘[ / ⌘K ⌘]     Fold/unfold all subregions
⌘K ⌘0 / ⌘K ⌘J     Fold/unfold all regions
⌘K ⌘C             Add line comment
⌘K ⌘U             Remove line comment
⌘/                Toggle line comment
⇧⌥A               Toggle block comment
⌥Z                Toggle word wrap

Display
⌃⌘F               Toggle full screen
⌥⌘0               Toggle editor layout (horizontal/vertical)
⌘= / ⇧⌘-          Zoom in/out
⌘B                Toggle Sidebar visibility
⇧⌘E               Show Explorer / Toggle focus
⇧⌘F               Show Search
⌃⇧G               Show Source Control
⇧⌘D               Show Debug
⇧⌘X               Show Extensions
⇧⌘H               Replace in files
⇧⌘J               Toggle Search details
⇧⌘U               Show Output panel
⇧⌘V               Open Markdown preview
⌘K V              Open Markdown preview to the side
⌘K Z              Zen Mode (Esc Esc to exit)

File management
⌘N                New File
⌘O                Open File...
⌘S                Save
⇧⌘S               Save As...
⌥⌘S               Save All
⌘W                Close
⌘K ⌘W             Close All
⇧⌘T               Reopen closed editor
⌘K Enter          Keep preview mode editor open
⌃Tab / ⌃⇧Tab      Open next / previous
⌘K P              Copy path of active file
⌘K R              Reveal active file in Finder
⌘K O              Show active file in new window/instance

Search and replace
⌘F                Find
⌥⌘F               Replace
⌘G / ⇧⌘G          Find next/previous
⌥Enter            Select all occurrences of Find match
⌘D Add            selection to next Find match
⌘K ⌘D             Move last selection to next Find match

Multi-cursor and selection
⌥ + click         Insert cursor
⌥⌘↑               Insert cursor above
⌥⌘↓               Insert cursor below
⌘U                Undo last cursor operation
⇧⌥I               Insert cursor at end of each line selected
⌘L                Select current line
⇧⌘L               Select all occurrences of current selection
⌘F2               Select all occurrences of current word
⌃⇧⌘→ / ←          Expand / shrink selection
⇧⌥ + drag mouse   Column (box) selection
⇧⌥⌘↑ / ↓          Column (box) selection up/down
⇧⌥⌘← / →          Column (box) selection left/right
⇧⌥⌘PgUp           Column (box) selection page up
⇧⌥⌘PgDn           Column (box) selection page down

Debug
F9                Toggle breakpoint
F5                Start/Continue
F11 / ⇧F11        Step into/ out
F10               Step over
⇧F5               Stop
⌘K ⌘I             Show hover

Editor management
⌘W                Close editor
⌘K F              Close folder
⌘\                Split editor
⌘1 / ⌘2 / ⌘3      Focus into 1st, 2nd, 3rd editor group
⌘K ⌘← / ⌘K ⌘→     Focus into previous/next editor group
⌘K ⇧⌘← / ⌘K ⇧⌘→   Move editor left/right
⌘K ← / ⌘K →       Move active editor group

Navigation
⌘T                Show all Symbols
⌃G                Go to Line...
⌘P                Go to File...
⇧⌘O               Go to Symbol...
⇧⌘M               Show Problems panel
F8 / ⇧F8          Go to next/previous error or warning
⌃⇧Tab             Navigate editor group history
⌃- / ⌃⇧-          Go back/forward
⌃⇧M Toggle        Tab moves focus

Rich languages editing
⌃Space            Trigger suggestion
⇧⌘Space           Trigger parameter hints
⇧⌥F               Format document
⌘K ⌘F             Format selection
F12               Go to Definition
⌥F12              Peek Definition
⌘K F12 O          Definition to the side
⌘.                Quick Fix
⇧F12              Show References
F2                Rename Symbol
⌘K ⌘X             Trim trailing whitespace
⌘K M              Change file language
```

