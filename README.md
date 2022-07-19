[![MELPA][melpa-badge]][melpa-package]
[![MELPA Stable][melpa-stable-badge]][melpa-stable-package]

# adoc-mode

## Introduction

[AsciiDoc](https://asciidoc.org/) is a text document format for
writing short documents, articles, books and UNIX man pages. AsciiDoc files
can be translated to HTML and DocBook markups.

`adoc-mode` is an Emacs major mode for editing AsciiDoc files. It emphasizes on
the idea that the document is highlighted so it pretty much looks like the
final output. What must be bold is bold, what must be italic is italic etc.
Meta characters are naturally still visible, but in a faint way, so they can
be easily ignored.

## Installation

`adoc-mode` is available on the community-maintained
[MELPA Stable][] and [MELPA][] repos.

NonGNU ELPA and MELPA Stable are recommended as they have the latest stable version.
MELPA has a development snapshot for users who don't mind breakage but
don't want to run `adoc-mode` from a git checkout.

You can install `adoc-mode` using the following command:

<kbd>M-x package-install [RET] adoc-mode [RET]</kbd>

or if you'd rather keep it in your Emacs config:

```emacs-lisp
(unless (package-installed-p 'adoc-mode)
  (package-refresh-contents)
  (package-install 'adoc-mode))
```

If the installation doesn't work try refreshing the package list:

<kbd>M-x package-refresh-contents</kbd>


## Configuration

* According to an old AsciiDoc manual, .txt is the standard file extension of
  AsciiDoc files. Add the following to your initialization file to open all
  .txt files with adoc-mode as major mode automatically: `(add-to-list
  'auto-mode-alist (cons "\\.txt\\'" 'adoc-mode))`.
  More recent conventions for AsciiDoc file extensions include `.adoc` and
  `.asciidoc`, these are associated automatically.

* If your default face is a fixed pitch (monospace) face, but in AsciiDoc
  files you liked to have normal text with a variable pitch face,
  buffer-face-mode is for you: `(add-hook 'adoc-mode-hook (lambda()
  (buffer-face-mode t)))`


## Features

- sophisticated highlighting

- promote / demote title

- toggle title type between one line title and two line title

- adjust underline length of a two line title to match title text's length

- goto anchor defining a given id, default reading from xref at point

- support for outline (however only with the one-line title style)

### Coming features

The next features I plan to implement

- Demote / promote for list items
- Outline support also for two line titles
- Correctly highlighting backslash escapes

## Screenshot

The highlighting emphasizes on how the output will look like. _All_
characters are visible, however meta characters are displayed in a faint way.

![screenshot](http://dl.dropbox.com/u/75789984/adoc-mode.png)

## License

Copyright © 2010-2013 Florian Kaufmann

Distributed under the GNU General Public License; type <kbd>C-h C-c</kbd> to view it.

[melpa-badge]: http://melpa.org/packages/adoc-mode-badge.svg
[melpa-stable-badge]: http://stable.melpa.org/packages/adoc-mode-badge.svg
[melpa-package]: http://melpa.org/#/adoc-mode
[melpa-stable-package]: http://stable.melpa.org/#/adoc-mode
[melpa]: http://melpa.org
[melpa stable]: http://stable.melpa.org
