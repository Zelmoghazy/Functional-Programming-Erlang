# Learning Functional Programming Through Erlang Documentation
* Following the online book https://learnyousomeerlang.com/content

## Installation (Windows)
1. Download Erlang/OTP  https://www.erlang.org/downloads
2. add `C:\Program Files\Erlang OTP\bin` to `PATH` system variable
3. check with `erl --version`

## Shell Commands
1. `help().`: the (.) is required 
2. `q()`: quit
3. `ctrl+g`: abort

* In the Erlang shell, expressions have to be terminated with a period followed by whitespace (line break, a space etc.), otherwise they won't be executed.
* You can separate expressions with commas, but only the result of the last one will be shown (the others are still executed).

## Operators
1. `/` : Floating point division 
2. `div` : Integer division
3. `rem` : mod
4. `base#value` : express integers in other bases

* variables can't be variable in functional programming.

```erlang
X = 1.
X = X + 1. 
** exception error: no match of right hand side value 2
```
* you can assign a value to a variable exactly once;
* The `=` operator (not the variables) has the role of comparing values and raising an exception if they're different.
  *  If they're the same, it returns the value
* What this operator does when mixed with variables is that if the left-hand side term is a variable and it is unbound (has no value associated to it), Erlang will automatically bind the right-hand side value to the variable on the left-hand side.
  *  The comparison will consequently succeed and the variable will keep the value in memory.
* To clear a variable `f(Variable).`, clear all variables `f().` (Only work in shell)


* Variable names must begin with a capital letter.

### Atoms
* Atoms are literals, constants with their own name for value.
* single words starting with a lowercase letter is a way to write an atom

```erlang
atom.
'Atom'.
```
* An atom should be enclosed in single quotes (') if it does not begin with a lower-case letter or if it contains other characters than alphanumeric characters, underscore (_), or @.
* an atom with single quotes is exactly the same as a similar atom without them.
* An atom is therefore mainly useful to express or qualify data coupled with it. 

### Reserved atoms
* `after`
* `and`
* `andalso`
* `band`
* `begin`
* `bnot`
* `bor`
* `bsl`
* `bsr`
* `bxor`
* `case`
* `catch`
* `cond`
* `div`
* `end`
* `fun`
* `if`
* `let`
* `not`
* `of`
* `or`
* `orelse`
* `query`
* `receive`
* `rem`
* `try`
* `when`
* `xor`

## Boolean Algebra & Comparison Operators
```erlang
true and false.
false or true.
true xor false.
not false.
not (true and true).
```
* Equality and inequality
```erlang
5 =:= 5.
1 =:= 0.
1 =/= 0.
5 =:= 5.0. -> false
5 == 5.0. -> true
5 /= 5.0.
1 < 2.
1 < 1.
1 >= 1.
1 =< 1.
```
* `=:=` : equals
* `=/=` : not equal
* `==`  : equals (dont care whether fp or integer)
* `/=`  : not equal (dont care whether fp or integer)


## Concepts

* **referential transparency :** given a function and an input value, you will always receive the same output.
  *  That is to say there is no external state used in the function.

* **The actor model** a mathematical model of concurrent computation that treats an actor as the basic building block of concurrent computation.
  *  In response to a message it receives, an actor can:
     * make local decisions
     * create more actors
     * send more messages
     * determine how to respond to the next message received.
   * Actors may modify their own private state, but can only affect each other indirectly through messaging (removing the need for lock-based synchronization).

* Erlang is also a development environment as a whole.
  * The code is compiled to bytecode and runs inside a virtual machine; So Erlang, much like Java, can run anywhere.
  * The standard distribution includes (among others):
    * development tools (compiler, debugger, profiler, test framework)
    * The Open Telecom Platform (OTP) Framework
    * a web server
    * a parser generator
    * the mnesia database : a key-value storage system able to replicate itself on many servers, supporting nested transactions and letting you store any kind of Erlang data.