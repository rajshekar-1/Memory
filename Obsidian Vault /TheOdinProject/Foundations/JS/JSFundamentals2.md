[[TheOdinProject/Foundations/JS/]]

### 8 data types in JavaScript 
- seven primitive data types:
1. number for numbers of any kind: integer or floating-point, integers are limited by ±(253-1).
2. bigint for integer numbers of arbitrary length.
3. string for strings. A string may have zero or more characters, there’s no separate single-character type.
4. boolean for true/false.
5. null for unknown values – a standalone type that has a single value null.
6. undefined for unassigned values – a standalone type that has a single value undefined.
7. symbol for unique identifiers.

- And one non-primitive data type:
8. object for more complex data structures.

- Object data types basically store complex data structures. so they are called 'Non Primitive'


#### What is null and undefined 

   Null is a value that you can assign to variable. Null is a value that exists so it isnt a null pointer or 
         Non existing value like in other languages

   Undefined means the variables value has not been assigned.

- single and doublw Quotes both work same. You use double quotes if you want single quotes inside a string and vice versa.

- backticks are called template literal. This allows you to use variables inside the string 

- Embeding variables in string is called  concatenation context.

- Backticks allow you to embed variables in a string

- You escape characters in a string with backslash '\''



### Note
			JavaScript counts positions from zero.
			
			First position is 0.
			
			Second position is 1.
			


<br/> <br/>
- JavaScript String slice()
slice() extracts a part of a string and returns the extracted part in a new string.

Slice out a portion of a string from position 7 to position 13 (13 not included):

```
let str = "Apple, Banana, Kiwi";
let part = str.slice(7, 13);
```


<br/> <br/>
- JavaScript String substring()
substring() is similar to slice().

The difference is that start and end values less than 0 are treated as 0 in substring().


Example
```
let str = "Apple, Banana, Kiwi";
let part = str.substring(7, 13);
```



<br/> <br/>
- JavaScript String substr()
substr() is similar to slice().

The difference is that the second parameter specifies the length of the extracted part.

Example
```
let str = "Apple, Banana, Kiwi";
let part = str.substr(7, 6);
```




<br/> <br/> <br/> <br/>
- AND (&) , OR (||) , NOT (!) - are 3 logical operators.
- = , == , === are comparison operators.

- The if (…) statement evaluates the expression in its parentheses and converts the result to a boolean.

>Let’s recall the conversion rules from the chapter Type Conversions: A number 0, an empty string "", null, undefined, and NaN all become false. Because of that they are called “falsy” values.
Other values become true, so they are called “truthy”.


### Conditionals


- if, else and else if


	if 
	```javascript
	if (condition) {
	  /* code to run if condition is true */
	} else if {
	  /* run some other code instead */
	}else {
		/* run some other code instead */
	}
	```


- switch statements
```javascript
	switch (expression) {
  case choice1:
   /** run this code **/
    break;

  case choice2:
   /**  run this code instead **/
    break;

  // include as many cases as you like

  default:
    /** actually, just run this code **/
}
```

- '?' - Ternary operator.
	This is like one liner for if statements
	condition ? run this code : run this code instead
	
	```Javascript
	const greet = isBirthday ? "Happy Birthday" : "Good Morning";
	```


### Nesting 

{ Main
	{
	Nested 1
	}
	{
	Nested 2 {
		Nested 2.1
		}
	}
}