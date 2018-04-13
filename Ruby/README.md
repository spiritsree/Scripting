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
  * [if/if..else](#if-else)
  * [case](#case)
  * [ternary operator](#ternary-operator)
  * [or/or..equal](#or-equal)
* [Loops](#loops)
  * [Loop](#loop)
  * [While Loop](#while-loop)
  * [Until Loop](#until-loop)
  * [For Loop](#for-loop)
  * [Iterators](#iterators)
* [Control Flow](#control-flow)
  * [break](#break)
  * [next](#next)
  * [redo](#redo)
  * [retry](#retry)
* [Methods](#methods)
* [Classes](#classes)
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

### if else

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

## or equal

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
## Control Flow

### break

break - Terminate the whole loop.

```ruby
x = 0
loop do
  x += 1
  puts 'Count ' + x.to_s
  break if x >= 5
end
```

### next

next - Jump to the next loop.

```ruby
x = 0
loop do
  x += 1
  next if x == 3
  puts 'Count ' + x.to_s
  break if x >= 5
end
```

### redo

redo - Redo this loop.

```ruby
a = [ "One", "Two", "Three"]
count = 0
a.each do |element|
  p element
  if element == 'Two'
    count += 1
    redo if count < 3
  end
end
```

### retry

retry - Start the whole loop over.

```ruby
def test
  attempt_again = true
  p 'Testing'
  begin
    # This is the point where the control flow jumps
    p 'About to crash'
    raise 'Boom'
  rescue Exception => e
    if attempt_again
      attempt_again = false
      retry       
    end
  end
end

test
```

## Methods

Methods are functions in ruby.

Syntax:

```ruby
def some_name
    code block
end

some_name
```

```ruby
def some_name(args)
    code block
end

some_name(args)
```

```ruby
irb(main):001:0> def welcome             # defining method
irb(main):002:1>    puts 'Hello World!'
irb(main):003:1> end
=> :welcome
irb(main):004:0> welcome                # calling the method.
Hello World!
=> nil

irb(main):001:0> def welcome             
irb(main):002:1>    return 'Hello World!'  # return gives the string as return value instead on nil.
irb(main):003:1> end
=> :welcome
irb(main):004:0> welcome                
"Hello World!"
```

e.g:

```ruby
def welcome(name="World!")
  return "Hello " + name
end

puts welcome('Mr. X')
greet = welcome
puts greet
```

## Classes

Classes are back-bone of OOP. Class define what an object is and what an object can do.

Syntax:

```ruby
class SomeName
    .....
end

var = SomeName.new
```

e.g:

```ruby
irb(main):001:0> class Animal
irb(main):002:1>   def make_noise
irb(main):003:2>     return "moo!"
irb(main):004:2>   end
irb(main):005:1> end
=> :make_noise
irb(main):006:0> 
irb(main):007:0* animal = Animal.new         # instance - an object created from class.
=> #<Animal:0x007f8a1a849a08>
irb(main):008:0> animal.make_noise
=> "moo!"
```

```ruby
#!/usr/bin/env ruby

class Animal
  def set_noise(noise='Moo!')   # setter method
    @noise = noise              # @noise is an instance variable and be preserved within the instance.
  end
  def make_noise                # getter method
    @noise
  end
end

a1 = Animal.new
a1.set_noise('Quack')
puts a1.make_noise

a2 = Animal.new
a2.set_noise
puts a2.make_noise
```

Output:

```
Quack
Moo
```

**Getter Method**

Syntax:

```ruby
attr_reader :name

OR

def name
  @name
end
```

**Setter Method**

Syntax:

```ruby
attr_writer :name

OR

def name=(value)
    @name = value
end
```

**Getter/Setter Methods**

Syntax:

```ruby
attr_accessor :name

OR

def name
  @name
end

def name=(value)
  @name = value
end
```

**Initialize method**

Initialize method will get initialized when a new class instance in called using .new method.

Syntax:

```ruby
class SomeName
    def initialize(var)
        @var = var
    end
end

SomeName.new(var)
```

**Class Methods**

A method that can be called on a class, even without and instance of the class.

Syntax:

```ruby
class ClassName
    def self.method_name
        .....
    end
end

ClassName.method_name
```

**Class inheritence**

In ruby, class can inherit only from one another class.

Syntax:

```ruby
class SubClassName < ClassName

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

