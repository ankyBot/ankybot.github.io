---
layout: post
title: A Practical Guide to Algorithms with JavaScript
published: true
---
While HTML and CSS control the content and styling of a page, JavaScript is used to make it interactive. In the JavaScript Algorithm and Data Structures Certification, you'll learn the fundamentals of JavaScript including variables, arrays, objects, loops, and functions.

Once you have the fundamentals down, you'll apply that knowledge by creating algorithms to manipulate strings, factorialize numbers, and even calculate the orbit of the International Space Station.

Along the way, you'll also learn two important programing styles or paradigms: Object Oriented Programing (OOP), and Functional Programing (FP).



# Regex

### **Using the Test Method**

Regular expressions are used in programming languages to match parts of strings. You create patterns to help you do that matching.

If you want to find the word `the` in the string `The dog chased the cat`, you could use the following regular expression: `/the/`. Notice that quote marks are not required within the regular expression.

JavaScript has multiple ways to use regexes. One way to test a regex is using the `.test()` method. The `.test()` method takes the regex, applies it to a string (which is placed inside the parentheses), and returns `true` or `false` if your pattern finds something or not.

```js
let testStr = "freeCodeCamp";
let testRegex = /Code/;
testRegex.test(testStr);
```

The `test` method here returns `true`.

------

Apply the regex `myRegex` on the string `myString` using the `.test()` method.

```js
let myString = "Hello, World!";
let myRegex = /Hello/;
let result = myRegex.test(myString);
```



### **Match Literal Strings**

In the last challenge, you searched for the word `Hello` using the regular expression `/Hello/`. That regex searched for a literal match of the string `Hello`. Here's another example searching for a literal match of the string `Kevin`:

```js
let testStr = "Hello, my name is Kevin.";
let testRegex = /Kevin/;
testRegex.test(testStr);
```

This `test` call will return `true`.

Any other forms of `Kevin` will not match. For example, the regex `/Kevin/` will not match `kevin` or `KEVIN`.

```js
let wrongRegex = /kevin/;
wrongRegex.test(testStr);
```

This `test` call will return `false`.

A future challenge will show how to match those other forms as well.

------

Complete the regex `waldoRegex` to find `"Waldo"` in the string `waldoIsHiding` with a literal match.

```js
let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
let waldoRegex = /Waldo/; // Change this line
let result = waldoRegex.test(waldoIsHiding);
```



### **Match a Literal String with Different Possibilities**Passed

Using regexes like `/coding/`, you can look for the pattern `coding` in another string.

This is powerful to search single strings, but it's limited to only one pattern. You can search for multiple patterns using the `alternation` or `OR` operator: `|`.

This operator matches patterns either before or after it. For example, if you wanted to match the strings `yes` or `no`, the regex you want is `/yes|no/`.

You can also search for more than just two patterns. You can do this by adding more patterns with more `OR` operators separating them, like `/yes|no|maybe/`.

------

Complete the regex `petRegex` to match the pets `dog`, `cat`, `bird`, or `fish`.

```js
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/; // Change this line
let result = petRegex.test(petString);
```





### **Ignore Case While Matching**
Up until now, you've looked at regexes to do literal matches of strings. But sometimes, you might want to also match case differences.

Case (or sometimes letter case) is the difference between uppercase letters and lowercase letters. Examples of uppercase are `A`, `B`, and `C`. Examples of lowercase are `a`, `b`, and `c`.

You can match both cases using what is called a flag. There are other flags but here you'll focus on the flag that ignores case - the `i` flag. You can use it by appending it to the regex. An example of using this flag is `/ignorecase/i`. This regex can match the strings `ignorecase`, `igNoreCase`, and `IgnoreCase`.

------

Write a regex `fccRegex` to match `freeCodeCamp`, no matter its case. Your regex should not match any abbreviations or variations with spaces.

```js
let myString = "freeCodeCamp";
let fccRegex = /freecodecamp/i; // Change this line
let result = fccRegex.test(myString);
```



### **Extract Matches**

So far, you have only been checking if a pattern exists or not within a string. You can also extract the actual matches you found with the `.match()` method.

To use the `.match()` method, apply the method on a string and pass in the regex inside the parentheses.

Here's an example:

```js
"Hello, World!".match(/Hello/);
let ourStr = "Regular expressions";
let ourRegex = /expressions/;
ourStr.match(ourRegex);
```

Here the first `match` would return `["Hello"]` and the second would return `["expressions"]`.

Note that the `.match` syntax is the "opposite" of the `.test` method you have been using thus far:

```js
'string'.match(/regex/);
/regex/.test('string');
```

------

Apply the `.match()` method to extract the string `coding`.

```js
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/; // Change this line
let result = extractStr.match(codingRegex); // Change this line
```



### **Find More Than the First Match**

So far, you have only been able to extract or search a pattern once.

```js
let testStr = "Repeat, Repeat, Repeat";
let ourRegex = /Repeat/;
testStr.match(ourRegex);
```

Here `match` would return `["Repeat"]`.

To search or extract a pattern more than once, you can use the `g` flag.

```js
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex);
```

And here `match` returns the value `["Repeat", "Repeat", "Repeat"]`

------

Using the regex `starRegex`, find and extract both `Twinkle` words from the string `twinkleStar`.

**Note**
You can have multiple flags on your regex like `/search/gi`

```js
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /twinkle/gi; // Change this line
let result = twinkleStar.match(starRegex); // Change this line
```



### **Match Anything with Wildcard Period(`.`)**

Sometimes you won't (or don't need to) know the exact characters in your patterns. Thinking of all words that match, say, a misspelling would take a long time. Luckily, you can save time using the wildcard character: `.`

The wildcard character `.` will match any one character. The wildcard is also called `dot` and `period`. You can use the wildcard character just like any other character in the regex. For example, if you wanted to match `hug`, `huh`, `hut`, and `hum`, you can use the regex `/hu./` to match all four words.

```js
let humStr = "I'll hum a song";
let hugStr = "Bear hug";
let huRegex = /hu./;
huRegex.test(humStr);
huRegex.test(hugStr);
```

Both of these `test` calls would return `true`.

------

Complete the regex `unRegex` so that it matches the strings `run`, `sun`, `fun`, `pun`, `nun`, and `bun`. Your regex should use the wildcard character.

```js
let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // Change this line
let result = unRegex.test(exampleStr);
```



### **Match Single Character with Multiple Possibilities**

You learned how to match literal patterns (`/literal/`) and wildcard character (`/./`). Those are the extremes of regular expressions, where one finds exact matches and the other matches everything. There are options that are a balance between the two extremes.

You can search for a literal pattern with some flexibility with character classes. Character classes allow you to define a group of characters you wish to match by placing them inside square (`[` and `]`) brackets.

For example, you want to match `bag`, `big`, and `bug` but not `bog`. You can create the regex `/b[aiu]g/` to do this. The `[aiu]` is the character class that will only match the characters `a`, `i`, or `u`.

```js
let bigStr = "big";
let bagStr = "bag";
let bugStr = "bug";
let bogStr = "bog";
let bgRegex = /b[aiu]g/;
bigStr.match(bgRegex);
bagStr.match(bgRegex);
bugStr.match(bgRegex);
bogStr.match(bgRegex);
```

In order, the four `match` calls would return the values `["big"]`, `["bag"]`, `["bug"]`, and `null`.

------

Use a character class with vowels (`a`, `e`, `i`, `o`, `u`) in your regex `vowelRegex` to find all the vowels in the string `quoteSample`.

**Note:** Be sure to match both upper- and lowercase vowels.

```js
let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
let vowelRegex = /[aeiou]/gi; // Change this line
let result = quoteSample.match(vowelRegex); // Change this line
```



### **Match Letters of the Alphabet**

You saw how you can use character sets to specify a group of characters to match, but that's a lot of typing when you need to match a large range of characters (for example, every letter in the alphabet). Fortunately, there is a built-in feature that makes this short and simple.

Inside a character set, you can define a range of characters to match using a hyphen character: `-`.

For example, to match lowercase letters `a` through `e` you would use `[a-e]`.

```js
let catStr = "cat";
let batStr = "bat";
let matStr = "mat";
let bgRegex = /[a-e]at/;
catStr.match(bgRegex);
batStr.match(bgRegex);
matStr.match(bgRegex);
```

In order, the three `match` calls would return the values `["cat"]`, `["bat"]`, and `null`.

------

Match all the letters in the string `quoteSample`.

**Note**: Be sure to match both uppercase and lowercase letters.

```js
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/gi; // Change this line
let result = quoteSample.match(alphabetRegex); // Change this line
```



### **Match Numbers and Letters of the Alphabet**

Using the hyphen (`-`) to match a range of characters is not limited to letters. It also works to match a range of numbers.

For example, `/[0-5]/` matches any number between `0` and `5`, including the `0` and `5`.

Also, it is possible to combine a range of letters and numbers in a single character set.

```js
let jennyStr = "Jenny8675309";
let myRegex = /[a-z0-9]/ig;
jennyStr.match(myRegex);
```

------

Create a single regex that matches a range of letters between `h` and `s`, and a range of numbers between `2` and `6`. Remember to include the appropriate flags in the regex.

```js
let quoteSample = "Blueberry 3.141592653s are delicious.";
let myRegex = /[h-s2-6]/gi; // Change this line
let result = quoteSample.match(myRegex); // Change this line
```



### **Match Single Characters Not Specified**

So far, you have created a set of characters that you want to match, but you could also create a set of characters that you do not want to match. These types of character sets are called negated character sets.

To create a negated character set, you place a caret character (`^`) after the opening bracket and before the characters you do not want to match.

For example, `/[^aeiou]/gi` matches all characters that are not a vowel. Note that characters like `.`, `!`, `[`, `@`, `/` and white space are matched - the negated vowel character set only excludes the vowel characters.

------

Create a single regex that matches all characters that are not a number or a vowel. Remember to include the appropriate flags in the regex.

