# amburn-theme.el
A high contrast amber theme for Emacs.

People talk about how "old" Emacs looks. I say ignore the agists and embrace our long legacy.  The future of Emacs glows as brightly now as the phosphor screens of yore.  Speaking of which, Emacs didn't have an amber theme until now.
         

![amburn](https://user-images.githubusercontent.com/53576362/155818685-6b259781-a1b9-4250-9894-8fcee3511c7e.png)


Disable whatever themes you have enabled using `disable-theme`.

Then call,

```lisp
(load "/path/to/amburn-theme.el")
(load-theme 'amburn t)
```

This theme works best when paired with one of the following True-Type Fonts:
1. https://github.com/lalo/VT220-mod-font
2. https://github.com/svofski/glasstty

Download the font and put it in `~/.local/share/fonts/`, creating any directories that don't exist.

