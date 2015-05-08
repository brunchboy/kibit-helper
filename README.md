# kibit-helper

A set of Emacs Lisp functions to make it very easy to work with [Kibit](https://github.com/jonase/kibit) inside GNU Emacs.

## Installation

Available as a package in melpa.org

```lisp
(add-to-list 'package-archives
             '("melpa" . "http://melpa.org/packages/") t)
```
    M-x package-install kibit-helper

## Usage

    M-x kibit
    M-x kibit-current-file
    M-x kibit-accept-proposed-change

You will likely want to bind the last function to <kbd>C-x</kbd>
<kbd>C-\`</kbd> so it is easy to alternate with the `next-error`
function (conventionally <kbd>C-x</kbd> <kbd>\`</kbd>) as you walk
through the suggestions made by Kibit:

```lisp
(global-set-key (kbd "C-x C-`") 'kibit-accept-proposed-change)
```

## Known limitations

Some changes cannot be automatically applied. Kibit strips comments
from the source code, and so they will be missing from both the
"original" and suggested versions of the code being examined. You will
need to manually apply these changes, and kibit-accept-proposed-change
will tell you when that happens. It will also tell you if you seem to
be running it twice on the same change, i.e. the suggested
improvements have already been made.

You may also want to use it in this mode from time to time just
because the act of manually applying the changes can help you learn
and internalizd the idioms they represent.

## Related packages

This package does not require
[Cider](http://www.github.com/clojure-emacs/cider), although if you
are working with Clojure in Emacs, you should almost certaily be using
it.