```js
let quoteSample = "3 blind mice.";
let myRegex = /[^\d|aeiou]/gi; // Change this line
let result = quoteSample.match(myRegex); // Change this line
```



### **Match Characters that Occur One or More Times**

Sometimes, you need to match a character (or group of characters) that appears one or more times in a row. This means it occurs at least once, and may be repeated.

You can use the `+` character to check if that is the case. Remember, the character or pattern has to be present consecutively. That is, the character has to repeat one after the other.

For example, `/a+/g` would find one match in `abc` and return `["a"]`. Because of the `+`, it would also find a single match in `aabc` and return `["aa"]`.

If it were instead checking the string `abab`, it would find two matches and return `["a", "a"]` because the `a` characters are not in a row - there is a `b` between them. Finally, since there is no `a` in the string `bcd`, it wouldn't find a match.

------

You want to find matches when the letter `s` occurs one or more times in `Mississippi`. Write a regex that uses the `+` sign.

```js
let difficultSpelling = "Mississippi";
let myRegex = /s+/gi; // Change this line
let result = difficultSpelling.match(myRegex);
```



### **Match Characters that Occur Zero or More Times**

The last challenge used the plus `+` sign to look for characters that occur one or more times. There's also an option that matches characters that occur zero or more times.

The character to do this is the asterisk or star: `*`.

```js
let soccerWord = "gooooooooal!";
let gPhrase = "gut feeling";
let oPhrase = "over the moon";
let goRegex = /go*/;
soccerWord.match(goRegex);
gPhrase.match(goRegex);
oPhrase.match(goRegex);
```

In order, the three `match` calls would return the values `["goooooooo"]`, `["g"]`, and `null`.

------

For this challenge, `chewieQuote` has been initialized as the string `Aaaaaaaaaaaaaaaarrrgh!` behind the scenes. Create a regex `chewieRegex` that uses the `*` character to match an uppercase `A` character immediately followed by zero or more lowercase `a` characters in `chewieQuote`. Your regex does not need flags or character classes, and it should not match any of the other quotes.

```js
let chewieQuote = "Aaaaaaaaaaaaaaaarrrgh!";
// Only change code below this line
let chewieRegex = /Aa*/; // Change this line
// Only change code above this line

let result = chewieQuote.match(chewieRegex);
```



### **Find Characters with Lazy Matching**

In regular expressions, a greedy match finds the longest possible part of a string that fits the regex pattern and returns it as a match. The alternative is called a lazy match, which finds the smallest possible part of the string that satisfies the regex pattern.

You can apply the regex `/t[a-z]*i/` to the string `"titanic"`. This regex is basically a pattern that starts with `t`, ends with `i`, and has some letters in between.

Regular expressions are by default greedy, so the match would return `["titani"]`. It finds the largest sub-string possible to fit the pattern.

However, you can use the `?` character to change it to lazy matching. `"titanic"` matched against the adjusted regex of `/t[a-z]*?i/` returns `["ti"]`.

**Note:** Parsing HTML with regular expressions should be avoided, but pattern matching an HTML string with regular expressions is completely fine.

------

Fix the regex `/<.*>/` to return the HTML tag `<h1>` and not the text `"<h1>Winter is coming</h1>"`. Remember the wildcard `.` in a regular expression matches any character.

```js
let text = "<h1>Winter is coming</h1>";
let myRegex = /<.*?>/; // Change this line
let result = text.match(myRegex);
```



**Find One or More Criminals in a Hunt**Passed

Time to pause and test your new regex writing skills. A group of criminals escaped from jail and ran away, but you don't know how many. However, you do know that they stay close together when they are around other people. You are responsible for finding all of the criminals at once.

Here's an example to review how to do this:

The regex `/z+/` matches the letter `z` when it appears one or more times in a row. It would find matches in all of the following strings:

```js
"z"
"zzzzzz"
"ABCzzzz"
"zzzzABC"
"abczzzzzzzzzzzzzzzzzzzzzabc"
```

But it does not find matches in the following strings since there are no letter `z` characters:

```js
""
"ABC"
"abcabc"
```

------

Write a greedy regex that finds one or more criminals within a group of other people. A criminal is represented by the capital letter `C`.

```js
let reCriminals = /C+/g; // Change this line
```



### **Match Beginning String Patterns**

Prior challenges showed that regular expressions can be used to look for a number of matches. They are also used to search for patterns in specific positions in strings.

In an earlier challenge, you used the caret character (`^`) inside a character set to create a negated character set in the form `[^thingsThatWillNotBeMatched]`. Outside of a character set, the caret is used to search for patterns at the beginning of strings.

```js
let firstString = "Ricky is first and can be found.";
let firstRegex = /^Ricky/;
firstRegex.test(firstString);
let notFirst = "You can't find Ricky now.";
firstRegex.test(notFirst);
```

The first `test` call would return `true`, while the second would return `false`.

------

Use the caret character in a regex to find `Cal` only in the beginning of the string `rickyAndCal`.

```js
let rickyAndCal = "Cal and Ricky both like racing.";
let calRegex = /^Cal/; // Change this line
let result = calRegex.test(rickyAndCal);
```



### **Match Ending String Patterns**

In the last challenge, you learned to use the caret character to search for patterns at the beginning of strings. There is also a way to search for patterns at the end of strings.

You can search the end of strings using the dollar sign character `$` at the end of the regex.

```js
let theEnding = "This is a never ending story";
let storyRegex = /story$/;
storyRegex.test(theEnding);
let noEnding = "Sometimes a story will have to end";
storyRegex.test(noEnding);
```

The first `test` call would return `true`, while the second would return `false`.

------

Use the anchor character (`$`) to match the string `caboose` at the end of the string `caboose`.

```js
let caboose = "The last car on a train is the caboose";
let lastRegex = /caboose$/; // Change this line
let result = lastRegex.test(caboose);
```



### **Match All Letters and Numbers**

Using character classes, you were able to search for all letters of the alphabet with `[a-z]`. This kind of character class is common enough that there is a shortcut for it, although it includes a few extra characters as well.

The closest character class in JavaScript to match the alphabet is `\w`. This shortcut is equal to `[A-Za-z0-9_]`. This character class matches upper and lowercase letters plus numbers. Note, this character class also includes the underscore character (`_`).

```js
let longHand = /[A-Za-z0-9_]+/;
let shortHand = /\w+/;
let numbers = "42";
let varNames = "important_var";
longHand.test(numbers);
shortHand.test(numbers);
longHand.test(varNames);
shortHand.test(varNames);
```

All four of these `test` calls would return `true`.

These shortcut character classes are also known as shorthand character classes.

------

Use the shorthand character class `\w` to count the number of alphanumeric characters in various quotes and strings.

```js
let quoteSample = "The five boxing wizards jump quickly.";
let alphabetRegexV2 = /\w/g; // It's the small "w"
let result = quoteSample.match(alphabetRegexV2).length;
```



### **Match Everything But Letters and Numbers**

You've learned that you can use a shortcut to match alphanumerics `[A-Za-z0-9_]` using `\w`. A natural pattern you might want to search for is the opposite of alphanumerics.

You can search for the opposite of the `\w` with `\W`. Note, the opposite pattern uses a capital letter. This shortcut is the same as `[^A-Za-z0-9_]`.

```js
let shortHand = /\W/;
let numbers = "42%";
let sentence = "Coding!";
numbers.match(shortHand);
sentence.match(shortHand);
```

The first `match` call would return the value `["%"]` and the second would return `["!"]`.

------

Use the shorthand character class `\W` to count the number of non-alphanumeric characters in various quotes and strings.

```js
let quoteSample = "The five boxing wizards jump quickly.";
let nonAlphabetRegex = /[\W]/g; // That's is capital "W"
let result = quoteSample.match(nonAlphabetRegex).length;
```



### **Match All Numbers**

You've learned shortcuts for common string patterns like alphanumerics. Another common pattern is looking for just digits or numbers.

The shortcut to look for digit characters is `\d`, with a lowercase `d`. This is equal to the character class `[0-9]`, which looks for a single character of any number between zero and nine.

------

Use the shorthand character class `\d` to count how many digits are in movie titles. Written out numbers ("six" instead of 6) do not count.

```js
let movieName = "2001: A Space Odyssey";
let numRegex = /\d/g; // Change this line
let result = movieName.match(numRegex).length;
```



### **Match All Non-Numbers**

The last challenge showed how to search for digits using the shortcut `\d` with a lowercase `d`. You can also search for non-digits using a similar shortcut that uses an uppercase `D` instead.

The shortcut to look for non-digit characters is `\D`. This is equal to the character class `[^0-9]`, which looks for a single character that is not a number between zero and nine.

------

Use the shorthand character class for non-digits `\D` to count how many non-digits are in movie titles.

```js
let movieName = "2001: A Space Odyssey";
let noNumRegex = /\D/g; // Change this line
let result = movieName.match(noNumRegex).length
```



### **Restrict Possible Usernames**

Usernames are used everywhere on the internet. They are what give users a unique identity on their favorite sites.

You need to check all the usernames in a database. Here are some simple rules that users have to follow when creating their username.

1. Usernames can only use alpha-numeric characters.
2. The only numbers in the username have to be at the end. There can be zero or more of them at the end. Username cannot start with the number.
3. Username letters can be lowercase and uppercase.
4. Usernames have to be at least two characters long. A two-character username can only use alphabet letters as characters.

------

Change the regex `userCheck` to fit the constraints listed above.

```js
let username = "JackOfAllTrades";
let userCheck = /^[a-z][a-z]+\d*$|^[a-z]\d\d+$/i; // Change this line
let result = userCheck.test(username);
```



### **Positive and Negative Lookahead**

Lookaheads are patterns that tell JavaScript to look-ahead in your string to check for patterns further along. This can be useful when you want to search for multiple patterns over the same string.

There are two kinds of lookaheads: positive lookahead and negative lookahead.

