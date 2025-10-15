# gruvbox-irssi.theme

An Irssi theme suitable for Gruvbox-terminals.

The theme is developed from a fork of Pipeline.theme

(link: https://github.com/hastinbe/irssi-theme-pipeline)

  License: GNU General Public License v2

  - Author: Björn Sundberg <bjorn@forndata.org>
  - Web: https://www.thisoldcabin.net/irssi
  - GitHub: https://github.com/hravnkel/gruvbox-irssi

Takes use of the following scripts: 
   - adv_windowlist.pl
   - usercount.pl
   - sb_separator.pl

A Nerd Font is also mandatory for icons and status bar design. 

## Notes: 
A lot of this theme uses original.theme without changes. Many such variables are located at the bottom of the theme for convenience and added readability. 

### Nicknames in channels: 
The way nicknames in chats are displayed stems from Pipeline.theme by Beau Hastings. 

### Channel hides: 
I personally like a decluttered IRC environment and therefore hide a lot of activity. My preferred setting is: 
  /window hidelevel JOINS PARTS QUITS NICKS HIDDEN
Since the theme relies on visual info about channel activity you should probably consider hiding at least some activity to get a good user experience. 

## Status bar configuration: 
This theme uses three separate status bars: topic, window and awl_x for adv_windowlist.

Within the window list the activity level changes color and/or shows an icon when: 
  - non message text appears
  - someone writes a message
  - a highlighted message appears

### Items are arranged within each window as follows. 

- Statusbar: topic
- Type	   : root  
- Placement: top
- Position : 1
- Visible  : always
- Items    : Name                                Priority  Alignment
  - : topicbarstart                       100       left
  - : separator_2                         10        left
  - : topic                               0         left
  - : topic_empty                         0         left
  - : topicbarend                         100       right

### EXPLANATION: 
The topic bar consists of the standard elements plus an added separator_2 item from the script sb_separator.pl. 
The separator_2 item provides a graphic element + icon in the topic bar. 

- Statusbar: window
- Type     : window
- Placement: bottom
- Position : 0
- Visible  : always
- Items    : Name                                Priority  Alignment
  - : barstart                            100       left
  - : separator                           0         left
  - : user                                0         left
  - : usercount                           0         right
  - : barend                              100       right

### EXPLANATION: 
Due to the way I had to configure the status bar layout I could use a standard method of applying a " " to the left of user with variables 'sb' or 'sbstart' without getting unwanted graphic effects on the window list in awl_x bars. Therefore I added a simple separator item first. 
User item is standard. Usercount stems from the script usercount and is aligned to the right. 
To maintain the layout of this status bar it's at this point not possible to add for example 'time' item. 

- Statusbar: awl_0
- Type     : root
- Placement: bottom
- Position : 0
- Visible  : always
- Items    : Name                                Priority  Alignment
  - : barstart                            100       left
  - : awl_0                               0         left
  - : barend                              100       right

### EXPLANATION: 
This is the standard adv_windowlist.pl way of showing channels windows on a non-tmux / screen terminal. If you use tmux / screen then switch to statusbar mode with the command '/toggle awl_viewer'
The awl_x windows expand and shrink depending on your screen width and number of channels.


Please use this theme as you find suitable and do not hesitate to make your own fork of it. Please share suggestions and/or ideas either on GitHub or via e-mail: bjorn@forndata.org.
