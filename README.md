# Funk-tional Programming

why functional ?

 …cause it's **funkier** than bruno mars with a vocoder. :)

it's clearly implied that that we'd be programming with functions, but using  that as the definition is pretty weak, i mean, we write functions everywhere right ?.

**Functional Programming** - the actual spelling if you actually wondering..

is a *paradigm*, that treats computation as the evaluation of
mathematical functions and avoids changing-state and mutable data. 

## I Still Don't Get It :(

So, i'm going to assume that you are one geeky six year old who just so happens to be interested in what functional programming is and not the latest justice league movie, which by the way, was pretty **EPIC**. 

so in one line, think of it as a way of writing your code following  a set of rules and concepts .

hold up, dont you kind of follow a set of rules while coding in other paradigms, yes. yes you do.

But, the rules to follow to functional programming are pretty peculiar.

If you've been writing javascript for a while, chances are you already implemented / written code following the rules that define functional programming.

ever used any of these : 

`array.sort(function(){}),`

 `array.find(function(){}),`

 `array.reduce(function(){}),` 

`array.map(function(){}).` ?

if your answer's yes, then yup..you've been funky, my friend. :)

if your answer's no, don't worry..i am still pretty sure you have, pretty much everybody has used a callback.

implementing a callback falls under the concept of higher order functions. we'll get to that in a bit.

## So What are These Rules

### . Pure Functions

For a function to be a pure function, it must satisfy someproperties 

-              Referential transparency that is the functionalways gives the same return value for the same argument, so it cannot dependon any mutable state

-              And it must be side  effect free

So we can say a pure function is one that returns an outputthat corresponds to the type of input it has been given and has no sideeffects.

In functional programming, the use of pure functions areencouraged.

An example of a pure function

`function add (a, b) { `

​                  `returna + b;`

`}`

An example of an impure function

`function canSmoke(age){`

​                  `returnage >= ageRange;`

`}`



### . Functors



### . Shared state

### . Mutation/Immutability



### . Side effects

Side-effects are the complexityiceberg. You look at the function signature, and the name, and think you’ve gota sense of what you’re looking at. But hidden beneath the surface of thefunction signature could be absolutely anything.

We accept that some side-effects areinevitable - most programs are run for what they *do* rather thanwhat they return, but within our program we will exercise tight control. Wewill eliminate side-effects (and side-causes) wherever we can, and tightlycontrol them whenever we can’t.

**Absenceof side-effects**,meaning that functions should rely solely on their arguments as input and theyshould not affect their environment in any way, meaning you should not use oralter anything outside the function itself. 

This, however, has some important implications, such as thefact that a function will always return the same output provided the same inputand the fact that, if the result of a functional call is not used, it can beremoved without causing any other changes in the code.

Example:

`Function multiply (a,b) {`

​            `Console.log (“Arguments:  ” , a, b);`

​            `Return a* b;`

`}`

### . Higher Order Functions

Higher-order function is a function that accepts (what istypically called) a callback function. It’s a function that can take a functionas an argument or return a function as a result, or both.

Functions are values, meaning you can pass them around, muchas you can do with variables. It is often used to create utility which can acton a wide verity of data. 

Anexample of a higher-order function is the differential operator which returnsthe derivative of a function.





### . Referential transparency

Referential transparency, referred to a function, indicates that you can determine theresult of applying that function only by looking at the values of its arguments. Referential transparency" is a verysimple and clear idea. The term "referent" is used in analyticalphilosophy to talk about *the thing that an expressionrefers to*. It is roughly the same as what we mean by"meaning" or "denotation" in programming language semantics.

Referential transparency, a term commonly used infunctional programming, means that given a function and an input value, youwill always receive the same output. That is to say there is no external stateused in the function.

Here is an example of a referential transparent function:

```
int plusOne(int x)
```

```
{
```

```
  return x+1;
```

```
}
```

With a referential transparent function, given an inputand a function, you could replace it with a value instead of calling thefunction. So instead of calling plusOne with a paremter of 5, we could justreplace that with 6.

