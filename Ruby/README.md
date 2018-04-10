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
* [Data Structures](#data-structures)
* [Conditionals](#conditionals)
  * [if/if..else](#if)
  * [case](#case)
  * [ternary operator](#ternary-operator)
  * [or/or..equal](#or)
* [Loops](#loops)
  * [Loop](#loop)
  * [While Loop](#while-loop)
  * [Until Loop](#until-loop)
  * [For Loop](#for-loop)
  * [Iterators](#iterators)
*
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
irb(main):004:0> x = 1.0
=> 1.0
irb(main):005:0> x.class
=> Float
irb(main):006:0> "string".class
=> String
irb(main):007:0> [ 1, 2, 3 ].class
=> Array
irb(main):008:0* { 1 => 'a', 2 => 'b' }.class
=> Hash
irb(main):009:0> (1..5).class
=> Range
irb(main):010:0> a = nil
=> nil
irb(main):011:0> a.class
=> NilClass
```

## Data Structures

Arrays - An ordered, integer-indexed collection of objects.

```ruby
irb(main):001:0> a = []
=> []
irb(main):002:0> a = [1, 2, 3]
=> [1, 2, 3]
irb(main):004:0> a[0]
=> 1
irb(main):005:0> a << 4      # Append to an array. same as a.push(4)
=> [1, 2, 3, 4]
irb(main):006:0> a[4]        # Returns nil if the position does not have value.
=> nil
irb(main):007:0> a[1] = nil
=> nil
irb(main):008:0> a
=> [1, nil, 3, 4]
```

Hash - An unordered, object-indexed collection of objects (or key - value pairs)

```ruby
irb(main):001:0> hash = { 'a' => 0, 'b' => 1, 'c' => 2 } 
=> {"a"=>0, "b"=>1, "c"=>2}
irb(main):002:0> hash['a']
=> 0
irb(main):004:0> hash['d'] = 3
=> 3
irb(main):005:0> hash
=> {"a"=>0, "b"=>1, "c"=>2, "d"=>3}
```

Symbols - A symbol will get stored only once in memory and denoted with :name.

```ruby
irb(main):001:0> "test".object_id
=> 70193267131660
irb(main):002:0> "test".object_id
=> 70193271616400
irb(main):003:0> :test.object_id
=> 358108
irb(main):004:0> :test.object_id
=> 358108
```

Ranges

```ruby
1..10     # .. inclusive range
1...10    # ... exclusive range (excludes 10)
"a".."z"
```

## Conditionals

### if / if..else

Syntax:

```ruby
if boolean
    ...
end

OR

if boolean
    ....
else
    ....
end

OR

if boolean
    ....
elsif boolean
    ....
else
    ....
end

OR

puts "Hello #{name}" if name
```

### unless

Syntax:

```ruby
unless boolean
    ....
end
```

### case

Syntax:

```ruby
case
when boolean
    ....
when boolean
    ....
else
    ....
end
```

### ternary operator

Syntax:

```ruby
boolean?code1:code2

puts a==1? "one":'not one'
```

## or / or..equal

Syntax:

```ruby
x = y||z

# similar to

if y
    x = y
else
    x =z
end
```

```ruby
x ||= y

# Similar to 

unless x
    x = y
end
```

## Loops

### Loop

Syntax:

```ruby
loop do
    ....
end
```

### While Loop

Syntax:

```ruby
while boolean
    ....
end
```

e.g:

```ruby
x = 0
while x < 20
    x += 2
    puts x
end

OR

x = 0
puts x += 2 while x < 20
```

### Until Loop

Syntax:

```ruby
until boolean
    ....
end
```

e.g:

```ruby
x = 0
until x >= 20
    x += 2
    puts x
end

OR

x = 0
puts x += 2 until x >= 20
```

### For Loop

Syntax:

```ruby
for var in array
    ....
end
```

### Iterators

Syntax:

```ruby
iterator do |variable|
    code
end
```

Loop over a list of items or fixed number of times.

```ruby
irb(main):001:0> 5.times { puts 'Hello' }
Hello
Hello
Hello
Hello
Hello
=> 5
irb(main):002:0> 1.upto(5) { puts 'Hello' }
Hello
Hello
Hello
Hello
Hello
=> 1
irb(main):003:0> 5.downto(1) { puts 'Hello' }
Hello
Hello
Hello
Hello
Hello
=> 5
irb(main):004:0> (1..5).each { puts 'Hello' }
Hello
Hello
Hello
Hello
Hello
=> 1..5
```

```ruby
1.upto(5) do |i|
  puts 'Hello ' + i.to_s
end
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

