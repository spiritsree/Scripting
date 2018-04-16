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
* [Modules](#modules)
* [Operators](#operators)
  * [Comparison Operators](#comparison-operators)
  * [Logical Operators](#logical-operators)
  * [Arithmetic Operator](#arithmetic-operator)
  * [Bitwise Operator](#bitwise-operator)
* [File I/O](#file-io)
* [Built-in Methods](#built-in-methods)
  * [Numeric Methods](#numeric-methods)
  * [String Methods](#string-methods)
  * [Container Methods](#container-methods)
  * [Boolean Methods](#boolean-methods)
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
irb(main):012:0> 1.upto(5).class
=> Enumerator
irb(main):013:0> (5 > 2).class
=> TrueClass
irb(main):014:0> (5 < 2).class
=> FalseClass
irb(main):014:0> :test.class
=> Symbol
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

**Subclass Overriding**

```ruby
class Animal
 def initialize(name, color)
    @name = name
    @color = color
  end
 def color
   return "#{@color}"
  end
end

class Cow < Animal
  def color                                  # This overrides the super class method.
    scolor = super                           # use super to access the super class.
    puts "Cow's color is #{@color} and parent color is #{scolor}"
  end
end

animal = Cow.new('Maisie', 'Black')
animal.color
```

## Modules

Modules are wrappers around ruby code.</br>
Modules can't be instantiated.</br>
Modules are used in conjunction with classes.

Syntax:

```ruby
module ModuleName
    ....
end

class ClassName
    include 'ModuleName'
    ....
end

OR

module ModuleName
    class ClassName
        ....
    end
end

something = ModuleName::ClassName.new      # namespacing, to avoid conflicting classes.
```

Ruby allows classes to inherit from one superclass. Mixin helps to avoid this issue by including modules.

```ruby
module ContactInfo
  attr_accessor :first_name, :last_name, :city, :state, :zip_code
  
  def full_name
    return @first_name + " " + @last_name
  end
  
  def city_state_zip
    csz = @city
    csz +=", #{@state}" if @state
    csz +=" #{@zip_code}" if @zip_code
    return csz
  end
end

class Person
  include ContactInfo
end

class Teacher
  include ContactInfo
  attr_accessor :lesson_plans
end

class Student < Person
  attr_accessor :books, :grades
end
```
You can use the above module as below.

```ruby
irb(main):001:0> load './person.rb'
=> true
irb(main):002:0> person = Person.new
=> #<Person:0x007fef5f04d7a0>
irb(main):003:0> person.first_name='Sreejith'
=> "Sreejith"
irb(main):004:0> person.last_name='G'
=> "G"
irb(main):005:0> person.full_name
=> "Sreejith G"
```

**load**

Loads the source file every single time its called.

```ruby
irb(main):001:0> load './person.rb'
=> true
irb(main):002:0> load './person.rb'
=> true
```

**require**

Loads the source file only once.

```ruby
irb(main):001:0> require './person.rb'
=> true
irb(main):002:0> require './person.rb'
=> false
```

**include**

Includes modules, nothing to do with files.

```ruby
class Person
  include ContactInfo
end
```

Enumerables as Mixins.

```ruby
class Animal
 include Enumerable
 
 attr_accessor :animals
 
 def initialize
  @animals = []
 end
 
 def each
  @animals.each { |animal| yield animal }
 end
end
```

```ruby
irb(main):001:0> require './animal.rb'
=> true
irb(main):002:0> animal = Animal.new
=> #<Animal:0x007ffe9806c888 @animals=[]>
irb(main):003:0> animal.animals = ['cat', 'dog', 'fish']
=> ["cat", "dog", "fish"]
irb(main):004:0> animal.select { |a| a.length > 3 }
=> ["fish"]
```

## Operators

### Comparison Operators

```
==    a == b      Equal
!=    a != b      Not Equal
<     a < b       Less than
>     a > b       Greater than
<=    a <= b      Less than equal
>=    a >= b      Greater than equal
<=>   a <=>       Spaceship operator
```

```ruby
irb(main):001:0> 1 <=> 2     # Spaceship operator is used for sorting based on value comparison.
=> -1
irb(main):002:0> 2 <=> 2
=> 0
irb(main):003:0> 2 <=> 1
=> 1
```

### Logical Operators

```
and     x and y     True is both x and y
&&      x && y      True is both x and y. Higher precedence.
or      x or y      True if x or y
||      x || y      True if x or y. Higher precedence.
not     not x       Invert state
!       !x          Invert state. Higher precedence.
```

### Arithmetic Operator

```
+		Addition
-		Subtraction
*		Multiplication
/		Division
%		(Remainder) Modulo
**		Exponent
-		Unary negative
+		Unary positive
```

### Bitwise Operator

```
&		AND
|		OR
^		XOR
<<		Shift left
>>		Shift right
```

## File IO

`__FILE__` refers to the file in which the handle is called.

```ruby
>> __FILE__
=> "(irb)"
>>  File.expand_path(__FILE__)
=> "/Users/gsree/(irb)"
>>  File.dirname(__FILE__)
=> "."
>>  File.basename(__FILE__)
=> "(irb)"
>> File.size('sample.txt')     # size in bytes.
=> 1722
>> File.extname('sample.txt')
=> ".txt" 
>> File.atime('sample.txt')       # Last access (read or write) time.
=> 2018-04-15 09:48:39 +1000
>> File.mtime('sample.txt')       # Last modified (write) time.
=> 2018-04-09 20:56:22 +1000
>> File.ctime('sample.txt')       # Last status change time.
=> 2018-04-09 20:56:22 +1000
```
File writing.

```ruby
>> fh = File.new('new_file.txt', 'w')     # File.new initializes a file handle and creates if the file does not exist.
=> #<File:new_file.txt>
>> fh.puts 'Hello World'
=> nil
>> fh.print "Hello World\n"
=> nil
>> fh.write "Hello World\n"
=> 12
>> fh << "Hello World\n"
=> #<File:new_file.txt>
>> fh.close                               # need to close the file handle explicitly. Write happen when the file is closed
=> nil
```

```ruby
>>  fh = File.new('new_file.txt', 'w')
=> #<File:new_file.txt>
>> fh.pos = 20
=> 20
>> fh.write('hello')              # Jumping to a nil position and writing will fill nill char to the start of the position.
=> 5
>> fh.close
=> nil
>>  fh = File.new('new_file.txt', 'r')
=> #<File:new_file.txt>
>> fh.gets
=> "\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000\u0000hello"
>> fh.gets
=> nil
>> fh.close
=> nil
>> 
```

Reading file.

```ruby
>> fh = File.new('new_file.txt', 'r')
=> #<File:new_file.txt>
>> fh.gets
=> "Hello World\n"
>> fh.gets.chomp
=> "Hello World"
>> fh.read(12)
=> "Hello World\n"
>> fh.gets
=> "Hello World\n"
>> fh.gets
=> nil
>> fh.rewind                # rewind sends the pointer position to 0 and also resets lineno.
=> 0
>> fh.pos
=> 0
>> fh.read(5)
=> "Hello"
>> fh.pos
=> 5
>> fh.read(7)
=> " World\n"
>> fh.eof?                    # eof? boolean operation to check end of file.
=> false
>> fh.pos = 15                # pos can set the position to beyond the end of file.
=> 15
>> fh.read(5)
=> "lo Wo"
>> fh.pos += 5
=> 20
>> fh.lineno
=> 0
>> fh.gets
=> "d\n"
>> fh.lineno                     # lineno is used as a counter for gets. It is not the actual lineno.
=> 1
>> fh.stat
=> #<File::Stat dev=0x1000004, ino=8604400607, mode=0100644, nlink=1, uid=502, gid=20, rdev=0x0, size=1722, blksize=4194304, blocks=8, atime=2018-04-15 09:48:39 +1000, mtime=2018-04-09 20:56:22 +1000, ctime=2018-04-09 20:56:22 +1000, birthtime=2018-04-09 20:56:22 +1000>
>> fh.stat.readable?
=> true
>> fh.stat.size
=> 1722
>> fh.close
=> nil
>> 
```

File access modes.

```
r   - Read from start. file must exist.
w   - Truncate/write from start.
a   - Append/Write from end.
```

```ruby
File.open('new_file.txt', 'r') do |file|            # second argument is mode, r, r+, w, w+, a, a+
    ....                                            # doesn't need and explicit close.
end
```

File rename and delete.

```ruby
>> File.rename('new_file.txt', 'sample_file.txt')
=> 0
>> File.delete('sample_file.txt')
=> 1
```
File booleans.

```ruby
>> File.exist?('sample.txt')
=> true
>> File.file?('sample.txt')
=> true
>> File.directory?('sample.txt')
=> false
>> File.readable?('sample.txt')
=> true
>> File.writable?('sample.txt')
=> true
>> File.executable?('sample.txt')
=> false
```

Workind with directories.

```ruby
>> Dir.pwd
=> "/tmp/ruby/"
>> Dir.chdir('..')
=> 0
>> Dir.entries('.')
=> [".", "..", "docker", ".DS_Store", "ruby"]
>> Dir.mkdir('Ruby')
=> 0
>> Dir.delete('Ruby')
=> 0
```

## Built-in Methods

### Numeric Methods

```ruby
>> 1.to_s       # to_s, converts to string.
=> "1"
>> "1".to_i     # to_i, converts to integer.
=> 1
>> 1.to_f       # to_f, converts to float.
=> 1.0
>> 1.to_c       # to_c, converts to complex number.
=> (1+0i)
>> -1.abs       # abs, coverts to absolute value.
=> 1
>> 1.next       # next, gives the next value.
=> 2
>> 1.55.round   #  round, rounds to the nearest value.
=> 2
>> 1.22.ceil    # ceil, rounds to upper value.
=> 2
>> 1.55.floor   # floor, rounds to lower value.
=> 1
```

### String Methods

```ruby
>> 'Hello'.reverse    # reverse, reverses the chars in a string.
=> "olleH"
>> "abc".capitalize   # capitalize, coverts first char to capital.
=> "Abc"
>> "abc".upcase       # upcase, converts all chars to capital.
=> "ABC"
>> "ABC".downcase     # downcase, converts all chars to  lower case.
=> "abc"
>> "a".next
=> "b"
>> 'Hello'.length     # length, gives length of the string.
=> 5
>> 'Hello'.reverse.upcase   # daisy chaining is possible with methods.
=> "OLLEH"
```

### Container Methods

**Array**

```ruby
>> array = [ 2, 5, 3, 1, 4 ]
=> [2, 5, 3, 1, 4]
>> array.join                     # join, joins the array.
=> "25314"
>> array.join(',')
=> "2,5,3,1,4"
>> array.length                   # length, gives the number of elements in an array.
=> 5
>> array.reverse                  # reverse, reverses array.
=> [5, 4, 3, 2, 1]
>> array.sort                     # sort, sorts the elements.
=> [1, 2, 3, 4, 5]
>> array.sort!                    # '!' forces the operation to save the result.
=> [1, 2, 3, 4, 5]
>> array.pop                      # pop, takes the last element and return.
=> 5
>> array.shift                    # shift, takes the first element and return.
=> 1
>> array.push(6)                  # push, adds a new element at the end or array.
=> [2, 3, 4, 6]
>> array.unshift(0)               # unshift adds a new element at the start of array.
=> [0, 2, 3, 4, 6]
>> array.inspect                  # inspect returns the array in a nice format (string).
=> "[0, 2, 3, 4, 6]"
>> puts array
0
2
3
4
6
=> nil
>> puts array.inspect
[0, 2, 3, 4, 6]
=> nil
>> "a,b,c,d,e".split(',')        # split, splits on the character and returns an array.
=> ["a", "b", "c", "d", "e"]
>> [1, 1, 2, 4, 3, 2, 5].uniq    # uniq, returns the array with uniq elements.
=> [1, 2, 4, 3, 5]
>> [1, 2, 4, 3, 5].delete(1)     # delete, deletes the value from and return.
=> 1
>> [1, 2, 4, 3, 5].delete_at(1)  # delete_at, deletes value at index and return the element.
=> 2
>> [1, 2, 3] + [ 'a', 'b' ]
=> [1, 2, 3, "a", "b"]
>> [1, 2, 3] - [2]               # same as delete.
=> [1, 3]
>> array.clear                   # clear, clears the array.
=> []
>> arr_a = [ 'x', 'xxxxx', 'xxx', 'xxxx', 'xx' ]
=> ["x", "xxxxx", "xxx", "xxxx", "xx"]
>> arr_a.sort
=> ["x", "xx", "xxx", "xxxx", "xxxxx"]
>> arr_a.sort {|v1,v2| v1 <=> v2}          # actual sort operation.
=> ["x", "xx", "xxx", "xxxx", "xxxxx"]
>> arr_a.sort.reverse
=> ["xxxxx", "xxxx", "xxx", "xx", "x"]
>> arr_a.sort {|v1,v2| v2 <=> v1}
=> ["xxxxx", "xxxx", "xxx", "xx", "x"]
>> arr_a.sort {|v1,v2| v2.length <=> v1.length}
=> ["xxxxx", "xxxx", "xxx", "xx", "x"]
>> arr_a.sort_by {|v| v.length}
=> ["x", "xx", "xxx", "xxxx", "xxxxx"]
>> array = [1, 2, 3, 4, 5]
=> [1, 2, 3, 4, 5]
>> array.collect
>> array.collect {|i| i * 3 }       # collect/map works on array, hash, range and return array with same number of elements.
=> [3, 6, 9, 12, 15]
>> array.map {|i| i * i }
=> [1, 4, 9, 16, 25]
>> [ 'a', 'b', 'c' ].map { |i| i.capitalize if i == 'c' }   
=> [nil, nil, "C"]
```

**Hash**

```ruby
>> hash = { "a" => 1, "b" => 2 }
=> {"a"=>1, "b"=>2}
>> hash.length
=> 2
>> hash.size                      # size and length gives number of elements.
=> 2
>> hash.to_a                      # to_a converts to an array.
=> [["a", 1], ["b", 2]]
>> hash.keys                      # keys, will give keys in a hash in the form of array.
=> ["a", "b"]
>> hash.values                    # values, will give values in a hash.
=> [1, 2]
>> hash.clear
=> {}
>> a = {'a' => 1, 'b' => 2 } 
=> {"a"=>1, "b"=>2}
>> b = {'b' => 3, 'c' => 4}
=> {"c"=>3, "d"=>4}
>> a.merge(b)                     # merge, merges two hashes and operate only on hashes.
=> {"a"=>1, "b"=>3, "c"=>4}
>> b.merge(a)
=> {"b"=>2, "c"=>4, "a"=>1}
>> a.merge(b) { |key,old,new| old }
=> {"a"=>1, "b"=>2, "c"=>4}
>> a.merge(b) { |key,old,new| old < new ? old : new}
=> {"a"=>1, "b"=>2, "c"=>4}
>> {'a' => 1, 'b' => 2}.map {|k,v| k }     # collect/map works on array, hash, range and return array with same number of elements.
=> ["a", "b"]
>> {'a' => 1, 'b' => 2}.map {|k,v| v }
=> [1, 2
>> {'a' => 1, 'b' => 2}.map {|k,v| "#{k} = #{v}" }
=> ["a = 1", "b = 2"]]
>> hash = { "c" => 3, "a" => 1, "b" => 2 }
=> {"c"=>3, "a"=>1, "b"=>2}
>> hash.sort                         # sort on hash converts it to array.
=> [["a", 1], ["b", 2], ["c", 3]]
>> hash.sort {|item1,item2| item2[0] <=> item1[0]}   # reverse sort.
=> [["c", 3], ["b", 2], ["a", 1]]
```

**Iterator**

```ruby
>> (1..10).begin                # begin gives the first value.
=> 1
>> (1..10).end                  # end gives the last value.
=> 10
>> (1..10).first
=> 1
>> (1..10).last
=> 10
>> a = (1..10)
=> 1..10
>> b = [*a]                          # * is splat operator. expands the range.
=> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>> (1..10).find {|i| i % 3 == 0}     # find/detect finds first value based on condition. Returns a single value or nil.
=> 3
>> (1..10).detect {|i| i % 3 == 0}
=> 3
>> (1..10).find {|i| i % 11 == 0}
=> nil
>> (1..10).find_all {|i| i % 3 == 0}   # find_all/select finds all values based on condition. Returns array.
=> [3, 6, 9]
>> (1..10).select {|i| i % 3 == 0}
=> [3, 6, 9]
>> [*1..10].delete_if {|i| i % 3 == 0}
=> [1, 2, 4, 5, 7, 8, 10]
>> (1..5).map {|i| i * i}         # collect/map works on array, hash, range and return array with same number of elements.
=> [1, 4, 9, 16, 25]
>> (1..10).inject {|memo,n| memo + n }   # memo is an accumulator, it collects the result. memo is initialized with 1.
=> 55
>> (1..10).inject(100) {|memo,n| memo + n }  # in this memo is initialized with 100.
=> 155
```

### Boolean Methods

```ruby
>> x = 1
=> 1
>> z = nil
=> nil
>> x.nil?
=> false
>> z.nil?
=> true
>> 2.between?(1,5)
=> true
>> [1, 2, 3].empty?
=> false
>> [].empty?
=> true
>> {}.empty?
=> true
>> [1, 2, 3].include?(2)
=> true
>> { 'a' => 1, 'b' => 2 }.has_key?('b')
=> true
>> { 'a' => 1, 'b' => 2 }.has_value?('4')
=> false
>> ('a'..'g').include?('f')
=> true
>> (1..10).any? {|i| i % 3 == 0}          # any value which satisfies the condition.
=> true
>> (1..10).all? {|i| i % 3 == 0}          # does all satisfies the condition.
=> false
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

