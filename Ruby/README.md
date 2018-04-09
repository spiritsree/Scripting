# Ruby

Everything in ruby is an object. Objects are instances of a class.

```
$ ruby file.rb

OR

$ irb
```

## Contents

* [Comment](#comment)
* [Printing](#printing)
* [Variable Assignment](#variable-assignment)
* [Documentation](#documentation)

## Comment

Comments are added with '#' prefix.

```ruby
# This is a comment
```

## Printing

```ruby
puts 'Hello World !'       # puts prints a line return at the end.
print 'Hello World !'      # print doesn't give a line return at the end of line.
print('Hello World !')
```

## Variable Assignment

Variable scope.

```
Global		$variable
Class		  @@variable
Instance	@variable
Local 		variable
Block 		variable
```

```ruby
irb(main):010:0> x = 0
=> 0
irb(main):011:0> y = x
=> 0
irb(main):012:0> var = 'a'
=> "a"
```

## Documentation

```
http://ruby-doc.org/
```

```
$ ri <module>
```

e.g:

```
$ ri upcase
$ ri String#upcase
```

