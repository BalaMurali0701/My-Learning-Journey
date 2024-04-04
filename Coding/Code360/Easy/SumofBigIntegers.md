**_*Try to solve by yourself*_** before reading this https://www.naukri.com/code360/problems/sum-of-big-integers_1229068 <br />( Recommended )

&emsp;&emsp; Hello guys, Welcome here. Today we are going to look at the problem involving BigIntegers, and solve it using c++, Java, and python. Let's don't waste time and get into the problem right away.

*_**Problem Statement:**_*

&emsp;&emsp; You have been given two integers ‘NUM1’ and ‘NUM2’ as a string. Your task is to print the sum of both the numbers.



*_**Understanding the Problem:**_*

&emsp;&emsp; We just need to code the function not the entire input and output stuff they are already taken care of by coding360. now we were given a function named **findSum** with two string passed as parameters.
Those string are only numbers.

**Step 1:** First we need to convert the string into Big Integer so we can do the *_**sum**_* operation on the given two numbers. <br />

**Step 2:** After performing addition convert the Big Integer back into ***String***.<br />

**Step 3:** Return the string.

These steps seems simple and easy. Let's dive into the coding part.

**Solution:**
```java
	public static String findSum(String num1 , String num2)  {
		// Write your code here.
		BigInteger n1 = new BigInteger(num1);
		BigInteger n2 = new BigInteger(num2);
		BigInteger sum = n1.add(n2);
		return sum.toString();
	}
```

**Explanation:**<br />
&emsp;&emsp; ***First Line:*** `BigInteger n1 = new BigInteger(num1);` Here we are just creating a **BigInteger** variable named n1 with the value of ***num1*** string.This is just the classic variable creation in C like `int a = 10;` nothing special. Don't get intimidated if you are new to this. Why i'm saying this is because i got so don't worry you'll get used to it in time.<br />

&emsp;&emsp; ***Second Line:*** `BigInteger n2 = new BigInteger(num2);`Here we are creating another BigInteger variable named n2.<br />

&emsp;&emsp; ***Third Line:*** `BigInteger sum = n1.add(n2)` This literally adds two numbers and save it to the sum variable just like we do it in C `int sum = 10 + 20;`. But we can't use the classic `n1 + n2` addition here, it won't work. How do i know because i tried it ಠ◡ಠ.<br />

&emsp;&emsp; ***Fourth Line:*** `return sum.toString();` This line returns the value of sum after converting the BigInteger into String. Why convert the BigInteger to string, so much waste of time. Because the return type of the function is string `public static String findSum(String num1 , String num2)`.<br />
