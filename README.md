# Geany for front-end developer

## Introduction

[Geany](http://geany.org) is a lightweight & fast IDE that is based on Scintilla source code editing component and uses GTK2 toolkit for GUI. Geany can run on Linux, Windows & Mac OS.

By default, Geany has some basic code highlighting for JavaScript & other front-end languages (quite comparable with the acclaimed SublimeText 2) but it leaves a lot of room for improvement via user-defined configuration files.

This package is a collection of configuration files to enhance Geany's source code highlighting and autocompletion for HTML/CSS/JavaScript, languages of front-end developers. (ActionScript is to be considered later).

## Installing latest Geany build

These config files were tested with the dev build of Geany, version 1.22. Although they may also work for latest stable build 0.21.

Binary builds for latest Geany in Linux & Windows can be found [here](http://nightly.geany.org).

## How to install these supplement files

- Copy the files in 'config/geany' folder to equivalent Geany's user config folder.
- On Linux, the Geany's user config folder is at **/home/username/.config/geany**
    - I have written an **install.sh** script to conveniently install the files on Linux:

        Open terminal and cd to the source of this project. Then
       
        ```shell
        chmod +x install.sh
        ./install.sh
```
- For other OS, refer to [this manual](http://www.geany.org/manual/current/index.html#configuration-file-paths) to identify user's config folder.

-----------------------------------

# The Enhancement

## 1. Snippets

With snippets, you can complete a whole block of code from short string like `if` or `for`. More on Geany's snippets configuration file at [this link](http://www.geany.org/manual/current/index.html#user-definable-snippets).

### The file:

- **snippets.conf**: The javascript section of this file has been modified so that braces are inserted and alignments are made according to common Javascript convention.

### How To:

To insert snippets into code editor, type the snippet keywords and press Tab. (For current Geany, no hinting popup will be displayed).

Supported snippets in this package:
`if`, `else`, `for`, `forin`, `while`, `do`, `switch`, `try`, `function` (NEW), `copyright` (NEW), 
`author` (NEW). 

Please edit your `author` name and `copyright` at [Default] section.

## 2. Keywords Highlighting

Language specific syntax highlighting are defined in filetype definition files in **filedefs** folder. For detailed guide on filetype definitions, refer to [this section](http://www.geany.org/manual/current/index.html#filetype-definition-files) of the manual.

### The files:

- **filedefs/filetypes.css**: This file lets Geany highlight latest CSS keywords properly. It contains up-to-date standard CSS1/2/3 as well as browser specific keywords. Besides, minor coloring rules have been patched to make CSS3 & prefixed keywords distinct from CSS1/2 ones.  
    ![Better CSS highlighting](ref/img/css_highlighting.png)

    Source of reference: [meiert.com](http://meiert.com/en/indices/css-properties/)

## 3. Code Hinting

**geany/tags** folder contains Geany's global tag files. These files will allow code-hinting and keywords auto-completion in Geany editor for a targeted filetype.

To learn more about Geany's tags, refer to [this section](http://www.geany.org/manual/current/index.html#tags) of the mannual.

### The files:

- **tags/std.css.tags**: As the name implied, this tag file enables code hinting for standard CSS (including CSS3) property names.
- **tags/prefixed.css.tags**: Code hinting for browser specific CSS property names.
- **tags/std.js.tags**: Code hinting for standard Javascript API. [incompleted]
- **tags/dom.js.tags**: Code hinting for Browser and DOM objects Javascript. [incompleted]
- **tags/styles.js.tags**: This file supplement JS property names of CSSStyleDeclaration object which are directly converted from the stadard CSS property names.
- **tags/mootools-core.js.tags**: (Extra) Code hinting for JS Mootools 1.4 framework

Source of references: [MDN](https://developer.mozilla.org/en/JavaScript/Reference), [JavaScript Kit](http://www.javascriptkit.com/jsref/), [Mootools Doc](http://mootools.net/docs/core)

### How To:

- Type at least 1 character and press Ctrl-Space to display the auto-completion popup. OR type in the first 4 characters of the keyword. (These number of characters can be changed in preference). 
- While the auto-completion popup appear, you can: 
  - press Up/Down to select a keyword; 
  - press Enter to complete the whole keyword;
  - press Tab to complete a word portion 
  - press press escape to close the pop  
    ![JS code hinting](ref/img/js-code-hinting.png)
- For function keywords, there is function parameters hint box to be displayed as soon as you type in function call bracket "(".
![JS function parameter hinting](ref/img/js-function-hinting.png)
- You can call this parameters hint box by pressing Ctrl-Shift-Space while the cursor is within brackets.
- If a function keyword has duplicated entries, the hinting box will be shown with arrow button to select.

## 4. Additional settings for ease of use

### Additional color schemes:
Visit [this github project](https://github.com/codebrainz/geany-themes) to download more color schemes for Geany 1.22+

### Recommended preferences:
Go to Preferences of Geany (shortcut Ctrl-Alt-P), do:

- Editor > Completions > Character to type...: 2
- Editor > Completions > Auto close brackets: select all except '' (or your choice)
- Editor > Completions > Auto complete all words
- Editor > Features > Comment toggle marker: clear the text box

![Editor completion preferences](ref/img/editor-completion-preferences.png)

You may also want to change these key binding to make Geany behave similarly to SublimeText or Webstorm

- Key Bindings > Format > Toggle line commentation: <Primary>slash
- Key Bindings > Editor > Move line(s) up: <Primary><Shift>Up
- Key Bindings > Editor > Move line(s) down: <Primary><Shift>Down

> Note: **<Primary>** is actually Ctrl on Linux/Windows

-----------------------------------

# Creator's Guide

[To be written]
