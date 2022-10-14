## vim setup and cheatsheet

Topics: [[vim]] [[cheatsheet]] [[commands]]  

---
# `vim` command cheatsheet and related information

## Shell script for quick customisation of .vimrc 
- Adds Molokai color scheme
- Adds some VIM options including line numbers and highlighting
- Installs for the current user.
- To use the custom .vimrc preferences when using `sudo` run `sudo -E vim <filename>`
- Does use `apt` to install and remove VIM (edit script if you don't want this function).
- Tested on Debian based OS.

### Learn VIM resources
- https://www.vimified.com/


#### Usage: Download and edit ![[vimconfig.sh]] script or use the one-liner below:
`bash -c "$(wget -O- https://raw.githubusercontent.com/bradsec/notes/main/101_vim/vimconfig.sh"`

## VIM Cheatsheet (Keyboard Commands)
### Movement
```terminal
h               move cursor left
j               move cursor down
k               move cursor up
l               move cursor right
G               move to the bottom of file
gg              move to the top of the file
0 (zero)        move to the beginning of line
$               move to the end of line
:#              move to line number # (replace # with the number)
H               (H)igh - move to the top of the screen
M               (M)iddle - move to the middle of the screen
L               (L)ow - move to the bottom of the screen
#h [j/k/l]      move in a specified direction multiple times
b / B           move to the start of a word / token
w / W           move to the start of the next word / token
e / E           move to the end of a word / token
Ctrl+b          move back one full screen
Ctrl+f          move forward one full screen
Ctrl+d          move forward 1/2 a screen
Ctrl+u          move back 1/2 a screen
Ctrl+e          move screen down one line (without moving cursor)
Ctrl+y          move screen up one line (without moving cursor)
Ctrl+o          move backward through the jump history
Ctrl+i          move forward through the jump history
```
### Search and Replace
#### Search
```terminal
*               jump to the next instance of a word
#               jump to the previous instance of a word
/pattern        search forward for the specified pattern
?pattern        search backward for the specified pattern
n               repeat the search in the same direction
N               repeat the search in the opposite direction
```
#### Replace
```terminal
:%s/old/new     replace the first match of {old} with {new}
:%s/old/new/g   replace all matches of {old} with {new}
:%s/old/new/gc  confirm each match replacement of {old} with {new}
```
### Copy / Cut / Paste
#### Copying
```terminal
yy              copy an entire line
#yy             copy the specified # number of lines
yaw             copy a word with its trailing whitespace
yiw             copy a word without its trailing white-space
y$              copy everything right of the cursor
y^              copy everything left of the cursor
ytx             copy everything between the cursor and
                a specified character (x)
yfx             copy everything between the cursor and
                a specified character (including that character)
```
#### Cutting
```terminal
dd              cut the entire line
#dd             cut # number of line
d$              everythinrg right of the cursor
```
#### Pasting
```terminal
p               paste text after the cursor
P               paste text before the cursor 
```
### Marking
```terminal
v               marking text using character mode
V               mark lines using line mode
Ctrl+v          mark text using block mode
gv              Reselect block
o               move from one end of the marked text to the other
aw              mark a word
ab              mark a block with ()
aB              mark a block with {}
at              mark a block with <>
ib              mark inner block ()
iB              mark inner block {}
it              mark inner block <>
y               yank (copy) the marked text
d               delete (cut) the marked text
p               paste the text after the cursor
u               change the marked text to lowercase
U               change the marked text to uppercase
```
### Editing
#### Insert
```terminal
i               insert text before the cursor
I               insert text at the beggining of the line
s               delete a character (+ move into insert mode)
```
#### Append
```terminal
a               append text after the cursor
A               append text at the end of the line
ea              append text at the end of the word
```
#### New Line
```terminal
o               open a new line below the current one
O               open a new line above the current one
```
#### Replace
```terminal
r               replace a single character (+ return to command mode)
cc              replace entire line (+ move into insert mode)
C / c$          replace from cursor to the end of line
cw              replace from cursor to the end of the word
```
#### Delete
```terminal
dd / D          delete a single line
dw              delete a single word
#dd / d#d       delete multiple lines (replace # with number)
:#,#d           delete a range of lines (replace # with number)
:%d             delete all lines
:.,$d           delete from current line to the end of the file
dgg             delete from current line to the beginning of file
:g/pattern/d    delete lines containg a specified pattern
:g!/pattern/d   delete lines that don’t contain a specified pattern
:g/^$/d         delete all blank lines
```
#### Undo
```terminal
u / :u / :undo  undo changes made in last entry
#u              undo # number of changes
U               undo latest changes in line
```
#### Redo
```terminal
Ctrl+r          redo mulitple changes
#Ctrl+r         redo # number of changes
```
### Macros
```terminal
qa              record macro (a)
q               stop recording macro
@a              run macro (a)
@@              run last macro again
```
### Multiple Windows
```terminal
:e filename     open file in new buffer
:sp filename    open filename in split horizontal viewport
:vs filename    open filename in split vertical viewport
:vert ba        edit all files in vertical viewports
:tab ba				edit all buffers as tabs
gt              move to next tab
gT              move to previous tab
Ctrl+ws         split viewport horizontally
Ctrl+wv         split viewport vertically
Ctrl+ww         switch viewports
Ctrl+wq         quit a viewport
Ctrl+wx         exchange current viewport for next
Ctrl+=          make all viewports equal size
:hide           close current window
:only           keep only this window open
:ls             show current buffers
:bn             move to next buffer
:bp             move to previous buffer
:bd             close buffer
:b filename     move to buffer by filename
:b#             move to buffer number #
```
### File Management Save / Quit
```terminal
:q              quits if no changes were made
:q! / ZZ        force quit without saving changes
:w              save/write the current file
:w filename     save/write as specified filename
:w !sudo tee %  write out the current file using sudo
:wq / ZQ        save/write the file and quit
:wq!            save/write/quit the file even if readonly
```