A positive lookahead will look to make sure the element in the search pattern is there, but won't actually match it. A positive lookahead is used as `(?=...)` where the `...` is the required part that is not matched.

On the other hand, a negative lookahead will look to make sure the element in the search pattern is not there. A negative lookahead is used as `(?!...)` where the `...` is the pattern that you do not want to be there. The rest of the pattern is returned if the negative lookahead part is not present.

Lookaheads are a bit confusing but some examples will help.

```js
let quit = "qu";
let noquit = "qt";
let quRegex= /q(?=u)/;
let qRegex = /q(?!u)/;
quit.match(quRegex);
noquit.match(qRegex);
```

Both of these `match` calls would return `["q"]`.

A more practical use of lookaheads is to check two or more patterns in one string. Here is a (naively) simple password checker that looks for between 3 and 6 characters and at least one number:

```js
let password = "abc123";
let checkPass = /(?=\w{3,6})(?=\D*\d)/;
checkPass.test(password);
```

------

Use lookaheads in the `pwRegex` to match passwords that are greater than 5 characters long, and have two consecutive digits.

**Solution:**

```js
let sampleWord = "astronaut";
let pwRegex = /(?=\w{6})(?=\w*\d{2})/gi; // Change this line
let result = pwRegex.test(sampleWord);
```























# [Javascript Object Oriented Programming](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming)



### **Create a Basic JavaScript Object**

Think about things people see every day, like cars, shops, and birds. These are all objects: tangible things people can observe and interact with.

What are some qualities of these objects? A car has wheels. Shops sell items. Birds have wings.

These qualities, or properties, define what makes up an object. Note that similar objects share the same properties, but may have different values for those properties. For example, all cars have wheels, but not all cars have the same number of wheels.

Objects in JavaScript are used to model real-world objects, giving them properties and behavior just like their real-world counterparts. Here's an example using these concepts to create a `duck` object:

```js
let duck = {
  name: "Aflac",
  numLegs: 2
};
```

This `duck` object has two property/value pairs: a `name` of `Aflac` and a `numLegs` of 2.



### **Use Dot Notation to Access the Properties of an Object**

The last challenge created an object with various properties. Now you'll see how to access the values of those properties. Here's an example:

```js
let duck = {
  name: "Aflac",
  numLegs: 2
};
console.log(duck.name);
```

Dot notation is used on the object name, `duck`, followed by the name of the property, `name`, to access the value of `Aflac`.



### **Create a Method on an Object **

Objects can have a special type of property, called a method.

Methods are properties that are functions. This adds different behavior to an object. Here is the `duck` example with a method:

```javascript
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();
// Returns "The name of this duck is Aflac."
```

The example adds the `sayName` method, which is a function that returns a sentence giving the name of the `duck`. Notice that the method accessed the `name` property in the return statement using `duck.name`. The next challenge will cover another way to do this.





### **Make Code More Reusable with the this Keyword**

The last challenge introduced a method to the `duck` object. It used `duck.name` dot notation to access the value for the `name` property within the return statement:

```js
sayName: function() {return "The name of this duck is " + duck.name + ".";}
```

While this is a valid way to access the object's property, there is a pitfall here. If the variable name changes, any code referencing the original name would need to be updated as well. In a short object definition, it isn't a problem, but if an object has many references to its properties there is a greater chance for error.

A way to avoid these issues is with the `this` keyword:

```js
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + this.name + ".";}
};
```

`this` is a deep topic, and the above example is only one way to use it. In the current context, `this` refers to the object that the method is associated with: `duck`. If the object's name is changed to `mallard`, it is not necessary to find all the references to `duck` in the code. It makes the code reusable and easier to read.





### **Define a Constructor Function**

Constructors are functions that create new objects. They define properties and behaviors that will belong to the new object. Think of them as a blueprint for the creation of new objects.

Here is an example of a constructor:

```js
function Bird() {
  this.name = "Albert";
  this.color = "blue";
  this.numLegs = 2;
}
```

This constructor defines a `Bird` object with properties `name`, `color`, and `numLegs` set to Albert, blue, and 2, respectively. Constructors follow a few conventions:

- Constructors are defined with a capitalized name to distinguish them from other functions that are not `constructors`.
- Constructors use the keyword `this` to set properties of the object they will create. Inside the constructor, `this` refers to the new object it will create.
- Constructors define properties and behaviors instead of returning a value as other functions might.



### **Use a Constructor to Create Objects**

Here's the `Bird` constructor from the previous challenge:

```js
function Bird() {
  this.name = "Albert";
  this.color  = "blue";
  this.numLegs = 2;
  // "this" inside the constructor always refers to the object being created
}

let blueBird = new Bird();
```

Notice that the `new` operator is used when calling a constructor. This tells JavaScript to create a new instance of `Bird` called `blueBird`. Without the `new` operator, `this` inside the constructor would not point to the newly created object, giving unexpected results. Now `blueBird` has all the properties defined inside the `Bird` constructor:

```js
blueBird.name; // => Albert
blueBird.color; // => blue
blueBird.numLegs; // => 2
```

Just like any other object, its properties can be accessed and modified:

```js
blueBird.name = 'Elvira';
blueBird.name; // => Elvira
```





### **Extend Constructors to Receive Arguments**

The `Bird` and `Dog` constructors from last challenge worked well. However, notice that all `Birds` that are created with the `Bird` constructor are automatically named Albert, are blue in color, and have two legs. What if you want birds with different values for name and color? It's possible to change the properties of each bird manually but that would be a lot of work:

```js
let swan = new Bird();
swan.name = "Carlos";
swan.color = "white";
```

Suppose you were writing a program to keep track of hundreds or even thousands of different birds in an aviary. It would take a lot of time to create all the birds, then change the properties to different values for every one. To more easily create different `Bird` objects, you can design your Bird constructor to accept parameters:

```js
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```

Then pass in the values as arguments to define each unique bird into the `Bird` constructor: `let cardinal = new Bird("Bruce", "red");` This gives a new instance of `Bird` with name and color properties set to Bruce and red, respectively. The `numLegs` property is still set to 2. The `cardinal` has these properties:

```js
cardinal.name // => Bruce
cardinal.color // => red
cardinal.numLegs // => 2
```

The constructor is more flexible. It's now possible to define the properties for each `Bird` at the time it is created, which is one way that JavaScript constructors are so useful. They group objects together based on shared characteristics and behavior and define a blueprint that automates their creation.





### **Verify an Object's Constructor with instanceof**

Anytime a constructor function creates a new object, that object is said to be an instance of its constructor. JavaScript gives a convenient way to verify this with the `instanceof` operator. `instanceof` allows you to compare an object to a constructor, returning `true` or `false` based on whether or not that object was created with the constructor. Here's an example:

```js
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird; // => true
```

If an object is created without using a constructor, `instanceof` will verify that it is not an instance of that constructor:

```js
let canary = {
  name: "Mildred",
  color: "Yellow",
  numLegs: 2
};

canary instanceof Bird; // => false
```

**Exercise:**- Create a new instance of the `House` constructor, calling it `myHouse` and passing a number of bedrooms. Then, use `instanceof` to verify that it is an instance of `House`.

```js

function House(numBedrooms) {

 this.numBedrooms = numBedrooms;

}

// Only change code below this line

let myHouse = new House(4);

console.log(myHouse instanceof House);
```

### **Understand Own Properties** 

In the following example, the `Bird` constructor defines two properties: `name` and `numLegs`:

```js
function Bird(name) {
  this.name  = name;
  this.numLegs = 2;
}

let duck = new Bird("Donald");
let canary = new Bird("Tweety");
```

`name` and `numLegs` are called `own` properties, because they are defined directly on the instance object. That means that `duck` and `canary` each has its own separate copy of these properties. In fact every instance of `Bird` will have its own copy of these properties. The following code adds all of the `own` properties of `duck` to the array `ownProps`:

```js
let ownProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}

console.log(ownProps); // prints [ "name", "numLegs" ]
```

### **Use Prototype Properties to Reduce Duplicate Code**

Since `numLegs` will probably have the same value for all instances of `Bird`, you essentially have a duplicated variable `numLegs` inside each `Bird` instance.

This may not be an issue when there are only two instances, but imagine if there are millions of instances. That would be a lot of duplicated variables.

A better way is to use `Bird’s` `prototype`. Properties in the `prototype` are shared among ALL instances of `Bird`. Here's how to add `numLegs` to the `Bird prototype`:

```js
Bird.prototype.numLegs = 2;
```

Now all instances of `Bird` have the `numLegs` property.

```js
console.log(duck.numLegs);  // prints 2
console.log(canary.numLegs);  // prints 2
```

Since all instances automatically have the properties on the `prototype`, think of a `prototype` as a "recipe" for creating objects. Note that the `prototype` for `duck` and `canary` is part of the `Bird` constructor as `Bird.prototype`. Nearly every object in JavaScript has a `prototype` property which is part of the constructor function that created it.





### **Understand the Constructor Property**

There is a special `constructor` property located on the object instances `duck` and `beagle` that were created in the previous challenges:

```js
let duck = new Bird();
let beagle = new Dog();

console.log(duck.constructor === Bird);  //prints true
console.log(beagle.constructor === Dog);  //prints true
```

Note that the `constructor` property is a reference to the constructor function that created the instance. The advantage of the `constructor` property is that it's possible to check for this property to find out what kind of object it is. Here's an example of how this could be used:

```js
function joinBirdFraternity(candidate) {
  if (candidate.constructor === Bird) {
    return true;
  } else {
    return false;
  }
}
```

**Note**
Since the `constructor` property can be overwritten (which will be covered in the next two challenges) it’s generally better to use the `instanceof` method to check the type of an object.

### **Change the Prototype to a New Object**

Up until now you have been adding properties to the `prototype` individually:

```js
Bird.prototype.numLegs = 2;
```

This becomes tedious after more than a few properties.

