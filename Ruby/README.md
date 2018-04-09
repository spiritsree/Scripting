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
* [Variable Interpolation](#variable-interpolation)
* [Type of a Value](#type-of-a-value)
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
Class		@@variable
Instance	@variable
Local 		variable
Block 		variable
```

```ruby
irb(main):001:0> x = 0
=> 0
irb(main):002:0> y = x
=> 0
irb(main):003:0> var = 'a'
=> "a"
```

## Variable Interpolation

```ruby
irb(main):009:0> puts "Value of x is #{x}"
Value of x is 0
=> nil
irb(main):007:0> greeting = "Hello"
=> "Hello"
irb(main):008:0> puts greeting + ' World!'
Hello World!
=> nil
```

## Type of a Value

To get the type of an object, use '.class' method.

```ruby
irb(main):001:0> 1.class
=> Fixnum
irb(main):002:0> 1234567890123456789234384834343.class
=> Bignum
irb(main):003:0> 1.0.class
=> Float
irb(main):005:0> x = 1.0
=> 1.0
irb(main):006:0> x.class
=> Float
irb(main):006:0> "string".class
=> String
irb(main):007:0> [ 1, 2, 3 ].class
=> Array
irb(main):012:0* { 1 => 'a', 2 => 'b' }.class
=> Hash
irb(main):015:0> (1..5).class
=> Range
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

