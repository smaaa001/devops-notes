# devops-notes

> Personal DevOps learning notes covering Linux, networking, SSH, backend deployment practices and others as needed.

Basic tmux terminal command that I use regularly.

---

### Note: `<value>` represents a variable to be replaced with actual value

## Basic Commands (in host terminal)

---


```bash
tmux                      # start tmux terminal

tmux list-key             # list keys (binding)

exit                      # exit tmux
```


## Basic Commands (in tmux command prompt)

---


```text
Session ------- Window --------Pane 1
        |              |
        |              |_______Pane 2
        |
        |_______Window
        
```

```bash
tmux                      # start tmux terminal

splitw -h                 # split current active window horizontally (creates panes)
splitw -v                 # split current active window vertically (creates panes)





resize-pane -[L|R|D|U] 5          # Resize pane by 5 unit

kill-pane                         # kill active pane
```



## Keyboard Bindings inside Tmux Terminal

---

<table>
    <tr>
        <th>Key Bindings</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>control + b</td>
        <td>Prefix Key to enter tmux command</td>
    </tr>
</table>


### Note: The following commands are followed by the prefix key.

---

<table>
    <tr>
        <th>Key Bindings</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>shift + ;</td>
        <td>tmux command prompt</td>
    </tr>
    <tr>
        <td>Arrow keys (Up, Down, Left, Right)</td>
        <td>Navigate between windows</td>
    </tr>
    <tr>
        <td>q</td>
        <td>Display pane index. <b>Press any number to navigate to that pane</b></td>
    </tr>
</table>



## ~/.tmux.conf

---

```text
bind -r h resize-pane -L 1          # resize active pane by 1 unit to the left
bind -r l resize-pane -R 1
bind -r j resize-pane -U 1
bind -r k resize-pane -D 1
```


### Note: Custom binding. Press control+b then select `[h|l|j|k]`