```js
Bird.prototype.eat = function() {
  console.log("nom nom nom");
}

Bird.prototype.describe = function() {
  console.log("My name is " + this.name);
}
```

A more efficient way is to set the `prototype` to a new object that already contains the properties. This way, the properties are added all at once:

```js
Bird.prototype = {
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

### **Set the Constructor Property when Changing the Prototype**

There is one crucial side effect of manually setting the prototype to a new object. It erases the `constructor` property! This property can be used to check which constructor function created the instance, but since the property has been overwritten, it now gives false results:

```js
duck.constructor === Bird; // false -- Oops
duck.constructor === Object; // true, all objects inherit from Object.prototype
duck instanceof Bird; // true, still works
```

To fix this, whenever a prototype is manually set to a new object, remember to define the `constructor` property:

```js
Bird.prototype = {
  constructor: Bird, // define the constructor property
  numLegs: 2,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name); 
  }
};
```

### **Understand Where an Object’s Prototype Comes From**

Just like people inherit genes from their parents, an object inherits its `prototype` directly from the constructor function that created it. For example, here the `Bird` constructor creates the `duck` object:

```js
function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");
```

`duck` inherits its `prototype` from the `Bird` constructor function. You can show this relationship with the `isPrototypeOf` method:

```js
Bird.prototype.isPrototypeOf(duck);
// returns true
```





### **Understand the Prototype Chain**

All objects in JavaScript (with a few exceptions) have a `prototype`. Also, an object’s `prototype` itself is an object.

```js
function Bird(name) {
  this.name = name;
}

typeof Bird.prototype; // yields 'object'
```

Because a `prototype` is an object, a `prototype` can have its own `prototype`! In this case, the `prototype` of `Bird.prototype` is `Object.prototype`:

```js
Object.prototype.isPrototypeOf(Bird.prototype); // returns true
```

How is this useful? You may recall the `hasOwnProperty` method from a previous challenge:

```js
let duck = new Bird("Donald");
duck.hasOwnProperty("name"); // yields true
```

The `hasOwnProperty` method is defined in `Object.prototype`, which can be accessed by `Bird.prototype`, which can then be accessed by `duck`. This is an example of the `prototype` chain. In this `prototype` chain, `Bird` is the `supertype` for `duck`, while `duck` is the `subtype`. `Object` is a `supertype` for both `Bird` and `duck`. `Object` is a `supertype` for all objects in JavaScript. Therefore, any object can use the `hasOwnProperty` method.
[More...](https://community.risingstack.com/javascript-prototype-chain-inheritance/#:~:text=The%20Prototype%20Chain,-Every%20object%20has&text=When%20an%20attribute%20is%20called,or%20the%20end%20is%20reached.)

### **Use Inheritance So You Don't Repeat Yourself**

There's a principle in programming called Don't Repeat Yourself (DRY). The reason repeated code is a problem is because any change requires fixing code in multiple places. This usually means more work for programmers and more room for errors.

Notice in the example below that the `describe` method is shared by `Bird` and `Dog`:

```js
Bird.prototype = {
  constructor: Bird,
  describe: function() {
    console.log("My name is " + this.name);
  }
};

Dog.prototype = {
  constructor: Dog,
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

The `describe` method is repeated in two places. The code can be edited to follow the DRY principle by creating a `supertype` (or parent) called `Animal`:

```js
function Animal() { };

Animal.prototype = {
  constructor: Animal, 
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

Since `Animal` includes the `describe` method, you can remove it from `Bird` and `Dog`:

```js
Bird.prototype = {
  constructor: Bird
};

Dog.prototype = {
  constructor: Dog
};
```





### **Inherit Behaviors from a Supertype**

In the previous challenge, you created a `supertype` called `Animal` that defined behaviors shared by all animals:

```js
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};
```

This and the next challenge will cover how to reuse `Animal's` methods inside `Bird` and `Dog` without defining them again. It uses a technique called inheritance. This challenge covers the first step: make an instance of the `supertype` (or parent). You already know one way to create an instance of `Animal` using the `new` operator:

```js
let animal = new Animal();
```

There are some disadvantages when using this syntax for inheritance, which are too complex for the scope of this challenge. Instead, here's an alternative approach without those disadvantages:

```js
let animal = Object.create(Animal.prototype);
```

`Object.create(obj)` creates a new object, and sets `obj` as the new object's `prototype`. Recall that the `prototype` is like the "recipe" for creating an object. By setting the `prototype` of `animal` to be `Animal's` `prototype`, you are effectively giving the `animal` instance the same "recipe" as any other instance of `Animal`.

```js
animal.eat(); // prints "nom nom nom"
animal instanceof Animal; // => true
```

### **Set the Child's Prototype to an Instance of the Parent**

In the previous challenge you saw the first step for inheriting behavior from the supertype (or parent) `Animal`: making a new instance of `Animal`.

This challenge covers the next step: set the `prototype` of the subtype (or child)—in this case, `Bird`—to be an instance of `Animal`.

```js
Bird.prototype = Object.create(Animal.prototype);
```

Remember that the `prototype` is like the "recipe" for creating an object. In a way, the recipe for `Bird` now includes all the key "ingredients" from `Animal`.

```js
let duck = new Bird("Donald");
duck.eat(); // prints "nom nom nom"
```

`duck` inherits all of `Animal`'s properties, including the `eat` method.





### **Reset an Inherited Constructor Property**

When an object inherits its `prototype` from another object, it also inherits the supertype's constructor property.

Here's an example:

```js
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
let duck = new Bird();
duck.constructor // function Animal(){...}
```

But `duck` and all instances of `Bird` should show that they were constructed by `Bird` and not `Animal`. To do so, you can manually set `Bird's` constructor property to the `Bird` object:

```js
Bird.prototype.constructor = Bird;
duck.constructor // function Bird(){...}
```

### **Add Methods After Inheritance**

A constructor function that inherits its `prototype` object from a super type constructor function can still have its own methods in addition to inherited methods.

For example, `Bird` is a constructor that inherits its `prototype` from `Animal`:

```js
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};
function Bird() { }
Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;
```

In addition to what is inherited from `Animal`, you want to add behavior that is unique to `Bird` objects. Here, `Bird` will get a `fly()` function. Functions are added to `Bird's` `prototype` the same way as any constructor function:

```js
Bird.prototype.fly = function() {
  console.log("I'm flying!");
};
```

Now instances of `Bird` will have both `eat()` and `fly()` methods:

```js
let duck = new Bird();
duck.eat(); // prints "nom nom nom"
duck.fly(); // prints "I'm flying!"
```

### **Override Inherited Methods**

In previous lessons, you learned that an object can inherit its behavior (methods) from another object by referencing its `prototype` object:

```js
ChildObject.prototype = Object.create(ParentObject.prototype);
```

Then the `ChildObject` received its own methods by chaining them onto its `prototype`:

```js
ChildObject.prototype.methodName = function() {...};
```

It's possible to override an inherited method. It's done the same way - by adding a method to `ChildObject.prototype` using the same method name as the one to override. Here's an example of `Bird` overriding the `eat()` method inherited from `Animal`:

```js
function Animal() { }
Animal.prototype.eat = function() {
  return "nom nom nom";
};
function Bird() { }

// Inherit all methods from Animal
Bird.prototype = Object.create(Animal.prototype);

// Bird.eat() overrides Animal.eat()
Bird.prototype.eat = function() {
  return "peck peck peck";
};
```

If you have an instance `let duck = new Bird();` and you call `duck.eat()`, this is how JavaScript looks for the method on `duck’s` `prototype` chain:

1. duck => Is eat() defined here? No.
2. Bird => Is eat() defined here? => Yes. Execute it and stop searching.
3. Animal => eat() is also defined, but JavaScript stopped searching before reaching this level.
4. Object => JavaScript stopped searching before reaching this level.



### **Use a Mixin to Add Common Behavior Between Unrelated Objects**

As you have seen, behavior is shared through inheritance. However, there are cases when inheritance is not the best solution. Inheritance does not work well for unrelated objects like `Bird` and `Airplane`. They can both fly, but a `Bird` is not a type of `Airplane` and vice versa.

For unrelated objects, it's better to use mixins. A mixin allows other objects to use a collection of functions.

```js
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};
```

The `flyMixin` takes any object and gives it the `fly` method.

```js
let bird = {
  name: "Donald",
  numLegs: 2
};

let plane = {
  model: "777",
  numPassengers: 524
};

flyMixin(bird);
flyMixin(plane);
```

Here `bird` and `plane` are passed into `flyMixin`, which then assigns the `fly` function to each object. Now `bird` and `plane` can both fly:

```js
bird.fly(); // prints "Flying, wooosh!"
plane.fly(); // prints "Flying, wooosh!"
```

Note how the mixin allows for the same `fly` method to be reused by unrelated objects `bird` and `plane`.



### **Use Closure to Protect Properties Within an Object from Being Modified Externally**

In the previous challenge, `bird` had a public property `name`. It is considered public because it can be accessed and changed outside of `bird`'s definition.

```js
bird.name = "Duffy";
```

Therefore, any part of your code can easily change the name of `bird` to any value. Think about things like passwords and bank accounts being easily changeable by any part of your codebase. That could cause a lot of issues.

The simplest way to make this public property private is by creating a variable within the constructor function. This changes the scope of that variable to be within the constructor function versus available globally. This way, the variable can only be accessed and changed by methods also within the constructor function.

```js
function Bird() {
  let hatchedEgg = 10; // private variable

  /* publicly available method that a bird object can use */
  this.getHatchedEggCount = function() { 
    return hatchedEgg;
  };
}
let ducky = new Bird();
ducky.getHatchedEggCount(); // returns 10
```

Here `getHatchedEggCount` is a privileged method, because it has access to the private variable `hatchedEgg`. This is possible because `hatchedEgg` is declared in the same context as `getHatchedEggCount`. In JavaScript, a function always has access to the context in which it was created. This is called `closure`.



