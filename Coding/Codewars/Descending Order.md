**Try to solve by yourself** before reading this https://www.codewars.com/kata/5467e4d82edf8bbf40000155

&emsp;&emsp; Hello guys, Welcome here. Today we are going to look at the problem named descending order, and solve it. Let's don't waste time and get into the problem right away.

**Problem Statement:**

&emsp;&emsp; Your task is to make a function that can take any non-negative integer as an argument and return it with its digits in descending order. Essentially, rearrange the digits to create the highest possible number.

**Understanding the Problem:**

&emsp;&emsp; We just need to code the function not the entire input and output stuff they are already taken care of by codewars. We were given a function named DescendingOrder with an integer passed as a parameters like 123456789.
We need to reverse the number and make it the ***highest possible number*** like 987654321. How do we do this? Oh man I am F****d. That's just a joke nevermind, Here is how we are doing this.

**For every problem Breakdown the problem into smaller problems.**

**Step 1:** First we nned to convert the number into an array and store each digits in each index of the array.

**Step 2:** Sort the array in descending order, Well thats what they asked.

**Step 3:** Convert the sorted array into an integer. YAY!!! We solved it.

These are the steps we are going to follow, Let's look at the code now.

## Solution:

```java
import java.util.ArrayList;
import java.util.Collections;

public class DescendingOrder {
  public static int sortDesc(final int num) {
    //Your code
    //Step 1: separate numbers and store it in dynamic array
    ArrayList<Integer> n = new ArrayList<Integer>(); // Dynamic array to store digits of num
    int copy = num, temp = 0, res = 0;
    while (copy > 0) {
      temp = copy % 10;
      n.add(temp);
      copy /= 10;
    }
    
    //Step 2: sort the array in descending order
    Collections.sort(n, Collections.reverseOrder());
    
    //Step 3: convert the array into integer
    int size = n.size();
    for (int i=0, j=size; i<size; i++, --j) {
      res = res + n.get(i) * (int) Math.pow(10, j-1);
    }
    
    return res;
    
  }
}
```

### Explanation:

&emsp;&emsp; It looks like a pretty big problem to explain so I'm going to separate it into well steps? or modules? I don't know &emsp;&emsp; ¯¯\_(⊙_☉)_/¯¯ Let's get into it.

&emsp;&emsp; ***Imports:*** 
```java
import java.util.ArrayList;
import java.util.Collections;
```
Here we are importing two classes named ArrayList and Collections within the util package. The **ArrayList** is imported inorder to create arraylist, why arraylist we already have arrays. Well we can't create an empty array and specify it's size later, if we do that 
it definitely give you an array, but we need an array that need to be change every time the value of **num** changes. Inorder to achieve this functionality we use the arraylist, In arraylist we can easily declare an empty arraylist and start adding elements because it's an 
dynamic array it can increase and decrease it's size accordingly.

Well the **Collections** class is for sorting the arraylist in descending order, That's all.

&emsp;&emsp; ***Step 1:***

```java
    //Step 1: separate numbers and store it in dynamic array
    ArrayList<Integer> n = new ArrayList<Integer>(); // Dynamic array to store digits of num
    int copy = num, temp = 0, res = 0;
    while (copy > 0) {
      temp = copy % 10;
      n.add(temp);
      copy /= 10;
    }
```
`ArrayList<Integer> n = new ArrayList<Integer>();` is just creating an empty arraylist. We use arraylist, because the num parameter in `sortDesc(final int num)` is never going to be constant.<br />

`int copy = num, temp = 0, res = 0;` Here declaring some bunch of integers we need later on. `int copy = num,` Why we copy the value of num into a variable?, Because there is a final keyword in the parameter `sortDesc(final int num)` if we even try to change the value of num the compiler will spam you with error you don't even know off.<br />

What is going on in the while loop?.....(⚆ᗝ⚆). First we are separating last digit from the given number and store it to temp variable in &emsp;&emsp;&emsp; `temp = copy % 10;`. Now we are adding the digit in temp to the arraylist in `n.add(temp);`. Now we are eliminating the last digit in the number in `copy /= 10;`. The while loop will run until the number becomes zero, so 
each and every number will be stripped don't worry.

Let's do the calculation here, I will give some calculations for it like 2 loop examples for better understanding the loop function.

