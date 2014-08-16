---
layout: post
title:  "Look Ma I Use Vim"
comments: true
date:   2014-08-15 11:07:02
categories: jekyll update
---

I wanted to show my Ma and Pa all the cool vim tricks I know but they couldn't find time to get away from the farm.
So I'm writing a blog post about all my best vim tricks.

# jk
Mapping jk to ESC is good for staying on the home row. Put this: `:imap jk <Esc>` in your vimrc to do so.
MAJOR GOTCHA: If you paste anything with the letters "jk" and you aren't in Paste mode, things will get wonky. Try it.

# cw
Delete a word and go into insert mode all in one motion.

# %
The cursor jumps between parenthesis. Throw this `runtime! macros/matchit.vim`
into your vimrc to turn on jumping between `do end` and the like.

# f, F
"Find". `f` moves the cursor forward to the first occurance of a character. So `f.` will
go to the first period. `F` does the same thing but moves the cursor backwards on the line.

# i (inside)
Do stuff inside quotes or parenthesis. Example: `ci"` would delete text inside quotes and put you in insert mode. Supercool.

# Dot operator
Also known as the period. It repeats your last interaction with text. It works best with insert mode. Making multiple changes
to the ends of a few lines is where I use it most.

# Visual Block
This one is super crazy. `Ctrl-v` gets you into it, and your cursor becomes a huge block. You can then delete or use `Shift i`
on that area.
![alt text](/images/visual_block.gif "Visual Block up in this shit")

# Shift-I
Use this with Visual Block to make the same change on multiple lines. Check out the gif. After making my visual block selection,
I press `Shift i` and my change is repeated everywhere the block is.
![alt text](/images/shift_i.gif "Shift i")

# Recording Macros
Macros are like a more precise dot operator. To use: `q[letter]` starts recording. Your keystrokes are then recorded until you press
`q` again. Using `0` and `f` work great with macros. In the gif I press `qq` to start recording on the q letter. My keystrokes are
`0 f , D`. I then press `q` to stop recording and reuse that macro again 5 lines below.
![alt text](/images/macro.gif "Recording Macros")
