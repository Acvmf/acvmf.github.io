---
layout: essay
type: essay
title: FizzBuzz tutorial
date: 2016-09-01
labels:
  - Tutorials
  - Javascript
---

## Introduction
A recent WOD challenge involved the game "Fizzbuzz", in which a group of friends take turns counting numbers from 1 to 100. The trick is, when a number is divisible by 3, the person instead says "Fizz", and when it's divisible by 5, they say "Buzz". If it's both (divisible by 15), they say "Fizzbuzz".

Here are two ways of going about it: the easy-to-read way, and the concise way. I'll write the pseudocode first so that in case you're not familiar with JS syntax, this still makes sense.

### Pseudocode:
```
loop(1 to 100){
  if the number is divisible by 3 or 5 (or both), then
    if only 3, write Fizz
    if only 5, write Buzz	
    if both, write Fizzbuzz
  otherwise, write the number itself.
}

```

### Readable:
```

function Fizzbuzz(){
let output = "";
let count = 1;
while (count < 101){
  if(count % 3 === 0)output = "Fizz";
  if(count % 5 === 0)output = "Buzz";
  if(count % 15 === 0)output = "Fizzbuzz";
  if(count % 3 !== 0 && count % 5 !== 0)output = count;
  console.log(output);
  output = "";
  count++;
}
return(true);
}
```
This function has two pieces of information, output and count. Count is the number currently being processed, and output is what's going to be said. It begins at 1, and then counts up until the number reaches 101, at which point it exits. For each number, it checks whether it is a Fizz, in which case it adds the word "Fizz" to the output, then it does the same for Buzz and FizzBuzz. The Fizzbuzz line could be omitted in favor of simply adding the "Fizz" or "Buzz" to output rather than replacing whatever is in output with new data; however, this is a little more complicated.

If none of the above conditions are true, output is set to simply the number in count. The function then sends output to the console, resets output to nothing, and increments count.

### Concise:
```
for (var i = 1; i <= 100; i++) {
  var f = i % 3 == 0, b = i % 5 == 0;
  console.log(f ? b ? "FizzBuzz" : "Fizz" : b ? "Buzz" : i);
}

This version will make very little sense to someone unfamiliar with powerful expressions and Javascript. However, in essence, it does the exact same thing.

The first line is a for-loop: it begins with an integer variable set to 1 (var i = 1). It will check the value of this variable each time it begins the loop, and if it is not less than or equal to 100 (i <= 100), it will exit. Each time it ends a loop, it will increment the variable by one (i++).

The second line sets two new variables, f and b. f is made equal to the value "i % 3 == 0", a comparison. This means that f will be true or false. b is similarly equal to "i % 5 == 0".

The third line evaluates the truth values of f and b using a complex nested ternary statement. It can be broken down as such:

```

(f ? (b ? "FizzBuzz" : "Fizz") : (b ? "Buzz" : i))
```

The overall form of a ternary statement is "true/false ? if true do this : if false do this". Therefore, the statement as a whole takes the value of f first. Then, in either case, it evaluates b. Based on this combination of truths, it knows whether to print Fizz, Buzz, or FizzBuzz. If it goes into the "false" side of f, and then the "false" side of b, it ends up with a single i character. If you remember, i was the name of the variable in the for loop which counts what number it's on. Therefore, if it sees that both f and b are false, it will print only the number.

Since the command "console.log" includes a new line character (carriage return), there is no need to manually set one; merely return to the beginning of the for-loop and check whether you should run it again.

I hope you have enjoyed this code breakdown. I did it mostly as an exercise for myself, but perhaps it'll help someone else out there.