```
Iteration 1:
Assume num = 4352,
Variables and their values: copy = 4352, temp = 0, n = {}
Conditions and their states: ( copy > 0 ) ==> ( 4352 > 0 ) ==> True
      temp = ( copy % 10 ) ==> ( 4352 % 10 ) ==> 2
      n = {} ==> {2}
      copy = ( 4352 / 10 ) ==> 435

Iteration 2:
Variables and their values: copy = 435, temp = 2, n = {2}
Conditions and their states: ( copy > 0 ) ==> ( 435 > 0 ) ==> True
      temp = ( copy % 10 ) ==> ( 435 % 10 ) ==> 5
      n = {2} ==> {2, 5}
      copy = ( 435 / 10 ) ==> 43
```

&emsp;&emsp; ***Step 2:***

```java
    //Step 2: sort the array in descending order
    Collections.sort(n, Collections.reverseOrder());
```
This step is having the honor of the easiest step in the problem. We are just calling the sort function and inside this function we are calling the reverseOrder function from collections. This will pretty much sort the arraylit in descending order. After sorting the n will become &emsp;&emsp;&emsp;&emsp;&emsp;`n = {5, 4, 3, 2}`.

&emsp;&emsp; ***Step 3:***

```java

    //Step 3: convert the array into integer
    int size = n.size();
    for (int i=0, j=size; i<size; i++, --j) {
      res = res + n.get(i) * (int) Math.pow(10, j-1);
    }
```
`int size = n.size();` just storing the size of the arraylist in size variable.<br />

`for (int i=0, j=size; i<size; i++, --j)` in this for loop we are having two variable declarations and two increment or decrement operations ___This is f*****g illeagal ╭(* _ *)╮.___ No this is completely valid.

`res = res + n.get(i) * (int) Math.pow(10, j-1);` here is the tricky part. First we are getting the **ith** element from the arraylist in `n.get(i)`. Second we are getting the power of 10 in (size - 1) in `(int) Math.pow(10, j-1)`. Then multiply it and add it to the res, we are done.

Let's do the calculation here, I will give some calculations for it like 2 loop examples for better understanding the loop function.
```
Iteration 1:
Assume size = 4, n = { 5,4,3,2 }                                // we need to make res have value of 5432 is our mission
variables and their values: i = 0, j = 4, res = 0               // res was declared in the first step 
conditions and their states: (i < size) ==> ( 0 < 4 ) ==> True
calculation:
      res = 0 + 5 * ( 10 raise to the power of 3 )
      res = 0 + 5 * ( 1000 )
      res = 0 + 5000
      res = 5000

Iteration 2:
variables and their values: i = 1, j = 3, res = 5000           // after the iteration 1 
conditions and their states: (i < size) ==> ( 1 < 4 ) ==> True
calculation:
      res = 5000 + 4 * ( 10 raise to the power of 2 )
      res = 5000 + 4 * 100
      res = 5000 + 400
      res = 5400
```
Now return the res. That's it, **MISSION COMPLETED** ***+5 respect***

### Personal Experience:

&emsp;&emsp; My experience with this problem is mind f**k, heart warming and here comes the ***depression***. At first glance I divided the problems into the smaller problems. Now I know what to, at first I also tries the empty array declaration and found that it is not possible after getting some errors on my face (--_--). After that I researched some way to declare an empty array and how to use it that's how I came to know about the **ArrayList**. Even after founding the way i had some initial difficulties as we need to import the classes and I didn't know the names. First step is finished, it was a good experience ヽ(•‿•)ノ.

&emsp;&emsp; The second step is just easy, I used chatGPT to know about the function names and the implementation of it and I need to say it present to you like it was simple as a oneliner but it was tough to use it on code.

&emsp;&emsp; Now this is the step **I am completely PROUD**. For this I really got my hands dirty on algorithms, I really calculated the calculations and after completion I felt really really happy about it. It felt like I can literally do anything on this world (⌒_⌒). Well i know that's just not possible, but I was so satisfied with it and I felt proud of myself and my confidence got skyrocketed. For some time, after that I got to know there is someone who finished this task in just three lines, **JUST THREE LINES** can you imagine it. Here is the code see for yourself
```java
import java.util.Arrays;
import java.util.Collections;

public class DescendingOrder {
    public static int sortDesc(final int num) {
        String[] array = String.valueOf(num).split("");
        Arrays.sort(array, Collections.reverseOrder());
        return Integer.valueOf(String.join("", array));
    }
}
```

&emsp;&emsp; After seeing this I got humbled and my big head blasted. Now I'm back to my depressed state and everything is back to normal. Now I feel like my code is best and i don't care what others say in this. Maybe in the future I may feel like **Damn I'm so dumb in the past** as i will be better in the future than my current state. That's pretty much it see you in next problem.
