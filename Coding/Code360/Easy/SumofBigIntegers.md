**_*Try to solve by yourself*_** before reading this https://www.naukri.com/code360/problems/sum-of-big-integers_1229068 <br />( Recommended )

&emsp;&emsp; Hello guys, Welcome here. Today we are going to look at the problem involving BigIntegers, and solve it. Let's don't waste time and get into the problem right away.

*_**Problem Statement:**_*

&emsp;&emsp; You have been given two integers ‘NUM1’ and ‘NUM2’ as a string. Your task is to print the sum of both the numbers.



*_**Understanding the Problem:**_*

&emsp;&emsp; We just need to code the function not the entire input and output stuff they are already taken care of by coding360. now we were given a function named **findSum** with two string passed as parameters.
Those string are only numbers.

**Step 1:** First we need to convert the string into Big Integer so we can do the *_**sum**_* operation on the given two numbers. <br />

**Step 2:** After performing addition convert the Big Integer back into ***String***.<br />

**Step 3:** Return the string.

These steps seems simple and easy. Let's dive into the coding part.

### Solution:
```java
	public static String findSum(String num1 , String num2)  {
		// Write your code here.
		BigInteger n1 = new BigInteger(num1);
		BigInteger n2 = new BigInteger(num2);
		BigInteger sum = n1.add(n2);
		return sum.toString();
	}
```

### Explanation:<br />
&emsp;&emsp; ***First Line:*** `BigInteger n1 = new BigInteger(num1);` Here we are just creating a **BigInteger** variable named n1 with the value of ***num1*** string.This is just the classic variable creation in C like `int a = 10;` nothing special. Don't get intimidated if you are new to this. Why i'm saying this is because i got so don't worry you'll get used to it in time.<br />

&emsp;&emsp; ***Second Line:*** `BigInteger n2 = new BigInteger(num2);`Here we are creating another BigInteger variable named n2.<br />

&emsp;&emsp; ***Third Line:*** `BigInteger sum = n1.add(n2)` This literally adds two numbers and save it to the sum variable just like we do it in C `int sum = 10 + 20;`. But we can't use the classic `n1 + n2` addition here, it won't work. How do i know because i tried it ಠ◡ಠ.<br />

&emsp;&emsp; ***Fourth Line:*** `return sum.toString();` This line returns the value of sum after converting the BigInteger into String. Why convert the BigInteger to string, so much waste of time. Because the return type of the function is string `public static String findSum(String num1 , String num2)`.<br />



### Personal Experience:

&emsp;&emsp; My experiecnce with this problem is bad like really really bad. I don't know what to do in mid way and about to give up, but you gotta keep going otherwise you learn nothing and finished this problem. At first submission of this code, This code is placed 119 th place in the participants and **I AM PROUD OF IT**.

&emsp;&emsp; At first glance after reading the problem I thought, well this was an absolute garbage question to ask it's so easy and simple Let me finish the code in 50 seconds. After some coding later an error has been thrown at my face, it describes ***" You can't return an integer from a string function. "*** I got a little confused, disappointed and a little dumb (⊙_☉). Now after converting my answer from int to string and submit again with much confidence and it ran successfully YAY!!!, But it failed the test case. The test case contained some pretty big numbers, I used **int** datatype to store some 20 digit number can you believe it a 20 digit number in the test case, I got shocked, disappointed and even dumber ╭( ๐_๐)╮, it was a pretty bad experience to be honest. 

&emsp;&emsp; I didn't know what datatype to use here I only know the highest integer storing datatype as **Long**, But it also betrayed me now i got depression and my remaining hope left me (--_--). Well after saying this all to **chatGPT** and got to know about BigIntegers it went well and i finished my problem and i was happy (◠‿◠), Don't be ashamed to turn your face to the experienced guy. But i gotta admit that converting the string to integers and BigIntegers and converting them back to string is a tough job to do （ー○ー). Now I feel like **" I have lifted some mountain. "**.

&emsp;&emsp; This is my experience with this easy problem. After this problem i got to know about the BigIntegers and conversion of string to int, BigInteger and converting int, BigInteger to string. I hope this small problem will help you in some way and if your experience is related to mine here is some hug for you ⊂((・▽・))⊃ .

### I know this is not the right approach for this problem and it may not be the correct solution, But it works and I am proud of it and you should be proud of yourself to be reading this and learing yourself, Bye and meet you next time with another problem.