### **Understand the Immediately Invoked Function Expression (IIFE)**

A common pattern in JavaScript is to execute a function as soon as it is declared:

```js
(function () {
  console.log("Chirp, chirp!");
})(); // this is an anonymous function expression that executes right away
// Outputs "Chirp, chirp!" immediately
```

Note that the function has no name and is not stored in a variable. The two parentheses () at the end of the function expression cause it to be immediately executed or invoked. This pattern is known as an immediately invoked function expression or IIFE.



### **Use an IIFE to Create a Module**

An immediately invoked function expression (IIFE) is often used to group related functionality into a single object or module. For example, an earlier challenge defined two mixins:

```js
function glideMixin(obj) {
  obj.glide = function() {
    console.log("Gliding on the water");
  };
}
function flyMixin(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  };
}
```

We can group these mixins into a module as follows:

```js
let motionModule = (function () {
  return {
    glideMixin: function(obj) {
      obj.glide = function() {
        console.log("Gliding on the water");
      };
    },
    flyMixin: function(obj) {
      obj.fly = function() {
        console.log("Flying, wooosh!");
      };
    }
  }
})(); // The two parentheses cause the function to be immediately invoked
```

Note that you have an immediately invoked function expression (IIFE) that returns an object `motionModule`. This returned object contains all of the mixin behaviors as properties of the object. The advantage of the module pattern is that all of the motion behaviors can be packaged into a single object that can then be used by other parts of your code. Here is an example using it:

```js
motionModule.glideMixin(duck);
duck.glide();
```







# [Functional Programming](https://youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)


### **Functional Programming**

Functional programming is a style of programming where solutions are simple, isolated functions, without any side effects outside of the function scope.

```
INPUT -> PROCESS -> OUTPUT
```

Functional programming is about:

1. Isolated functions - there is no dependence on the state of the program, which includes global variables that are subject to change
2. Pure functions - the same input always gives the same output
3. Functions with limited side effects - any changes, or mutations, to the state of the program outside the function are carefully controlled



### **Understand Functional Programming Terminology**

The FCC Team had a mood swing and now wants two types of tea: green tea and black tea. General Fact: Client mood swings are pretty common.

With that information, we'll need to revisit the `getTea` function from last challenge to handle various tea requests. We can modify `getTea` to accept a function as a parameter to be able to change the type of tea it prepares. This makes `getTea` more flexible, and gives the programmer more control when client requests change.

But first, let's cover some functional terminology:

Callbacks are the functions that are slipped or passed into another function to decide the invocation of that function. You may have seen them passed to other methods, for example in `filter`, the callback function tells JavaScript the criteria for how to filter an array.

Functions that can be assigned to a variable, passed into another function, or returned from another function just like any other normal value, are called first class functions. In JavaScript, all functions are first class functions.

The functions that take a function as an argument, or return a function as a return value are called higher order functions.

When the functions are passed in to another function or returned from another function, then those functions which gets passed in or returned can be called a lambda.



### **Use the map Method to Extract Data from an Array**

So far we have learned to use pure functions to avoid side effects in a program. Also, we have seen the value in having a function only depend on its input arguments.

This is only the beginning. As its name suggests, functional programming is centered around a theory of functions.

It would make sense to be able to pass them as arguments to other functions, and return a function from another function. Functions are considered first class objects in JavaScript, which means they can be used like any other object. They can be saved in variables, stored in an object, or passed as function arguments.

Let's start with some simple array functions, which are methods on the array object prototype. In this exercise we are looking at `Array.prototype.map()`, or more simply `map`.

The `map` method iterates over each item in an array and returns a new array containing the results of calling the callback function on each element. It does this without mutating the original array.

When the callback is used, it is passed three arguments. The first argument is the current element being processed. The second is the index of that element and the third is the array upon which the `map` method was called.

See below for an example using the `map` method on the `users` array to return a new array containing only the names of the users as elements. For simplicity, the example only uses the first argument of the callback.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const names = users.map(user => user.name);
console.log(names);
```

The console would display the value `[ 'John', 'Amy', 'camperCat' ]`.

--------

The `watchList` array holds objects with information on several movies. Use `map` on `watchList` to assign a new array of objects with only `title` and `rating` keys to the `ratings` variable. The code in the editor currently uses a `for` loop to do this, so you should replace the loop functionality with your `map` expression.

**Solution:**

```js

// Only change code below this line
const ratings = watchList.map(item => ({
  title: item["Title"],
  rating: item["imdbRating"]
}));
// Only change code above this line

console.log(rating);
```



### **Implement map on a Prototype**

As you have seen from applying `Array.prototype.map()`, or simply `map()` earlier, the `map` method returns an array of the same length as the one it was called on. It also doesn't alter the original array, as long as its callback function doesn't.

In other words, `map` is a pure function, and its output depends solely on its inputs. Plus, it takes another function as its argument.

You might learn a lot about the `map` method if you implement your own version of it. It is recommended you use a `for` loop or `Array.prototype.forEach()`.

------

Write your own `Array.prototype.myMap()`, which should behave exactly like `Array.prototype.map()`. You should not use the built-in `map` method. The `Array` instance can be accessed in the `myMap` method using `this`.

```js
// The global variable
var s = [23, 65, 98, 5];

Array.prototype.myMap = function(callback) {
  var newArray = [];
  // Only change code below this line
  for(let i = 0; i < this.length; i++) {
    newArray.push(callback(this[i]));
  }
  // Only change code above this line
  return newArray;
};

var new_s = s.myMap(function(item) {
  return item * 2;
});
```



### **Use the filter Method to Extract Data from an Array**

Another useful array function is `Array.prototype.filter()`, or simply `filter()`.

`filter` calls a function on each element of an array and returns a new array containing only the elements for which that function returns `true`. In other words, it filters the array, based on the function passed to it. Like `map`, it does this without needing to modify the original array.

The callback function accepts three arguments. The first argument is the current element being processed. The second is the index of that element and the third is the array upon which the `filter` method was called.

See below for an example using the `filter` method on the `users` array to return a new array containing only the users under the age of 30. For simplicity, the example only uses the first argument of the callback.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersUnder30 = users.filter(user => user.age < 30);
console.log(usersUnder30); 
```

The console would display the value `[ { name: 'Amy', age: 20 }, { name: 'camperCat', age: 10 } ]`.

------

The variable `watchList` holds an array of objects with information on several movies. Use a combination of `filter` and `map` on `watchList` to assign a new array of objects with only `title` and `rating` keys. The new array should only include objects where `imdbRating` is greater than or equal to 8.0. Note that the `rating` values are saved as strings in the object and you may need to convert them into numbers to perform mathematical operations on them.

**Solution: **

```js

// Only change code below this line
var finalArray = watchList.filter(function(num) {
  return num["imdbRating"] > 8;
});

var filteredList = finalArray.map(val => ({
  title: val["Title"],
  rating: val["imdbRating"]
}))
// Only change code above this line

console.log(filteredList);
```



### **Implement the filter Method on a Prototype**

You might learn a lot about the `filter` method if you implement your own version of it. It is recommended you use a `for` loop or `Array.prototype.forEach()`.

------

Write your own `Array.prototype.myFilter()`, which should behave exactly like `Array.prototype.filter()`. You should not use the built-in `filter` method. The `Array` instance can be accessed in the `myFilter` method using `this`.

**Solution:**

```js
// The global variable
var s = [23, 65, 98, 5];

Array.prototype.myFilter = function(callback) {
  // Only change code below this line
  var newArray = [];
  for(let i = 0; i < this.length; i++) {
    if(callback(this[i]) == true) {
      newArray.push(this[i]);
    }
  }
  // Only change code above this line
  return newArray;
};

var new_s = s.myFilter(function(item) {
  return item % 2 === 1;
});
```



### **Return Part of an Array Using the `slice` Method**

