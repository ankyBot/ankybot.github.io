---
layout: post
title: A Practical Guide to Algorithms with JavaScript
published: true
---

In this post we will discuss about javascript algorithm 


# [A Practical Guide to Algorithms with JavaScript](https://slides.com/bgando/intro-to-algorithms)



## **Space** and Time complexity

### **Time** Complexity

How many primitive ***operations*** are executed?

### **Space** Complexity

How much ***memory*** is used?




### Complexity in general

| Big-O, name       | # of Operations | Algorithm                        |
| ----------------- | --------------- | -------------------------------- |
| O(n^2), quadratic | n^2             | compare all numbers              |
| O(n), linear      | 2n              | Find min and max numbers         |
| O(1), constant    | 2               | Sorted list, find first and last |



###  Complexity of Common Operations

| Complexity | Operation                                      |
| ---------- | ---------------------------------------------- |
| O(1)       | Running a statement                            |
| O(1)       | Value look-up on an array, object, variable    |
| O(logn)    | Loop that cuts problem in half every iteration |
| O(n)       | Looping through the values of an array         |
| O(n^2)     | Double nested loops                            |
| O(n^3)     | Triple nested loops                            |









##  Optimization with Caching

### Unique sort

```js
//Transforming the simple sorting algorithm into a unique sort. 
// It's not returning any duplicate values in the sorted array.

//input: [1,5,2,1] => output: [1,2,5]
//input: [4,2,2,3,2,2,2] => output: [2,3,4]

const uniqSort = function(arr) {
    const breadcrumbs = {};
    let myResult = [];

    for(let i = 0; i < arr.length; i++) {

      if(!breadcrumbs[arr[i]]) {
        myResult.push(arr[i]);
        breadcrumbs[arr[i]] = true;
      }
    }
    return myResult.sort((a, b) => a - b);
};

uniqSort([4,2,2,3,2,2,2]); // => [2,3,4]
```



### Memoization

In computing, **memoization** or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again.



### Basic Memoization Soluation

```js
// simple multiplication fn Memoization fn
// A function, times10, that takes an argument, n, and multiples n times 10

const times10 = (n) => {
  let myVal = 0;
  for(let i = 1; i <= n; i++) {
    myVal += 10;
  }
  return myVal;
};

console.log('~~~~~~~~~~~~~~TASK 1~~~~~~~~~~~~~~');
console.log('times10 returns:', times10(9));

// Here we are using an object to cache the results of our times10 function. 
 
const cache = {};

const memoTimes10 = (n) => {
  if(n in cache) {
    return cache[n];
  } else {
    let myVal = times10(n);
    cache[n] = myVal;
    return myVal;
  }
}

console.log('~~~~~~~~~~~~~~TASK 2~~~~~~~~~~~~~~');
console.log('Task 2 calculated value:', memoTimes10(9));	// calculated
console.log('Task 2 cached value:', memoTimes10(9));	// cached
```



### Memoization with closure

```js
const times10 = (n) => (n * 10);

// Cleaning up our global scope by moving our cache inside our function.

const memoizedClosureTimes10 = () => {
  let cache = {};
  return (n) => {
    if(n in cache) {
      return cache[n];
    } else {
      let result = times10(n);
      cache[n] = result;
      return result;
    }
  };
};

const memoClosureTimes10 = memoizedClosureTimes10();
console.log('~~~~~~~~~~~~~~TASK 3~~~~~~~~~~~~~~');
try {
  console.log('Task 3 calculated value:', memoClosureTimes10(9));	// calculated
  console.log('Task 3 cached value:', memoClosureTimes10(9));	// cached
} catch(e) {
  console.error('Task 3:', e);
}
```



### Generic Memoization function

```js
const times10 = (n) => (n * 10);

// Making our memo function generic and accept the times10 function as a callback rather than defining the n * 10 logic inside the if/else or pulling it in from the global scope.

const memoize = (cb) => {
  let cache = {};
  return (n) => {
    if(n in cache) {
      return cache[n];
    } else{
      let result = cb(n);
      cache[n] = result;
      return result;
    }
  };
};

// returned function from memoizedAdd
const memoizedTimes10 = memoize(times10);
console.log('~~~~~~~~~~~~~~TASK 4~~~~~~~~~~~~~~');
try {
  console.log('Task 4 calculated value:', memoizedTimes10(9));	// calculated
  console.log('Task 4 cached value:', memoizedTimes10(9));	// cached
} catch(e) {
  console.error('Task 4:', e)
}
```



