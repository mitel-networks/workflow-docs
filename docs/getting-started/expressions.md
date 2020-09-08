---
layout: default
title: Expressions
parent: Getting Started
nav_order: 7
---

# Workflow Expression Language

Workflow expression language is used anywhere there is an input, throughput assignment.

```javascript
membership == "gold" and (waitTime * factor > 4000 or status in ("pending", "error"))
```

## Values
```javascript
True, -34.7, "abcdef", ( 3, "dfg" )
```

There are 5 supported value types:

* Boolean
```javascript
True, False
```
* Number
```javascript
45, -90.3, NaN, Infinity
```
* String
```javascript
"abcd", "23cvb54R 3rt4+53yt"
```
* Object
```javascript
someObject
```
* Array
```javascript
(a, b, c)
someArray
```

## Variables
```javascript
variableName
variableA + variableB
anotherVariable != False
```

All variables present in the current expression scope are available for use:
* User Defined variables within scope
* Arguments of all activities within scope

Variables are accessible via their plain text name and will be displayed as autocomplete options

Variables will always be of one of the five Value types:
* Boolean, Number, String, Object, Array

## Arithmetic
```javascript
( x + 5 ) ^ ( y % 3 ) - sqrt( x )
```

All common arithmetic operators are supported:
* Addition, Subtraction, Multiplication, Division
```javascript
x + y
x - y
x * y
x / y
```
* Exponentiation
```javascript
x ^ y
```
* Modulus - Returns the remainder from integer division
```javascript
x % y
```

Several useful arithmetic functions are also available:
* Absolute Value
```javascript
abs( x: number ): number
```
* Natural Logarithm
```javascript
log( x: number ): number
```
* Square Root
```javascript
//Equivalent to x ^ ( 1 / 2 )
sqrt( x: number ): number
```
* Ceiling - Rounds upwards to nearest integer
```javascript
ceil( x: number ): number
```
* Floor - Rounds downwards to nearest integer
```javascript
floor( x: number ): number
```
* Minimum - Returns smallest number in given list
```javascript
min( a, b, c... ): number
```
* Maximum - Returns largest number in given list
```javascript
max( a, b, c... ): number
```
* Rounding - Round to nearest integer
```javascript
round( x: number ): number
```
* Random - Random floating point from 0.0 to 1.0
```javascript
random(): number
```

## Boolean Logic
```javascript
( x or y ) and not z
```

The following boolean operators are supported:
* AND - TRUE if both x AND y are TRUE - FALSE otherwise
```javascript
x and y
```
* OR - TRUE if x OR y OR both are TRUE - FALSE otherwise
```javascript
x or y
```
* NOT - TRUE if x is FALSE - FALSE otherwise
```javascript
not x //
```

* Ternary - If x is TRUE return y otherwise return z
```javascript
x ? y : z
```

## Equalities
```javascript
volume > 56
color != "green"
```

The following equality operators are supported: 
* Equal, Not Equal
```javascript
x == y
x != y
```
* Less than, Less than OR equal
```javascript
x < y
x <= y
```
* Greater than, Greater than OR equal
```javascript
x > y
x >= y
```

## Arrays
```javascript
( 2, 34, 2 )
( "a", "xyz", "23" )
( True, "abc", 5 )
( ( True, 34 ) , "abc", ( 3 ) )
```

Arrays are lists of values

* Creation
```javascript
//Method 1
( a, b, c, ... )
( True, "abc", 5 )
//Method 2
ArrayCreate( a, b, c ...): any[]
ArrayCreate( "color", 12, False )
```
* Membership
```javascript
x in (a, b, c) 
x not in (a, b, c)
```
* Element Access
```javascript
//Method 1
someArray.x
//Method 2
ArrayGetItem(array: Array<any>, index: number): any
ArrayGetItem(someArray, 4)
```
* Appending items
```javascript
ArrayConcat(array: Array<any>, ...values): any[] 
ArrayConcat(someArray, "red", 14)
```
* Length
```javascript
ArrayCount(array: Array<any>): number
```

## Objects
Generic Objects are supported and are essentially bags of Key Value pairs

* Creation
```javascript
ObjectCreate(keys: any[], values: any[])
ObjectCreate( ( "count", "color", "isReady" ), ( 23, "red", True) )
```
* Member Access
```javascript
x.y
y of x
```
* Check existence of object property
```javascript
ObjectHasProperty(obj: object, propertie: string)
ObjectHasProperty(someObject, "property1" ) )
```

## String Expressions
Several convenience functions are available for common String processing situations

* Length
```javascript
StringLen(str: string): number
```
* Conditional
```javascript
StringStartsWith(str: string, subStr: string): boolean
StringContains(str: string, subStr: string): boolean
StringEndsWith(str: string, subStr: string): boolean
```
* Building
```javascript
StringBuilder(...strings): string
```
* Trim
```javascript
StringTrim(str: string)
```
* To Lower Case
```javascript
StringToLowerCase(str: string)
```

* Regular Expressions
```javascript
x ~= y
x ~= "^(abc)$"
```

## Date and Time Expressions
```javascript
"Thu Jan 26 2017 11:00:00 UTC"
```

While there is no dedicated Date or Time type, several convenience functions are available for working with Date Time Strings:
* Current Date Time (UTC)
```javascript
DateUtcNow(): string 
```
* Manipulating Date Time Strings (UTC):
```javascript
//Adding time
DateUtcAddDay(date: string, daysToAdd: number): string
DateUtcAddHour(date: string, hoursToAdd: number): string
DateUtcAddMinutes(date: string, minutesToAdd: number): string
DateUtcAddSeconds(date: string, secondsToAdd: number): string
//Subtracting time
DateUtcSubDay(date: string, daysToSub: number): string
DateUtcSubHour(date: string, hoursToSub: number): string
DateUtcSubMinutes(date: string, minutesToSub: number): string
DateUtcSubSeconds(date: string, secondsToSub: number): string
```
