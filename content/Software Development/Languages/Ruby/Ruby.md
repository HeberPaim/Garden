## About #numbers 
````ruby
# Addition
1 + 1   #=> 2

# Subtraction
2 - 1   #=> 1

# Multiplication
2 * 2   #=> 4

# Division
10 / 5  #=> 2

# Exponent
2 ** 2  #=> 4
3 ** 4  #=> 81

# Modulus (find the remainder of division)
8 % 2   #=> 0  (8 / 2 = 4; no remainder)
10 % 4  #=> 2  (10 / 4 = 2 with a remainder of 2)
````



#### Integers and floats

###### Comportamento de operações matemáticas
````ruby

17 / 5    #=> 3, not 3.4

17 / 5.0  #=> 3.4

````

###### Para realizar a conversão, utilizar os métodos: 

````ruby
# To convert an integer to a float:
13.to_f   #=> 13.0

# To convert a float to an integer:
13.0.to_i #=> 13
13.9.to_i #=> 13

````

###### Métodos úteis 

````ruby

6.odd? #=> false
7.odd? #=> true

6.even? #=> true
7.even? #=> false

````

## About #strings

###### Concatenation

 ````ruby
 # With the plus operator:
"Welcome " + "to " + "Odin!"    #=> "Welcome to Odin!"

# With the shovel operator:
"Welcome " << "to " << "Odin!"  #=> "Welcome to Odin!"

# With the concat method:
"Welcome ".concat("to ").concat("Odin!")  #=> "Welcome to Odin!"

 ````

###### Substrings 

 ````ruby
"hello"[0]      #=> "h"

"hello"[0..1]   #=> "he"

"hello"[0, 4]   #=> "hell"

"hello"[-1]     #=> "o"
 ````



###### Escape Characters
 ````ruby
\\  #=> Need a backslash in your string?
\b  #=> Backspace
\r  #=> Carriage return, for those of you that love typewriters
\n  #=> Newline. You'll likely use this one the most.
\s  #=> Space
\t  #=> Tab
\"  #=> Double quotation mark
\'  #=> Single quotation mark
 ````
 
##### Interpolation
````ruby
name = "Odin"

puts "Hello, #{name}" #=> "Hello, Odin"
puts 'Hello, #{name}' #=> "Hello, #{name}"
 ````
 
#### Common String Methods

###### Capitalize
 ````ruby
"hello".capitalize #=> "Hello"
 ```` 

###### Include?
 ````ruby
"hello".include?("lo")  #=> true

"hello".include?("z")   #=> false
 ```` 

###### upcase
 ````ruby
"hello".upcase  #=> "HELLO"
 ```` 
 
###### downcase
 ````ruby
"hello".downcase  #=> "HELLO"
 ```` 
 
###### empty?

 ````ruby
"hello".empty?  #=> false

"".empty?       #=> true
 ````
 
###### length

 ````ruby
"hello".length  #=> 5
 ```` 

###### reverse
 ````ruby
"hello".reverse  #=> "olleh"
 ```` 
 
###### split
 ````ruby
"hello world".split  #=> ["hello", "world"]

"hello".split("")    #=> ["h", "e", "l", "l", "o"]
 ````

###### strip

 ````ruby
" hello, world   ".strip  #=> "hello, world"
 ````
 
##### Examples 
 ````ruby

"he77o".sub("7", "l")           #=> "hel7o"

"he77o".gsub("7", "l")          #=> "hello"

"hello".insert(-1, " dude")     #=> "hello dude"

"hello world".delete("l")       #=> "heo word"

"!".prepend("hello, ", "world") #=> "hello, world!"
 ````
 
#### Convertion to string

 ````ruby
5.to_s        #=> "5"

nil.to_s      #=> ""

:symbol.to_s  #=> "symbol"
 ````

## About #Symbols
### What are Symbols?
Symbols are an interesting twist on the idea of a string. The full explanation can be a bit long, but here’s the short version:

Strings can be changed, so every time a string is used, Ruby has to store it in memory even if an existing string with the same value already exists. Symbols, on the other hand, are stored in memory only once, making them faster in certain situations.

#### Create a Symbol 

To create a symbol, simply put a colon at the beginning of some text:

````ruby
:my_symbol
````

#### Symbols vs Strings

To get a better idea of how symbols are stored in memory, give this a whirl in irb or a REPL. The #object_id method returns an integer identifier for an object. (And remember: in Ruby, everything is an #object!)

````ruby
"string" == "string"  #=> true

"string".object_id == "string".object_id  #=> false

:symbol.object_id == :symbol.object_id    #=> true
````
## About Nil
In Ruby, nil represents “nothing”. Everything in Ruby has a return value. When a piece of code doesn’t have anything to return, it will return nil. 
Nil == null == undefined