## Recursion

Recursion is simply when a function calls itself; however it doesn't stop there.

### Call stack





### Looping with recursion 

```js
const loopNTimes = (n) => {

  console.log('n ===', n);

  if (n <= 1) {
      return 'complete';
  }
  return loopNTimes(n-1);
};

loopNTimes(3);
```



### Factorial with a loop vs recursion

```js
//Factorial using loop
function computeFactorial(num) {
  var result = 1;

  for(var i = 2; i <= num; i++) {
    result *= i;
  }

  return result;
}

computeFactorial(5);

//Factorial using recursion
function factorial(val) {
   if(val < 1) {
       return 1;
   } else {
       return val * factorial(val - 1);
   }
}

factorial(5);
```



#### **Common pattern for recursion**

### wrapper function

In programming languages such as JavaScript, a wrapper is a function that is intended to call one or more other functions, sometimes purely for convenience, and sometimes adapting them to do a slightly different task in the process.



### Accumulators



### Recursive factorial and memoize solution

```js

let memoize = (val) => {
  let cache = {};
  
  return (n) => {
    if(n in cache) {
      console.log("it was cached")
      return cache[n];
    } else {
      let result = val(n);
      cache[n] = result;
      return result;
    }
  };
};

function factorial(x) {
  if(x === 0) {
    return 1;
  } else {
    return x * factorial(x -1)
  }
}

let memoFactorial = memoize(factorial);

console.log(memoFactorial(5));
```





## Divide and Conquer

A **divide and conquer algorithm** is a strategy of solving a large problem by

1. breaking the problem into smaller sub-problems
2. solving the sub-problems, and
3. combining them to get the desired output.



### linear search

```js
function linearSearch(list, item) {
let result = -1;

  for(let i = 0; i < list.length; i++) {
    if(list[i] === item) {
      result = i;
    }
  }
return result;
}

console.log(linearSearch([2,6,7,90,103, 100, 90], 90));
```



### Binary search

```js
function binarySearch(list, item) {
  let min = 0;
  let max = list.length - 1;
  let guess;
  while(min <= max) {
    guess = Math.floor((min + max) / 2)
    if(list[guess] === item) {
      return guess;
    } else{
      if(list[guess] < item) {
        min = guess + 1;
      } else {
        max = guess - 1;
      }
    }
  }
return -1;
}

binarySearch([2,6,7,8,90,103], 90);
```





## Sorting
## 1. *Naive Sorts*


### Bubble sort


```js
function swap(array, i, j) {
  let temp = array[i];
  array[i] = array[j];
  array[j] = temp;
}

function bubbleSort(array) {
  for(let i = 0; i < array.length; i++) {
    for(j = 1; j < array.length; j++) {
      if(array[j - 1] > array[j]) {
        swap(array, j-1, j)
      }
    }
  }
  return array;
}

let myArr = [9, 1, 4, 8, 7,11, 13, 6, 2];
console.log(bubbleSort(myArr));
```



## 2. *Divide & Conquer Sorts*

###  Merge sort

```js
function mergeSort (arr) {
  if (arr.length === 1) {
    // return once we hit an array with a single item
    return arr
  }

  const middle = Math.floor(arr.length / 2) // get the middle item of the array rounded down
  const left = arr.slice(0, middle) // items on the left side
  const right = arr.slice(middle) // items on the right side
  const sortedLeft = mergeSort(left);
  const sortedRight = mergeSort(right);
  return merge(sortedLeft, sortedRight);
}

// compare the arrays item by item and return the concatenated result
function merge (left, right) {
  let result = []
  let indexLeft = 0
  let indexRight = 0

  while (indexLeft < left.length && indexRight < right.length) {
    if (left[indexLeft] < right[indexRight]) {
      result.push(left[indexLeft])
      indexLeft++
    } else {
      result.push(right[indexRight])
      indexRight++
    }
  }

  return result.concat(left.slice(indexLeft)).concat(right.slice(indexRight))
}

const list = [2, 5, 1, 3, 7, 2, 3, 8, 6, 3]
console.log(mergeSort(list)) // [ 1, 2, 2, 3, 3, 3, 5, 6, 7, 8 ]

```
