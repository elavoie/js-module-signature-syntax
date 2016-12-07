Syntax for describing the signature of modules. 

Useful for concisely and precisely declaring what arguments are expected and what kind of value is returned. Also useful for concisely expressing properties about their behavior for reasoning about correctness. It was designed to reason about the correctness of pull-stream modules.

Syntax
======

A variable named a of type number is written:

    a: number
    
The basic types follow the [TypeScript notation](http://www.typescriptlang.org/docs/handbook/basic-types.html).
         
A function named foo that takes 2 arguments, the first named a of type number and the second named b of type string, and returns c of type number is written:
 
    foo: (a: number, b: string) => c: number

Note that return values do not have names in JavaScript but for reasoning about the behaviour of a module it is easier to name all constituents of its signature.

A function named foo that takes no argument and returns undefined is written:

    foo: () => _
    
The return signature '=> _' may be omitted for conciseness when it is undefined:

    foo: ()

A function parameter may be optional, in which case we prefix the parameter with '?':

    foo: (a: number, ?b: string)

An object with a property a of type number and another property b of type function is written:

    {
        a: number,
        b: () => c: number
    }

Objects may also be named by prefixing them with their name, an empty object named 'foo' is therefore written:

    foo: {}

The same syntax applies when a named object is actually the child of another object:

    {
        foo: {
            a: number 
        }
    }

    
Examples
========



Conventions
===========

1. When objects describe [pull-streams](https://pull-stream.github.io), the methods are listed from top to bottom in the order in which the values pass through them.
