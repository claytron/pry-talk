autoscale: true

# [fit] Exploring Code
# [fit] with __Pry__!

[@indy.rb][indyrb] 02.2015

-------------------------------------------------------------------------------

# [fit] __Who__ am I?

![][claytron]

claytron on the internets

Senior Software Engineer at TinderBox ![fit][tinderbox]

Debugger afficianado

-------------------------------------------------------------------------------

![inline fit][pry_logo]

> *Pry* is a __powerful__ alternative to the standard *IRB* shell for Ruby.
> It features syntax highlighting, a flexible __plugin__ architecture,
> runtime invocation and __source__ and documentation __browsing__
-- [pryrepl.org][pry]

^ Powerful REPL
Pluggable
Code Browser

-------------------------------------------------------------------------------

# Getting __Started__

```sh
$ gem install pry pry-doc
$ pry
[1] pry(main)> puts 'hello'
hello
=> nil
[2] pry(main)>
```

^ Install pry + pry-doc
Run pry and see the output / return

-------------------------------------------------------------------------------

And now for my first trick...

-------------------------------------------------------------------------------

![inline autoplay fit](movies/string_inspect.mov)

^ See that pry is installed.
Start it up.
Create a string.
`cd` into it.
`ls` it.
`upcase` then `upcase!` it.
`split` it

-------------------------------------------------------------------------------

![inline autoplay fit](movies/pry_edit.mov)

^ `cd` to Pry.
`ls` it.
add a `self.hello` method.
`cd` back to main.
`ls -G` to find the method.
use the method.

-------------------------------------------------------------------------------

# Getting __Help__

```
[1] pry(main)> help
Help
  help               Show a list of commands or information about a specific command.

Context
  cd                 Move into a new context (object or scope).
  ls                 Show the list of vars and methods in the current scope.
  wtf?               Show the backtrace of the most recent exception.

Editing
  edit               Invoke the default editor on a file.

Introspection
  show-doc           Show the documentation for a method or class.
  show-source        Show the source for a method or class.

Input and output
  .<shell command>   All text following a '.' is forwarded to the shell.
  cat                Show code from a file, pry's input buffer, or the last exception.
```

-------------------------------------------------------------------------------

# Getting __Help__

```
[1] pry(main)> help wtf?
Usage: wtf[?|!]

Show's a few lines of the backtrace of the most recent exception (also available
as `_ex_.backtrace`). If you want to see more lines, add more question marks or
exclamation marks.

wtf?
wtf?!???!?!?
```
[//]: # ( Links                                                               )
[//]: # ( ------------------------------------------------------------------- )
[indyrb]: https://twitter.com/indyrb
[claytron]: images/claytron.jpg
[tinderbox]: images/TinderboxLogo.png
[pry]: http://pryrepl.org/
[pry_logo]: images/pry.png
[//]: # ( ------------------------------------------------------------------- )
