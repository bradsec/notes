## tmux cheatsheet commands

Topics: [[tmux]] [[cheatsheet]] [[commands]]  

---

## Manage Sessions  
```terminal
tmux 									Create new session with default session name
tmux new 								Create new session with default session name
tmux new-session 						Create new session with default session name
tmux new -s session_name 				Creates a new session called “session_name.”
Ctrl+b : 								Enters command mode
Ctrl+b :new -s session_name 			Creates new session within an existing session
tmux ls 								List active tmux sessions
tmux list-sessions 						List active tmux sessions
Ctrl+b s 								List active tmux sessions
tmux a -t session_name 					Attaches to session by the name "session_name"
tmux at -t session_name 				Attaches to session by the name "session_name"
tmux attach -t session_name 			Attaches to session by the name "session_name"
tmux attach-session -t session_name 	Attaches to session by the name "session_name"
tmux kill-ses -t session_name 			Kills session by the name "session_name"
tmux kill-session -t session_name 		Kills session by the name "session_name"
Ctrl+b d 								Detaches from the session, leaving the session running in the background.
Ctrl+b $ 								Rename the session name
Ctrl+b ( 								Move to the previous session
Ctrl+b ) 								Move to the next session
```
## Help  
```terminal
Ctrl+b ? 								Show the list of bind options
Ctrl+s 									In the bind help section search for string
```
## Manage Panes  
```terminal
Ctrl+b % 								Divides the current window in half vertically.
Ctrl+b " 								Divides the current window in half horizontally
Ctrl+b o 								Cycles through open panes
Ctrl+b q 								Momentarily displays pane numbers in each pane
Ctrl+b x 								Closes the current pane after prompting for confirmation
Ctrl+b & 								Closes the current window after prompting for confirmation
Ctrl+b & 								Closes the current window after prompting for confirmation
Ctrl+b space 							Cycles through the various pane layouts
Ctrl+b { 								Move the current pane to left
Ctrl+b } 								Move the current pane to right
Ctrl+b ⇑ 								Switch to the pane above the current pane
Ctrl+b ⇓ 								Switch to the pane below the current pane
Ctrl+b ⇐ 								Switch to the pane on the left side of the current pane
Ctrl+b ⇒ 								Switch to the pane on the right side of the current pane
Ctrl+b z 								Toggle pane zoom
Ctrl+b ! 								Combine and Convert all the panes into single window
Ctrl+b :setw synchronize-panes 			To synchronise all the panes
Ctrl+b :setw synchronize-panes off 		To turn off synchronisation between all the panes
```
## Manage Windows  
```terminal
Ctrl+b c 								Creates a new window from within an existing tmux session
Ctrl+b w 								Displays a list of windows in the current session
Ctrl+b n 								Moves to the next window
Ctrl+b p 								Moves to the previous window
Ctrl+b 0..9 							Selects windows by number
Ctrl+b l 								Go to the last window
Ctrl+b , 								Displays a prompt to rename a window
Ctrl+b & 								Closes the current window after prompting for confirmation
Ctrl+b x 								Closes the current window after prompting for confirmation
Ctrl+b f 								Searches for a window that contains the text you specify
```
