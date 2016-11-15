Add this to .tclshrc 
```
if {$tcl_interactive} {
    package require Tclx
    package require tclreadline
    ::tclreadline::Loop
}
```
# 12 Rules of Tcl

### 1. Commands 
A Tcl script is a string containing one or more commands.  
Commands follow the form **cmd arg1 arg2 ... argN**.    
Semicolons and newlines are command separators (unless quoted).  
```
puts "Hello, world!"
puts Hello          # quotes not needed   
puts 1
puts "Command 2!"; puts "Command 3!"
puts Hello, world   # crashes. puts with 3 args will write to file
```

### 2. Evaluation
Commands are evaluated in two steps.  
The Tcl interpreter breaks the command into words and performs substitutions  
The first word will be the command procedure (like a function/method).  
All remaining words are passed to the command procedure  

### 3. Words
Words are commands separated by whitespace (except newline)  
A word is a string of characters, and a command is a list of words  
```
puts "This is a puts command with two words"
puts {This is also a puts command with two words}
```

### 4. Double Quotes
If a word starts with a double quote, then the word is terminated by the next double quote.  
Semicolons, brackets, and whitespace characters are treated as characters within double quotes.  
Substitutions are still performed between the quotes.  
Double quotes are not retained as part of the word.  
```
puts "Hello

newlinesubstitution\n-----
worlds!
;;;;
"

# Hello
# 
# newlinesubstitution
# -----
# worlds!
# ;;;;
```

### 5. Argument Expansion
If a word starts with {\*} followed by a non-whitespace character,  
then the {\*} is removed and the rest of the word is parsed and substituted as any other word.  
After substitution, the word is parsed as a list.  
Its words are added to thecommand being substituted.  
In other words, command substitution breaks word barriers. (see rule 12) 
```
cmd a {*}{b [c]} d {*}{$e f "g h"}      # same as cmd a b {[c]} d {$e} f "g h"
```

### 6. Braces
If a word starts with a brace, then the word is terminated by the closing brace.  
No substitutions are performed on the characters between the braces, except for backslash-newline.  
Semicolons, newlines, brackets, and white space do not receive any special interpretation.  

### 7. Command Substitution
If a word contains an open bracket, Tcl performs command substitution.  
The characters inside the brackets are processed as a script.  
The result of the script is substituted in place of the word.  
```
set myVar [expr {5 + 6}]
puts $myVar           # 11

namespace import tcl::mathop::*
set myVar [+ 5 [expr {4 / 2}]]
puts $myVar           # 7
```

### 8. Variable Substitution
If a word begins with $, Tcl performs variable substitution.  
The $ and word is replaced by the value of the variable.  
```
set one 1
set two 2
set three 3
set myArray(four) 4

puts "My first variable is $one"                # 1
puts "My second variable is ${two}"             # 2
puts "My third variable is $[set three]"        # 3
puts "My array variable is $myArray(four)"      # 4

puts $one$two$three         # 123
puts $oneis1$two$three      # crashes
puts ${one}is1$two$three    # 1is123
```

### 9. Backslash Substitution
When a backslash appears inside a word, Tcl performs backslash substitution.  
In most cases, the following character is treated as a normal character.  
There are some sequences that are handled differently.  
```
puts "Control-C is here --->\003<---"
puts "New line goes here --->\n<---"
```

### 10. Comments
There are no block comments in Tcl.  
```
# single line comment

if {0} {
    This is a block 
    comment
}
```

### 11. Order of Substitution
Substitutions take place from left to right.  
Each substitution is evaluated completely before the next.  
```
set y [set x 0][incr x][incr x]       # y = 012
set y "[set x 0][incr x][incr x]"     # y = 012
set y ([set x 0][incr x][incr x])     # y = (012)
set y {[set x 0][incr x][incr x]}     # y = [set x 0][incr x][incr x]
```

### 12. Substitution and Word Boundaries
Substitutions usually do not affect the word boundaries of a command.  
```
set args [list one 2 3 4 five]
puts $args      # one argument instead of five
```









