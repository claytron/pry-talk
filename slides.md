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
[//]: # ( Links                                                               )
[//]: # ( ------------------------------------------------------------------- )
[indyrb]: https://twitter.com/indyrb
[claytron]: images/claytron.jpg
[tinderbox]: images/TinderboxLogo.png
[pry]: http://pryrepl.org/
[pry_logo]: images/pry.png
[//]: # ( ------------------------------------------------------------------- )