The `slice` method returns a copy of certain elements of an array. It can take two arguments, the first gives the index of where to begin the slice, the second is the index for where to end the slice (and it's non-inclusive). If the arguments are not provided, the default is to start at the beginning of the array through the end, which is an easy way to make a copy of the entire array. The `slice` method does not mutate the original array, but returns a new one.

Here's an example:

```js
var arr = ["Cat", "Dog", "Tiger", "Zebra"];
var newArray = arr.slice(1, 3);
```

`newArray` would have the value `["Dog", "Tiger"]`.

------

Use the `slice` method in the `sliceArray` function to return part of the `anim` array given the provided `beginSlice` and `endSlice` indices. The function should return an array.

```js
function sliceArray(anim, beginSlice, endSlice) {
  // Only change code below this line
return anim.slice(beginSlice, endSlice);

  // Only change code above this line
}
var inputAnim = ["Cat", "Dog", "Tiger", "Zebra", "Ant"];
sliceArray(inputAnim, 1, 3);
```



 ### **Remove Elements from an Array Using `slice` Instead of `splice`**

A common pattern while working with arrays is when you want to remove items and keep the rest of the array. JavaScript offers the `splice` method for this, which takes arguments for the index of where to start removing items, then the number of items to remove. If the second argument is not provided, the default is to remove items through the end. However, the `splice` method mutates the original array it is called on. Here's an example:

```js
var cities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
cities.splice(3, 1);
```

Here `splice` returns the string `London` and deletes it from the cities array. `cities` will have the value `["Chicago", "Delhi", "Islamabad", "Berlin"]`.

As we saw in the last challenge, the `slice` method does not mutate the original array, but returns a new one which can be saved into a variable. Recall that the `slice` method takes two arguments for the indices to begin and end the slice (the end is non-inclusive), and returns those items in a new array. Using the `slice` method instead of `splice` helps to avoid any array-mutating side effects.

------

Rewrite the function `nonMutatingSplice` by using `slice` instead of `splice`. It should limit the provided `cities` array to a length of 3, and return a new array with only the first three items.

Do not mutate the original array provided to the function.

**Solution:**

```js
function nonMutatingSplice(cities) {
  // Only change code below this line
  return cities.slice(0, 3);

  // Only change code above this line
}
var inputCities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
console.log(nonMutatingSplice(inputCities));
```



### **Combine Two Arrays Using the `concat` Method**

Concatenation means to join items end to end. JavaScript offers the `concat` method for both strings and arrays that work in the same way. For arrays, the method is called on one, then another array is provided as the argument to `concat`, which is added to the end of the first array. It returns a new array and does not mutate either of the original arrays. Here's an example:

```js
[1, 2, 3].concat([4, 5, 6]);
```

The returned array would be `[1, 2, 3, 4, 5, 6]`.

------

Use the `concat` method in the `nonMutatingConcat` function to concatenate `attach` to the end of `original`. The function should return the concatenated array.

**Soluation:**

```js
function nonMutatingConcat(original, attach) {
  // Only change code below this line
  return original.concat(attach);

  // Only change code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
console.log(nonMutatingConcat(first, second));
```



### **Add Elements to the End of an Array Using concat Instead of push**

Functional programming is all about creating and using non-mutating functions.

The last challenge introduced the `concat` method as a way to combine arrays into a new one without mutating the original arrays. Compare `concat` to the `push` method. `push` adds an item to the end of the same array it is called on, which mutates that array. Here's an example:

```js
var arr = [1, 2, 3];
arr.push([4, 5, 6]);
```

`arr` would have a modified value of `[1, 2, 3, [4, 5, 6]]`, which is not the functional programming way.

`concat` offers a way to add new items to the end of an array without any mutating side effects.

------

Change the `nonMutatingPush` function so it uses `concat` to add `newItem` to the end of `original` instead of `push`. The function should return an array.

```js
function nonMutatingPush(original, newItem) {
  // Only change code below this line
  return original.concat(newItem);

  // Only change code above this line
}
var first = [1, 2, 3];
var second = [4, 5];
nonMutatingPush(first, second);
```



### **Use the reduce Method to Analyze Data**

`Array.prototype.reduce()`, or simply `reduce()`, is the most general of all array operations in JavaScript. You can solve almost any array processing problem using the `reduce` method.

The `reduce` method allows for more general forms of array processing, and it's possible to show that both `filter` and `map` can be derived as special applications of `reduce`. The `reduce` method iterates over each item in an array and returns a single value (i.e. string, number, object, array). This is achieved via a callback function that is called on each iteration.

The callback function accepts four arguments. The first argument is known as the accumulator, which gets assigned the return value of the callback function from the previous iteration, the second is the current element being processed, the third is the index of that element and the fourth is the array upon which `reduce` is called.

In addition to the callback function, `reduce` has an additional parameter which takes an initial value for the accumulator. If this second parameter is not used, then the first iteration is skipped and the second iteration gets passed the first element of the array as the accumulator.

See below for an example using `reduce` on the `users` array to return the sum of all the users' ages. For simplicity, the example only uses the first and second arguments.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);
console.log(sumOfAges);
```

The console would display the value `64`.

In another example, see how an object can be returned containing the names of the users as properties with their ages as values.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersObj = users.reduce((obj, user) => {
  obj[user.name] = user.age;
  return obj;
}, {});
console.log(usersObj);
```

The console would display the value `{ John: 34, Amy: 20, camperCat: 10 }`.

------

The variable `watchList` holds an array of objects with information on several movies. Use `reduce` to find the average IMDB rating of the movies directed by `Christopher Nolan`. Recall from prior challenges how to `filter` data and `map` over it to pull what you need. You may need to create other variables, and return the average rating from `getRating` function. Note that the rating values are saved as strings in the object and need to be converted into numbers before they are used in any mathematical operations.

**Solution: **

```js
let averageRating = watchList.filter(function(val) {
  return val.Director == "Christopher Nolan";
})
.map(function(val1) {
  return Number(val1.imdbRating);
})
.reduce(function(val, ratings) {
 return val + ratings
})
/watchList.filter(function(film) {
  return film.Director == "Christopher Nolan";
})
.length;
  // Only change code above this line
  
  return averageRating;
}
console.log(getRating(watchList));
```





### **Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem**

Now that you have worked through a few challenges using higher-order functions like `map()`, `filter()`, and `reduce()`, you now get to apply them to solve a more complex challenge.

------

We have defined a function named `squareList`. You need to complete the code for the `squareList` function using any combination of `map()`, `filter()`, and `reduce()` so that it returns a new array containing only the square of *only* the positive integers (decimal numbers are not integers) when an array of real numbers is passed to it. An example of an array containing only real numbers is `[-3, 4.8, 5, 3, -3.2]`.

**Note:** Your function should not use any kind of `for` or `while` loops or the `forEach()` function.

**Solution:**

```js
const squareList = arr => {
  // Only change code below this line
  return arr.filter(function(val) {
    return Number.isInteger(val) == true & val > 0;
  })
  .map(function(val) {
    return val * val;
  });
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```



### **Sort an Array Alphabetically using the sort Method**

The `sort` method sorts the elements of an array according to the callback function.

For example:

```js
function ascendingOrder(arr) {
  return arr.sort(function(a, b) {
    return a - b;
  });
}
ascendingOrder([1, 5, 2, 3, 4]);
```

This would return the value `[1, 2, 3, 4, 5]`.

```js
function reverseAlpha(arr) {
  return arr.sort(function(a, b) {
    return a === b ? 0 : a < b ? 1 : -1;
  });
}
reverseAlpha(['l', 'h', 'z', 'b', 's']);
```

This would return the value `['z', 's', 'l', 'h', 'b']`.

JavaScript's default sorting method is by string Unicode point value, which may return unexpected results. Therefore, it is encouraged to provide a callback function to specify how to sort the array items. When such a callback function, normally called `compareFunction`, is supplied, the array elements are sorted according to the return value of the `compareFunction`: If `compareFunction(a,b)` returns a value less than 0 for two elements `a` and `b`, then `a` will come before `b`. If `compareFunction(a,b)` returns a value greater than 0 for two elements `a` and `b`, then `b` will come before `a`. If `compareFunction(a,b)` returns a value equal to 0 for two elements `a` and `b`, then `a` and `b` will remain unchanged.

------

Use the `sort` method in the `alphabeticalOrder` function to sort the elements of `arr` in alphabetical order.

**Solution:**

```js
function alphabeticalOrder(arr) {
  // Only change code below this line
  return arr.sort(function(a, b) {
    return a === b ? 0 : a < b ? -1 : 1;
  });
  // Only change code above this line
}
console.log(alphabeticalOrder(["a", "d", "c", "a", "z", "g"]));
```



### **Return a Sorted Array Without Changing the Original Array**

A side effect of the `sort` method is that it changes the order of the elements in the original array. In other words, it mutates the array in place. One way to avoid this is to first concatenate an empty array to the one being sorted (remember that `slice` and `concat` return a new array), then run the `sort` method.

------

Use the `sort` method in the `nonMutatingSort` function to sort the elements of an array in ascending order. The function should return a new array, and not mutate the `globalArray` variable.

**Solution:**

```js
var globalArray = [5, 6, 3, 2, 9];
function nonMutatingSort(arr) {
  // Only change code below this line
  let myArr = arr.slice();
  myArr.sort(function(a, b) {
    return a === b ? 0 : a < b ? -1 : 1;
  });
  return myArr;
  // Only change code above this line
}
console.log(nonMutatingSort(globalArray));
```





### **Split a String into an Array Using the `split ` Method**

The `split` method splits a string into an array of strings. It takes an argument for the delimiter, which can be a character to use to break up the string or a regular expression. For example, if the delimiter is a space, you get an array of words, and if the delimiter is an empty string, you get an array of each character in the string.

Here are two examples that split one string by spaces, then another by digits using a regular expression:

```js
var str = "Hello World";
var bySpace = str.split(" ");

var otherString = "How9are7you2today";
var byDigits = otherString.split(/\d/);
```

`bySpace` would have the value `["Hello", "World"]` and `byDigits` would have the value `["How", "are", "you", "today"]`.

Since strings are immutable, the `split` method makes it easier to work with them.

------

Use the `split` method inside the `splitify` function to split `str` into an array of words. The function should return the array. Note that the words are not always separated by spaces, and the array should not contain punctuation.

**Solution:**

```js
function splitify(str) {
  // Only change code below this line
  return str.split(/\W/);

  // Only change code above this line
}
console.log(splitify("Hello World,I-am code"));
```



### **Combine an Array into a String Using the join Method**

The `join` method is used to join the elements of an array together to create a string. It takes an argument for the delimiter that is used to separate the array elements in the string.

Here's an example:

```js
var arr = ["Hello", "World"];
var str = arr.join(" ");
```

`str` would have a value of the string `Hello World`.

------

Use the `join` method (among others) inside the `sentensify` function to make a sentence from the words in the string `str`. The function should return a string. For example, `I-like-Star-Wars` would be converted to `I like Star Wars`. For this challenge, do not use the `replace` method.

**Solution:**

```js
function sentensify(str) {
  // Only change code below this line
  let myArr = str.split(/\W/);
  console.log(myArr)
  return myArr.join(" ");
  // Only change code above this line
}
console.log(sentensify("May-the-force-be-with-you"));
```





### **Apply Functional Programming to Convert Strings to URL Slugs**

The last several challenges covered a number of useful array and string methods that follow functional programming principles. We've also learned about `reduce`, which is a powerful method used to reduce problems to simpler forms. From computing averages to sorting, any array operation can be achieved by applying it. Recall that `map` and `filter` are special cases of `reduce`.

Let's combine what we've learned to solve a practical problem.

Many content management sites (CMS) have the titles of a post added to part of the URL for simple bookmarking purposes. For example, if you write a Medium post titled `Stop Using Reduce`, it's likely the URL would have some form of the title string in it (`.../stop-using-reduce`). You may have already noticed this on the freeCodeCamp site.

------

Fill in the `urlSlug` function so it converts a string `title` and returns the hyphenated version for the URL. You can use any of the methods covered in this section, and don't use `replace`. Here are the requirements:

The input is a string with spaces and title-cased words

The output is a string with the spaces between words replaced by a hyphen (`-`)

The output should be all lower-cased letters

The output should not have any spaces

**Solution:**

```js
// Only change code below this line
function urlSlug(title) {
return title
.toLowerCase()
.split(" ")
.filter(subStr => subStr !== "")
.join("-");  
}
// Only change code above this line
console.log(urlSlug(" Winter Is  Coming"));
```



### **Use the every Method to Check that Every Element in an Array Meets a Criteria**

The `every` method works with arrays to check if *every* element passes a particular test. It returns a Boolean value - `true` if all values meet the criteria, `false` if not.

For example, the following code would check if every element in the `numbers` array is less than 10:

```js
var numbers = [1, 5, 8, 0, 10, 11];
numbers.every(function(currentValue) {
  return currentValue < 10;
});
```

The `every` method would return `false` here.

------

Use the `every` method inside the `checkPositive` function to check if every element in `arr` is positive. The function should return a Boolean value.

**Soluation:**

```js
function checkPositive(arr) {
  // Only change code below this line
return arr.every(val => val >= 0);
  // Only change code above this line
}
checkPositive([1, 2, 3, -4, 5]);
```





### **Use the some Method to Check that Any Elements in an Array Meet a Criteria**

The `some` method works with arrays to check if *any* element passes a particular test. It returns a Boolean value - `true` if any of the values meet the criteria, `false` if not.

For example, the following code would check if any element in the `numbers` array is less than 10:

```js
var numbers = [10, 50, 8, 220, 110, 11];
numbers.some(function(currentValue) {
  return currentValue < 10;
});
```

The `some` method would return `true`.

------

Use the `some` method inside the `checkPositive` function to check if any element in `arr` is positive. The function should return a Boolean value.

**Soluation:**

```js
function checkPositive(arr) {
  // Only change code below this line
return arr.some(val => val >= 0);
  // Only change code above this line
}
checkPositive([1, 2, 3, -4, 5]);
```





### **Introduction to Currying and Partial Application**

The arity of a function is the number of arguments it requires. Currying a function means to convert a function of N arity into N functions of arity 1.

In other words, it restructures a function so it takes one argument, then returns another function that takes the next argument, and so on.

Here's an example:

```js
function unCurried(x, y) {
  return x + y;
}

function curried(x) {
  return function(y) {
    return x + y;
  }
}

const curried = x => y => x + y

curried(1)(2)
```

`curried(1)(2)` would return `3`.

This is useful in your program if you can't supply all the arguments to a function at one time. You can save each function call into a variable, which will hold the returned function reference that takes the next argument when it's available. Here's an example using the curried function in the example above:

```js
var funcForY = curried(1);
console.log(funcForY(2)); // 3
```

Similarly, partial application can be described as applying a few arguments to a function at a time and returning another function that is applied to more arguments. Here's an example:

```js
function impartial(x, y, z) {
  return x + y + z;
}
var partialFn = impartial.bind(this, 1, 2);
partialFn(10); // 13
```

------

Fill in the body of the `add` function so it uses currying to add parameters `x`, `y`, and `z`.

**Solution:**

```js
function add(x) {
  // Only change code below this line
  return function add(y) {
    return function add(z) {
      return x + y + z;
    }
  }
  // Only change code above this line
}
console.log(add(10)(20)(30));
```









# [Intermediate Algorithm Scripting](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#intermediate-algorithm-scripting)

Now that you know the basics of algorithmic thinking, along with OOP and Functional Programming, test your skills with the Intermediate Algorithm Scripting challenges.





### **Sum All Numbers in a Range**

We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. The lowest number will not always come first.

For example, `sumAll([4,1])` should return `10` because sum of all the numbers between 1 and 4 (both inclusive) is `10`.

**Soluation:**

```js
function sumAll(arr) {
  let myArr = arr.sort((a, b) => a -b);
  let result = 0;
  for(let i = myArr[0]; i <= myArr[1]; i++) {
    result += i;
  }
  return result;
}

sumAll([1, 4]);
```



### **Diff Two Arrays**

Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

**Note:** You can return the array with its elements in any order.

**Solution:**

```js
function diffArray(arr1, arr2) {
var newArr1 = [];
var newArr2 = [];

  //Looping through first array to find elements that don't exist in second array and 	   pushing the elements in separate array
  for(let i = 0; i < arr1.length; i++) {
    if(arr2.indexOf(arr1[i]) < 0) {
      newArr1.push(arr1[i]);
    }
  }


  //Looping through second array to find elements that don't exist in first array and 	   pushing the elements in separate array
  for(let j = 0; j < arr2.length; j++) {
    if(arr1.indexOf(arr2[j]) < 0) {
      newArr2.push(arr2[j]);
    }
  }

    
//returning the final array by concating seperated array
return newArr1.concat(newArr2);
}
console.log(diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]));
```



### **Wherefore art thou**

Make a function that looks through an array of objects (first argument) and returns an array of all objects that have matching name and value pairs (second argument). Each name and value pair of the source object has to be present in the object from the collection if it is to be included in the returned array.

For example, if the first argument is `[{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }]`, and the second argument is `{ last: "Capulet" }`, then you must return the third object from the array (the first argument), because it contains the name and its value, that was passed on as the second argument.

**Solution:**

```js
function whatIsInAName(collection, source) {
  var resultArr = [];
  //run a for loop for iterate trought the objects presnets in the arr
  
  for(let i = 0; i < collection.length; i++) {
      //on each iteration check whether the all value of sencond arg object is presnt in the object Array or not 

      let myObj = collection[i];
      let valPresent = true;

      for(let value in source) {
        if(myObj[value] !== source[value]) {
          valPresent = false;
        }
      }
      if(valPresent) {
        //if value is presnt, push the object in the result array
        resultArr.push(collection[i])
      }

  }
  return resultArr;
}
```



### **Spinal Tap Case**

Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.

Solution:

first method-

```js
function spinalCase(str) {
  
  //replace the "white spaces" and "under_scores" with "-"
  let myResult = str.replace(/\s|_/g, "-");
  

  //split the string followed by capltile letter
  let myArr = myResult.split(/(?=[A-Z])/);
 
    
  //join the arrays putting "-" between string, make it in lowercase and remove the repeted "-"
  let myFinalResult =  
   myArr.join("-")
  .toLowerCase()
  .replace(/(-)\1+/g, '$1');

  return myFinalResult;
}

console.log(spinalCase("The_Andy_Griffith_Show"))
```

optimized method-

```js
function spinalCase(str) {
  let myStr = str.split(/\s|_|(?=[A-Z])/)
  console.log(myStr)
  return myStr.join("-").toLowerCase();
}

console.log(spinalCase("Teletubbies say Eh-oh"))
```



### Pig latin

Pig Latin is a way of altering English Words. The rules are as follows:

\- If a word begins with a consonant, take the first consonant or consonant cluster, move it to the end of the word, and add `ay` to it.

\- If a word begins with a vowel, just add `way` at the end.

------

Translate the provided string to Pig Latin. Input strings are guaranteed to be English words in all lowercase.



Solution:

```js
function translatePigLatin(str) {
  //split the string after the first seen of vowels
  let myStr = str.split(/([aeiou].*)/).filter(word => word.length > 0);
  
  let myString = myStr.join();
  let myRegx = /[aeiou]/gi;
  
 
  let result = "";
  //IF array length is greater than zero, add the first index in the last of array last and retrun it as string + "ay";
  if(myStr.length > 1) {
    console.log(myStr.length)
    for(let i = myStr.length - 1; i >= 0; i--) {
      result += myStr[i]
    }
    result += "ay";
  } else if(myStr.length == 1 & myRegx.test(myString) === false) {
    return myStr.join("") + "ay";
  } //else, return the array as string + "way";
  else{
    return myStr.join("") + "way";
  }
  return result;
}

console.log(translatePigLatin("rhythm"));
```



### **Search and Replace**

Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

**Note:** Preserve the case of the first character in the original word when you are replacing it. For example if you mean to replace the word `Book` with the word `dog`, it should be replaced as `Dog`

**Solution:** 

```js
function myReplace(str, before, after) {
  let myBefore = before;
  let myAfter = after;
  let myFinalAfter = "";
  
  if(myBefore[0] == myBefore[0].toUpperCase()) {
    myFinalAfter = myAfter[0].toUpperCase();

    for(let i = 1; i < myAfter.length; i++) {
        myFinalAfter += myAfter[i];
    }
  } else if(myAfter[0] == myAfter[0].toUpperCase()) {
    myFinalAfter = myAfter[0].toLowerCase();

    for(let i = 1; i < myAfter.length; i++) {
        myFinalAfter += myAfter[i];
    }
  }
  
  if(before[0] == before[0].toUpperCase()) {
    return str.replace(myBefore,myFinalAfter); 
  } else if(after[0] == after[0].toUpperCase()) {
    return str.replace(myBefore,myFinalAfter); 
  }
  else {
    return str.replace(myBefore,myAfter);
  }
}


myReplace("His name is Tom", "Tom", "john");
```



### **DNA Pairing**

The DNA strand is missing the pairing element. Take each character, get its pair, and return the results as a 2d array.

[Base pairs](http://en.wikipedia.org/wiki/Base_pair) are a pair of AT and CG. Match the missing element to the provided character.

Return the provided character as the first element in each array.

For example, for the input `GCG`, return `[["G", "C"], ["C","G"], ["G", "C"]]`

The character and its pair are paired up in an array, and all the arrays are grouped into one encapsulating array.

```js
function pairElement(str) {
  let resultArr = [];
  //iterate throught the string
  for(let i = 0; i < str.length; i++) {
    console.log(str[i]);
  //pass the individual string is switch case 
    switch(str[i]) {
    //push the array in new balnk array for each value of string
      case "A":
        resultArr.push(["A","T"]);
        break;
      case "C":
        resultArr.push(["C","G"]);
        break;
      case "G":
        resultArr.push(["G","C"]);
        break;
      case "T":
        resultArr.push(["T","A"])
        break;
    }

  }
  //return the result array
  return resultArr;
}

console.log(pairElement("TTGAG"));
```



### **Missing letters**

Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return `undefined`.

```js
function fearNotLetter(str) {

  for(let i = 0; i < str.length; i++) {
    //take the char code of first word of string
    //compare it with nextchar code
    let diff = str.charCodeAt([i+1]) - str.charCodeAt([i]);
    //IF the difference is more than one 
    if(diff > 1) {
      //return the word between them
      return String.fromCharCode((str.charCodeAt([i])) + 1);
    }
  }
  return undefined;
}

console.log(fearNotLetter("abce"));
```



### **Sorted Union**

Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.

In other words, all values present from all arrays should be included in their original order, but with no duplicates in the final array.

The unique numbers should be sorted by their original order, but the final array should not be sorted in numerical order.

Check the assertion tests for examples.

```js
function uniteUnique(...arr) {
  let myArr = arr;

  //declear a blank arr
  let resultArr = [];
  //take the element from the array
  for(let i = 0; i < myArr.length; i++) {
    for(let j = 0; j < myArr[i].length; j++) {
      let myVal = myArr[i][j]; 
      //pusing the value if already not present in the array
      if(!resultArr.includes(myVal)) {
        resultArr.push(myArr[i][j]);
      }
    }
  }
  //returning the result array
  return resultArr;
}

console.log(uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]));
```



### **Convert HTML Entities**

Convert the characters `&`, `<`, `>`, `"` (double quote), and `'` (apostrophe), in a string to their corresponding HTML entities.

```js
function convertHTML(str) {
  let myArr = str.split("");
  //iterate through string
  for(let i = 0; i < myArr.length; i++) {
    //if found any special char than 
    switch(myArr[i]) {
	  //replace it with respected HTML entities
      case "&": 
        myArr[i] = "&amp;";
        break;
      case "<":
        myArr[i] = "&lt;";
        break;
      case ">":
        myArr[i] = "&gt;";
        break;
      case "\"":
        myArr[i] = "&quot;";
        break;
      case "\'":
        myArr[i] = "&apos;";
        break;
    }
  }
  //return the result string
  return myArr.join("");
}

console.log(convertHTML("Dolce & Gabbana"));
```



###  sum of all odd fibonacci numbers
Given a positive integer `num`, return the sum of all odd Fibonacci numbers that are less than or equal to `num`.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, `sumFibs(10)` should return `10` because all odd Fibonacci numbers less than or equal to `10` are 1, 1, 3, and 5.

Solution:

```js
function sumFibs(num) {
  //generate a array of fibonacci num for given no
  function fibo(n) {
    let baseVal = 1;
    let resultArr = [0];
    
    for(let i = 0; i < n; i++) {
      resultArr.push(baseVal + resultArr[i]);
      
      baseVal = resultArr[i];
    }
    return resultArr;
  }

  let fibNumArr = fibo(num);
  let result = 0;
  
  let myArr = fibNumArr.map(function(val) {
    if(val <= num & val % 2 != 0) {
      return result += val;
    }
  });

return result;
}

console.log(sumFibs(1000));
```



### sum all prims

**Sum All Primes**Passed

A prime number is a whole number greater than 1 with exactly two divisors: 1 and itself. For example, 2 is a prime number because it is only divisible by 1 and 2. In contrast, 4 is not prime since it is divisible by 1, 2 and 4.

Rewrite `sumPrimes` so it returns the sum of all prime numbers that are less than or equal to num.

```js
function sumPrimes(num) {
  let result = 0;
  //generate all the prime no
  function primeNum(num) {
    let val = [2];
    let counter = 0;
    
    for(let i = 3; i <= num; i++) {
      for(let j = 2; j <= num; j++) {
        if(i % j === 0) {
          counter++;
        }
      }
      if(counter < 2) {
        val.push(i);
      }
      counter = 0;
    }
    return val;
  }

  let primeValues = primeNum(num);
 
  //add all prime numbers
  for(let i = 0; i < primeValues.length; i++) {
    result += primeValues[i]
  }

  //return the resulr value
  return result;

}

console.log(sumPrimes(977));
```



### **Smallest Common Multiple**

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

For example, if given 1 and 3, find the smallest common multiple of both 1 and 3 that is also evenly divisible by all numbers *between* 1 and 3. The answer here would be 6.

```js
// LCM of all numbers in the range of arr=[a, b] 
  function smallestCommons(arr) {
    let myArr = arr.slice(); 
    // Swap [big, small] to [small, big]
    if(myArr[0] > myArr[1]) {
      (myArr = [myArr[1], myArr[0]]);
    }

    let result = myArr[0];
    
    // Euclid algorithm for Greates Common Divisor
    function gcd(a, b) {
      if(!b) {
        return a;
      } else {
        return gcd(b, a%b);
      }
    }

    // Least Common Multiple function
    function lcm(a, b) {
      return (a * b) / gcd(a,b);
    }

    for(let x = result; x <= myArr[1]; x++) {
      result = lcm(x, result);
    }

    return result;
  }
```



### **Drop it**

Given the array `arr`, iterate through and remove each element starting from the first element (the 0 index) until the function `func` returns `true` when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, `arr` should be returned as an empty array.

```js
function dropElements(arr, func) {
  let resultArr = [];
  //iterate through the array
  for(let  i = 0; i < arr.length; i++) {
  //pass the iterated array value in function
  let funReturn = func(arr[i]);
  //if it's returns true 
  if(funReturn) {
    //push the left array value in result arr
    for(let j = i; j < arr.length; j++) {
        resultArr.push(arr[j])
      }
    break;
    }
  }
  //return the result arr
  return resultArr;
}

console.log(dropElements([1, 2, 3, 7, 4], function(n) {return n > 3;}));
```



### **Steamroller**

Flatten a nested array. You must account for varying levels of nesting.

```js
function steamrollArray(arr) {
  let resultArr = [];
  function flatten(myArr) {
    myArr.forEach((val) => {
      if(!Array.isArray(val)) {
        resultArr.push(val);
      } else {
        flatten(val);
      }
    })
  }

  flatten(arr);
  return resultArr;
}
steamrollArray([1, [2], [3, [[4]]]]);
```



### **Binary Agents**

Return an English translated sentence of the passed binary string.

The binary string will be space separated.

```js
function binaryAgent(str) {
  let myStrArr = str.split(" ");
  let result = "";

  for (let i = 0; i < myStrArr.length; i++) {
    switch (myStrArr[i]) {
      //for capital letter

      case "01000001":
        result += "A";
        break;

      case "01000010":
        result += "B";
        break;

      case "01000011":
        result += "C";
        break;

      case "01000100":
        result += "D";
        break;

      case "01000101":
        result += "E";
        break;

      case "01000110":
        result += "F";
        break;

      case "01000111":
        result += "G";
        break;

      case "01001000":
        result += "H";
        break;

      case "01001001":
        result += "I";
        break;

      case "01001010":
        result += "J";
        break;

      case "01001011":
        result += "K";
        break;

      case "01001100":
        result += "L";
        break;

      case "01001101":
        result += "M";
        break;

      case "01001110":
        result += "N";
        break;

      case "01001111":
        result += "O";
        break;

      case "01010000":
        result += "P";
        break;

      case "01010001":
        result += "Q";
        break;

      case "01010010":
        result += "R";
        break;

      case "01010011":
        result += "s";
        break;

      case "01010100":
        result += "T";
        break;

      case "01010101":
        result += "U";
        break;

      case "01010110":
        result += "V";
        break;

      case "01010111":
        result += "W";
        break;

      case "01011000":
        result += "X";
        break;

      case "01011001":
        result += "Y";
        break;

      case "01011010":
        result += "Z";
        break;

      //for small letter

      case "01100001":
        result += "a";
        break;

      case "01100010":
        result += "b";
        break;

      case "01100011":
        result += "c";
        break;

      case "01100100":
        result += "d";
        break;

      case "01100101":
        result += "e";
        break;

      case "01100110":
        result += "f";
        break;

      case "01100111":
        result += "g";
        break;

      case "01101000":
        result += "h";
        break;

      case "01101001":
        result += "i";
        break;

      case "01101010":
        result += "j";
        break;

      case "01101011":
        result += "k";
        break;

      case "01101100":
        result += "l";
        break;

      case "01101101":
        result += "m";
        break;

      case "01101110":
        result += "n";
        break;

      case "01101111":
        result += "o";
        break;

      case "01110000":
        result += "p";
        break;

      case "01110001":
        result += "q";
        break;

      case "01110010":
        result += "r";
        break;

      case "01110011":
        result += "s";
        break;

      case "01110100":
        result += "t";
        break;

      case "01110101":
        result += "u";
        break;

      case "01110110":
        result += "v";
        break;

      case "01110111":
        result += "w";
        break;

      case "01111000":
        result += "x";
        break;

      case "01111001":
        result += "y";
        break;

      case "01111010":
        result += "z";
        break;

      //special charecters

      case "00111111":
        result += "?";
        break;

      case "00100001":
        result += "!";
        break;

      case "00100111":
        result += "'";
        break;

      case "00100000":
        result += " ";
        break;
    }
  }
  return result;
}

```

second method:

```js
function binaryAgent(str) {
  let myStrArr = str.split(" ");
  let result = "";

  /*using the radix (or base) parameter in parseInt, we can convert the binary
      number to a decimal number while simultaneously converting to a char*/

  for (var i = 0; i < myStrArr.length; i++) {
    let decVal = parseInt(myStrArr[i], 2);
    result += String.fromCharCode(decVal);
  }

  // we then simply return the result string
  return result;
}
```

