# vim-autolog-js

This vim plugin allows you to iterate more quickly in javascript by creating a
shortcut key for checking the output of a line of code.

## Installation with vim-plug

Add to `.vimrc`:
```
Plug 'rafpaf/vim-autolog-js'
```

## How to use

Add these mappings to your `.vimrc`:

```vim
map <leader>n :ShowNodeLog<CR>
map <leader>N :MarkLineToLog<CR>
```

Or choose other shortcut keys.

Type `<leader>N` to mark to a line of code with the comment `/*log*/`. Type
`<leader>n` to show the output. (For me, `<leader>` is a comma, so I just type
`,n` and `,N`. That's because I have `let mapleader = ","` in my `.vimrc`.)

For example, suppose your script has a line like this:

```js
isInDict("cat") === true;
```

Typing `<leader>N` marks the line like so:

```js
isInDict("cat") === true; /*log*/
```

Type `<leader>n`, and you'll see this at the bottom of the screen:

```
true          isInDict("cat") === true
```

You can mark multiple lines in the file, and you'll see all the outputs when
pressing `<leader>n`.

If you're using Typescript, add a line like this to the file:

```js
// run as: /path/to/compiled_js_file.js 
```
