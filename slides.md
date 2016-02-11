autoscale: true

# [fit] Exploring Code
# [fit] with __Pry__!

[@indy.rb][indyrb] 02.2015

-------------------------------------------------------------------------------

# [fit] __Who__ am I?

![][claytron]

claytron on the internets

Senior Software Engineer at TinderBox ![fit][tinderbox]

Debugger aficionado

^ Rubyist for less than a year.
My first official Ruby talk!
Let me know if I'm off base :)

-------------------------------------------------------------------------------

![inline fit][pry_logo]

> *Pry* is a __powerful__ alternative to the standard *IRB* shell for Ruby.
> It features syntax highlighting, a flexible __plugin__ architecture,
> runtime invocation and __source__ and documentation __browsing__
-- [pryrepl.org][pry]

^ Powerful REPL
Pluggable
Code Browser
Q: Who has used Pry? Hasn't?

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

# Anatomy of the __Prompt__

```
[1] pry(main)>
 |   |   |
 |   | Current Context
 |   |
 |  Prompt Name
 |
Command history
```

-------------------------------------------------------------------------------

# [fit] And now for my first trick...

![][trick_image]

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

![inline autoplay fit](movies/pry_source.mov)

^ Show tab completion for `O<tab>`.
`ls OpenStruct`.
`show-doc OpenStruct`.
`show-source OpenStruct`.
`edit OpenStruct`.

-------------------------------------------------------------------------------

![inline autoplay fit](movies/pry_line_editing.mov)

^ Create a `hello` method.
Print out a message.
Mess up the next `puts`.
Use `amend-line` to fix it.
Use `show-input` to see where we are at.
Run the command.
Use `edit` to fix the method.
Run it again.

-------------------------------------------------------------------------------

# Halp!

![original 1300%][halp_image]

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

-------------------------------------------------------------------------------

# Customization


![172%][customize_image]

-------------------------------------------------------------------------------

`vim ~/.pryrc`

-------------------------------------------------------------------------------

# Repeat Last Command

```ruby
# Hit Enter to repeat last command
Pry::Commands.command(/^$/, 'repeat last command') do
  last_command = Pry.history.to_a.last
  unless ['c', 'continue', 'q', 'exit-program', 'quit'].include? last_command
    _pry_.run_command last_command
  end
end
```

-------------------------------------------------------------------------------

# Aliases

```ruby
# Single letter and pdb like aliases
if defined?(PryByebug)
  Pry.commands.alias_command 'c', 'continue'
  Pry.commands.alias_command 's', 'step'
  Pry.commands.alias_command 'n', 'next'
  Pry.commands.alias_command 'return', 'finish'
  Pry.commands.alias_command 'r', 'finish'
  Pry.commands.alias_command 'f', 'finish'
  Pry.commands.alias_command 'q', 'exit-program'
  Pry.commands.alias_command 'quit', 'exit-program'
end
```

-------------------------------------------------------------------------------

# Other Stuff

```ruby
# Turn off the automatic pager
Pry.config.pager = false

# Make the prompt silly
# [1] oh no!(main)>
Pry.config.prompt_name = 'oh no!'
```

-------------------------------------------------------------------------------

# Plugins

![240%][plugins_image]

-------------------------------------------------------------------------------

# pry-awesome_print

Automatically `ap` return value

Use semi-colon to silence return value

```
[1] pry(main)> x = {foo: :bar, baz: :bang}
=> {:foo=>:bar, :baz=>:bang}
[2] pry(main)> x = {foo: :bar, baz: :bang};
[3] pry(main)>
```

-------------------------------------------------------------------------------

# pry-byebug

Make Pry act like an actual debugger

Adds `next`, `step`, `continue`, etc.

-------------------------------------------------------------------------------

# pry-stack_explorer

Show the call stack

Go up and down the call stack

-------------------------------------------------------------------------------

# pry-clipboard

Quickly copy history or output to the clipboard

Works cross platform via the `clipboard` gem

-------------------------------------------------------------------------------

# pry-rails

Automatically use Pry instead of IRB for `rails console`

Commands to inspect models and routes

-------------------------------------------------------------------------------

# Debugging

![][debugging_image]

-------------------------------------------------------------------------------

# Runtime Invocation

```ruby
require 'pry'
binding.pry
```

-------------------------------------------------------------------------------

![inline autoplay fit](movies/debugging.mov)

^ Add a binding.pry.
Step into `write_fortune`.
Use `next` across a few lines.
Print the `text` variable.
Do `text.split('%')`
Do `puts text.split('%')[1];`
Finish out by `continue` -ing

-------------------------------------------------------------------------------

# Links

- [Pry][pry]
- [Repeat last command][last_command]
- [Command Aliases][command_aliases]

-------------------------------------------------------------------------------

# Photo Credits

- And now for my first trick... ([@vtornick][trick_credit])
- Halp! ([@daveblog][halp_credit])
- Customize ([@hz536n][customize_credit])
- Plugins ([@antpaniagua][plugins_credit])
- Debugging ([@eduardox][debugging_credit])

[//]: # ( Links                                                               )
[//]: # ( ------------------------------------------------------------------- )
[indyrb]: https://twitter.com/indyrb
[claytron]: images/claytron.jpg
[tinderbox]: images/TinderboxLogo.png
[pry]: http://pryrepl.org/
[pry_logo]: images/pry.png
[last_command]: https://github.com/claytron/dotfiles/blob/master/.pryrc#L7
[command_aliases]: https://github.com/claytron/dotfiles/blob/master/.pryrc#L15

[//]: # ( CC Images                                                           )
[//]: # ( ------------------------------------------------------------------- )
[trick_image]: images/trick.jpg
[trick_credit]: https://flic.kr/p/6psgfH
[halp_image]: images/halp.jpg
[halp_credit]: https://flic.kr/p/7sVMkt
[customize_image]: images/customize.jpg
[customize_credit]: https://flic.kr/p/cK5q45
[plugins_image]: images/plugins.jpg
[plugins_credit]: https://flic.kr/p/dmFGqt
[debugging_image]: images/debugging.jpg
[debugging_credit]: https://flic.kr/p/4wDL2b
[//]: # ( ------------------------------------------------------------------- )
