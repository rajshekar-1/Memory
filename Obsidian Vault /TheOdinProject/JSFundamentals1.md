# Fundamentals 1

- 3 ways to make variables
	- let - modern latest method
	- var - older 
	- const 


- You should avoid var cause it has wierd behaviours. 
- Rules to naming variables
	- CamelCase for readability
	- Avoid reserved words.
        - let, class, return, and function are reserved.
    - $ and _ can be used in names
    - Dont start with numbers
    - case sensitive so apple != APPLE
    - Non latin letters are allowed but not best practice
	- declare variables explicitly before using. you can use variables without declaring but that will give you errors.

-  so the + sign is wierd in JS 
	- it can be used to add number/integers
	- it can be usd to concatenate strings
	- You can add a string "10" and int 10
		
		``` javascript
		let a = "10", b = 10, c = a+b;
		console.log(c)
		``` 
		This will work and print 20 
	``` javascript
		let apples = "2";
		let oranges = "3";
		
		alert( apples + oranges ); // "23", the binary plus concatenates strings
		
		// both values converted to numbers before the binary plus
		alert( +apples + +oranges ); // 5
	```

- The % operator return the remainder after divison
	- `8 % 3 = 2`

- = & == & === 
	- = assigns value. `a = 10` 
	- == : The equality test - checks if both the values match and returns true or false.
	```javascript
		let a = 10;
		let b = 11;
		alert( 2 == 1 ); // false (wrong)
	```
	
	 
	 - A regular equality check == has a problem. It cannot differentiate 0 from false.
	
	``` javascript 
		alert( 0 == false ); // true
		alert( '' == false ); // true
	```
	
	 
	 - == equality operator converts operands of different type to numbers. So empty string gets converted to number 0. 
	- === - called strict equality operator fixes this. no conversions here. 

- what happens when you add a number to string or do math on non integers - you get `NaN` as result.

### ++/-- is used to increase or decrease a variables value.

- If the result of increment/decrement is not used, there is no difference in which form to use:
	
	```javascript
	let counter = 0;
	counter++;
	++counter;
	alert( counter ); // 2, the lines above did the same
	```
- If we’d like to increase a value and immediately use the result of the operator, we need the prefix form:

	```javascript
	let counter = 0;
	alert( ++counter ); // 1
	```

- If we’d like to increment a value but use its previous value, we need the postfix form:
	```javascript
	let counter = 0;
	alert( counter++ ); // 0
	```

- Operator precedence = BODMAS rule in javascript math

- ctrl + shift + I or C - gives you developer tools and console on chrome

- console.log() Logs information on the console. 

#### Unary `+` 
 - converts binary variabes to numbers. 
	 ```javascript
	 // No effect on numbers
	let x = 1;
	alert( +x ); // 1
	
	let y = -2;
	alert( +y ); // -2
	
	// Converts non-numbers
	alert( +true ); // 1
	alert( +"" );   // 0
	```

