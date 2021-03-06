Development has moved to: https://codeberg.org/excalamus/amburn-theme.el

# amburn-theme.el
A high contrast amber theme for Emacs.

People talk about how "old" Emacs looks. I say ignore the agists and embrace the legacy.  The future of Emacs glows as brightly now as the phosphor screens of yore.
         

![amburn](https://user-images.githubusercontent.com/53576362/155818685-6b259781-a1b9-4250-9894-8fcee3511c7e.png)


Disable whatever themes you have enabled using `disable-theme`.

Then call,

```lisp
(load "/path/to/amburn-theme.el")
(load-theme 'amburn t)
```

The retro VT220 font [Glass_TTY_VT220.ttf](https://github.com/excalamus/amburn-theme.el/blob/main/Glass_TTY_VT220.ttf) is included with `amburn-theme.el` for extra fun.

Put the font file in `~/.local/share/fonts/`, creating any directories that don't exist.

Enable the font using:

```lisp
;; Height values in 1/10pt, so 100 will give you 10pt, etc.
(set-face-attribute 'default nil
                    :font "Glass TTY VT220"
                    :height 150)
```

# Modifying

Amburn is built using three colors: 

* `amburn-fgl` (foreground light)
* `amburn-fgd` (foreground dark)
* `amburn-bg` (background)

The default colors come from here: https://retrocomputing.stackexchange.com/a/12837

First, all faces in Emacs are set to "fgd-on-bg".

Next, faces are set in bulk according to package.  Use the following variables to set the color for a package:

* `amburn-bulk-fgl-on-bg` 
* `amburn-bulk-fgd-on-bg`
* `amburn-bulk-bg-on-fgd`
* `amburn-bulk-bg-on-fgl`

The variable should hold a list of cons cells where the car is the filename and the cdr is the package namespace.  For example, the following sets fgd-on-bg for the `font-lock` package which has filename "font-lock.el" and namespace "font-lock-":

```lisp
(setq amburn-bulk-fgd-on-bg
      '(
        (font-lock . "font-lock-")
        ))
```

Finally, individual faces are set using one of:

* `amburn-individual-fgl-on-bg`
* `amburn-individual-fgd-on-bg`
* `amburn-individual-bg-on-fgl`
* `amburn-individual-bg-on-fgd`

Each of these is a list of faces to color accordingly.  For example,

```lisp
(setq amburn-individual-bg-on-fgl
      '(
        error
        secondary-selection
        success
        warning
        ))
```