Another good example is mathematics in general. Inmathematics given a function and an input value, it will always map to the sameoutput value. f(x) = x + 1. Therefore functions in mathematics are referentiallytransparent.

This concept is important to researchers because it meansthat when you have a referentially transparent function, it lends itself toeasy automatic parallelization and caching..--

In contrast there is the concept of referential opaqueness.This means the opposite. Calling the function may not always produce the sameoutput.

```
//global G
```

```
int G = 10;
```

```
 
```

```
int plusG(int x)
```

```
{//G can be modified externally returning different values.
```

```
  return x + G;
```

```
}
```

Another example, is a member function in an objectoriented programming language. Member functions commonly operate on its membervariables and therefore would be referential opaque. Member functions thoughcan of course be referentially transparent.

Yet another example is a function that reads from a textfile and prints the output. This external text file could change at any time sothe function would be referentially opaque.

Arithmetic operations are referentiallytransparent: 5*5 can be replaced by 25, for instance. In fact, all functions in the mathematical senseare referentially transparent: sin(x) is transparent, since it will always give the same resultfor each particular x.

Assignments are not transparent. For instance,the [C](https://en.wikipedia.org/wiki/C_(programming_language)) expression x = x + 1 changes the value assigned to the variable x. Assuming x initially hasvalue 10, two consecutive evaluations of theexpression yield, respectively, 11 and 12. Clearly,replacing x = x + 1 with either 11 or 12 gives a programwith different meaning, and so the expression is not referentially transparent.However, calling a function such as int plusone(int x) {return x+1;} *is* transparent, as it willnot implicitly change the input x and thus has no such [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science)).

today() is not transparent, as if you evaluate it and replace itby its value (say, "Jan 1, 2001"), you don't get the same result asyou will if you run it tomorrow. This is because it depends on a state (thedate).

In languages with no side-effects, like [Haskell](https://en.wikipedia.org/wiki/Haskell_(programming_language)), we can substitute equals for equals because f(x) = 

f(x) for every value of x. This does not hold for languageswith side-effects.

You can write referentially transparent functions in anyprogramming language, e.g. Python, Scheme, Pascal, C.

On the other hand, in most languages you can also writenon referentially transparent functions. For example, this Python function:

`counter = 0`

`def foo(x):`

  `globalcounter`

  `counter+= 1`

  `returnx + counter`

is not referentially transparent, in fact calling

`foo(x) + foo(x)`

and

`2 * foo(x)`

 

will produce differentvalues, for any argument `x`.The reason for this is that the function uses and modifies a global variable,therefore the result of each invocation depends on this changing state, and notonly on the function's argument.

Haskell, a purelyfunctional language, strictly separates *expression evaluation* inwhich *pure functions* are applied and which is alwaysreferentially transparent, from *action execution*(processingof special values), which is not referentially transparent, i.e. executing thesame action can have each time a different result.

So, for any Haskell function

```
f :: Int -> Int
```

and any integer `x`, it is always true that

```
2 * (f x) == (f x) + (f x)
```

An example of an action isthe result of the library function `getLine`:

```
getLine :: IO String
```

As a result of expressionevaluation, this function (actually a constant) first of all produces a purevalue of type `IO String`.Values of this type are values like any other: you can pass them around, putthem in data structures, compose them using special functions, and so on. Forexample you can make a list of actions like so:

```
[getLine, getLine] :: [IO String]
```

Actions are special in that you can tell the Haskellruntime to execute them by writing:

```
main = <some action>
```

In this case, when yourHaskell program is started, the runtime walks through the action bound to `main` and *executes* it, possibly producing side-effects.Therefore, action execution is not referentially transparent because executingthe same action two times can produce different results depending on what theruntime gets as input.

Thanks to Haskell's typesystem, an action can never be used in a context where another type isexpected, and vice versa. So, if you want to find the length of a string youcan use the `length`function:

```
length "Hello"
```

will return 5. But if you want to find the length of astring read from the terminal, you cannot write

```
length (getLine)
```

because you get a typeerror: `length` expectsan input of type list (and a String is, indeed, a list) but `getLine` is a value of type `IO String` (an action). In this way, thetype system ensures that an action value like `getLine` (whose execution is carried outoutside the core language and which may be non-referentially transparent)cannot be hidden inside a non-action value of type `Int`.

 

### . Function composition

Function composition is the process of combining two or morefunctions in order to produce a new function or perform some form ofcomputation.

For example, f(g(x)) is a combination of 2 functions, thatis the result of function g(x) is passed into function f. Example illustratedbelow

`const a = {`

​                  `value: 4;`

`}`

`const f = x = Object.assign({}, x, {value: x.value + 3});`

`const g= x = Object.assign({}, x, {value: x.value  * 5});`

`var b = f(g(x)).value);` 

The result b would be equal to 23.



### . Declarative vs Imperative

Declarative programming is a programming style thatabstracts the flow control process away using some functional utility likeArray.prototype.map and instead focuses on what the program does.

Imperative in the other sense would describe the flowprocess control that is, how to do things.

Imperative style of writing

`const tripleMap = number => {`

​                  `consttriple = [ ];`

​                  `for(let I = 0; I < number.length; I++) {`

​                                    `doubled.push(numbers[I]* 3;`

​                  `}`

​                  `returntriple;`

`};`

`console.log(tripleMap([3,4,5]));` 

  

Declarative style of writing the same thing

`const tripleMap = numbers => numbers.map(n => n * 3);`

`console.log(tripleMap([3,4,5]));` 

 

They would both produce the same result below:

[9, 12, 15]



### . Lambdas & Closures

**LAMBDAS:** They are anonymous functions i.efunction defined with no name, but is usually used as a value passed to anotherfunction in order pass a behavior as a value.

**CLOSURES: **They are functions whichcloses over the environment in which it was defined i.e it can access variablesnot in the parameter’s list.



**EXAMPLES**

**LAMBDA:**

```
var names = [

 { name: "JimHoskins", id: 1 },

 { name: "GuilHernandez", id: 2 },

 { name: "BenJakuben", id:3  }

];
```

 

```
names.sort(function (a, b) {

   if (a.name < b.name) {
     return  -1;
   }else if (a.name > b.name) {
     return 1;
   }else {
     return 0;
   }

});
```

Explanation: In this example we aresorting by the name property of the object. The lambda is a function that willreceive 2 parameters (the 2 items to compare for the sort) and it should returna numeric value (negative for a before b, 0 for equal, positive for a after b);

 

**CLOSURES:**

```
def lexical_scope_example(multiplier)

  [1, 2, 3].map do |number|

    new_number_to_double = number * multiplier

    new_number_to_double * 2

  end

end
```

Explanation: From the example above, the block we pass to the map  methodcan the multiplier access, number  and new_number_to_double variable.

### . Recursion

It is a programmingconcept. It is a technique foriterating over an operation by having a function call itself repeatedly untilit arrives at a result. Most loops can be rewritten in a recursive style, andin some functional languages this approach to looping is the default.

 

**Recursion** is best applied when you need to call the samefunction repeatedly with different parameters from within a loop. While it canbe used in many situations, it is most effective for solving problems involvingiterative branching, such as fractal math, sorting, or traversing the nodes ofcomplex or non-linear data structures

 

**Example:**

```
var factorial = function(number) {

 if (number <= 0) { 
   return 1;
 } else { 
   return (number * factorial(number - 1));
 }
};

console.log(factorial(6));
```

Explanation: For a factorial calculated this way,the terminal case comes when the number passed in is zero or negative. Writing code this way allows us to describe thewhole process in a stateless way with no side effects.

 



## REFERENCES:

1.        <https://softwareengineering.stackexchange.com/questions/254304/what-is-referential-transparency>

2.        https://en.wikipedia.org/wiki/Referential_transp