# grails.el

Grails.el is an Emacs minor mode that allows an easy navigation 
of Grails projects.

## Features

Grails.el allows you to __fast open__ a domain class, a controller 
or service just typing it's name. Moreover __it can jump__ from the current
domain|controller|service to the relative domain|controller|service.

This minor mode __doesn't have any external dependencies__ and works nicely 
with Grails 2 and __Grails 3__ projects.

### Demo

![Emacs grails.el demo](https://raw.githubusercontent.com/lifeisfoo/emacs-grails/master/res/emacs-grails-el-demo.gif)

### Available commands
  
| Shortcut | Effect | Example |
| -------- | ------ | ------- |
| `C-c` `-` `d`  | Open the Domain class relative to the current file | If current file is `controllers/UserController.groovy`, it opens  `domain/User.groovy` |
| `C-c` `-` `c`  | Open the Controller class relative to the current file | If current file is `domain/User.groovy`, it opens  `controllers/UserController.groovy` |
| `C-c` `-` `s`  | Open the Service class relative to the current file | If current file is `controllers/UserController.groovy`, it opens  `services/UserService.groovy` |
| `C-c` `-` `n` `d`| Ask for a class name and open to the relative Domain class | If `name` is `User`, it opens  `domain/User.groovy` |
| `C-c` `-` `n` `c`| Ask for a class name and open to the relative Controller class | If `name` is `User`, it opens  `controllers/UserController.groovy` |
| `C-c` `-` `n` `s`| Ask for a class name and open to the relative Service class | If `name` is `User`, it opens  `services/UserService.groovy` |

#### Class names with packages
Class names with __packages are fully supported__.

- `C-c` `-` `c` (if current buffer is `domain/my/package/User.groovy`) will open `controllers/my/package/UserController.groovy` 
- `C-c` `-` `n` `c` `my/package/User` will open `controllers/my/package/UserController.groovy`

## Installation

Copy this file to to some location in your Emacs load path.  Then add
`(require 'grails)` to your Emacs initialization (.emacs,
init.el, or something):

    (require 'grails)

## Configuration

Then, to auto enable grails minor mode, create a .dir-locals.el file
in the root of the grails project with this configuration:

    ((groovy-mode (grails . 1))
     (html-mode (grails . 1))
     (java-mode (grails . 1)))

In this way, the grails minor mode will be auto enabled when any of
these major modes are loaded (only in this directory tree - the project tree)
(you can attach it to other modes if you want).

The first time that this code is executed, Emacs will show a security
prompt: answer "!" to mark code secure and save your decision (a configuration 
line is automatically added to your .emacs file).

### Grails minor mode always enabled

In order to have grails minor mode always enabled inside your project tree,
place inside your `.dir-locals.el`:

    ((nil . ((grails . 1))))

## Contributing
Pull requests are welcome. 

Check open issues for feature requests or current bugs.

## License

This software is released under the [GPL license version 3](http://www.gnu.org/licenses/gpl-3.0.en.html), or (at your option) any later version.
