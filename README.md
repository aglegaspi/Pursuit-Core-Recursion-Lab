# Recursion Exercises

- ### Sum of all from 1 to n √

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```swift
//input: 6
//output: 21
//21 = 6 + 5 + 4 + 3 + 2 + 1

func recursiveSum(n: Int) -> Int {
    
    // BASE CASE
    if n == 0 { return 0 }
    
    // RECURSIVE CASE
    return n + recursiveSum(n: n - 1)
    
}
recursiveSum(n: 6)

```


- ### Multiply array √

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```swift
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50

func multArr(_ arrOfInts: [Int]) -> Int {
    
    // BASE CASE
    if arrOfInts.count == 1 {
        return arrOfInts[0]
    }
    
    // RECURSIVE CASE
    return arrOfInts[0] * multArr(Array(arrOfInts[1...]))
}
```

- ### Concatenate array √

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```swift
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'


func concatArr(_ strings: [String]) -> String {
    
    var output = ""
    
    // BASE CASE
    if strings.count == 1 {
        return strings[0]
    }
    
    // RECURSIVE CASE
    for i in 0..<strings.count {
        output += "\(concatArr([strings[i]])) "
    }
    return output
    
}


concatArr(["is", "it", "tomorrow"]); // returns 'is it tomorrow'
concatArr(["or", "just", "the", "end", "of", "time"]); //returns 'or just the end of time'
```

- ### Sum evens √

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```swift
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24

func sumEvens(_ nums: [Int]) -> Int {
    
    // BASE CASE
    if nums.count == 1 {
        return nums[0]
    }
    
    // RECURSIVE CASE
    let evens = nums.filter({ $0 % 2 == 0})
    return nums[0] + sumEvens(Array(evens[1...]))
}

```

- ### Recursive range  √

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```swift
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]

func range(_ num1: Int,_ num2: Int) -> [Int] {
    print([num1])
    // BASE CASE
    if num1 == num2 {
        return [num1]
    }
    
    // RECURSIVE CALL
    
    return [num1] + range(num1 + 1, num2)
    
}
```


- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```swift
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```swift
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)
