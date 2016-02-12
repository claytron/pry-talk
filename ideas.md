Explain project local pryrc file.

Show off the shell command integration w/interpolation.

Explain the initial context

```ruby
pry(main)> self
pry(main)> self.class
pry(main)> def hello
pry(main)>*  puts 'hello'
pry(main)>*end
pry(main)> edit self.hello
```

Flip between the class and the instantiated object (`cd -`). Add / edit methods. Flip to instance, use them.

```ruby
class User
  def hi
    puts 'hello'
  end
end
```

