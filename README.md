Syntax for describing the signature of modules. 

Useful for concisely and precisely declaring what arguments are expected and value returned. Also useful for expressing properties about their behavior for reasoning about correctness.

Syntax
======

A variable named a of type number is written:

    a: number
    
The basic types follow the [TypeScript notation](http://www.typescriptlang.org/docs/handbook/basic-types.html).
         
A function named foo that takes 2 arguments, the first named a of type number and the second named b of type string is written:
 
    foo (a: number, b: string)

A function named foo that takes no argument and returns c of type number is written:

    foo () => c: number

Note that return values do not have names in JavaScript but for reasoning about the behaviour of a module it is easier to name all constituents of its signature.

A function parameter may be optional, in which case we prefix the parameter with '?':

    foo (a: number, ?b: string)

An object named foo with a property a of type number and another property b of type function is written:

    foo {
        a: number,
        b: b () => c: number
    }

Since the second name of the function is redundant, we omit it. Also to more closely follow the previous syntax for functions we also omit the ':':

    foo {
        a: number,
        b () => c: number
    }


    
Examples
========



Conventions
===========

When objects describe pull-streams, the methods are listed from top to bottom in the order in which the values pass through them.
