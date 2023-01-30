# Lab Report 3

---

## Part 1

### Code for StringServer
![image](https://user-images.githubusercontent.com/114371214/215438771-640d4327-46b2-4f61-a696-c29ed39c8fe8.png)

The code above shows the implementation of a web server called "StringServer." The state of the server is a string that gets concatenated to by incoming requests. The StringHandler class implements the URLHandler interface, and provides the logic for handling HTTP requests. It has a single instance variable loadingString which is initially an empty string. Requests are recieved through `handleRequest` which checks if the request path is `/add-message`. If it is, then it splits the query of the request into a String array and checks if the initial element is "s." If it is "s, it proceeds to concatenate "\n" and the value of the second element of `paramenters` array to `loadingString`. Finally, the method returns the `loadingString` as the output of the method. 


---
### Example 1: /add-message?s=Hello
![image](https://user-images.githubusercontent.com/114371214/215437572-bcc9bcaf-4780-4089-8b2c-576d707e2635.png)


To note, the example above shows the page being loaded an additional 3 times, producing four "Hello" Strings on four seperate lines. Example 1 calls the method `handleRequest` with the String argument for the request being `/add-message?s=Hello`. The program splits the query at **=** and the second element of the array is further concatenated to `runningString`, subsequent to a newline character produced. `loadingString` is then returned producing the output of `\nHello`. 

---
### Example 2: /add-message?s=How are you__
![image](https://user-images.githubusercontent.com/114371214/215438110-808e5e87-0878-4079-8c26-0b35a50660df.png)

Similarly, example 2 calls the `handleRequest` method using the argument `/add-message?s=How are you`. The method is called with the argument of the `url`, with the argument being `/add-message?s=How are you,` which is further split on `=` where the second element of the array is concatenated to `loadingString`. `loadingString` is returned producing the output of `\nHow are you`, as shown on the fifth line of the example


---

## Part 2
### A failure-inducing input for the buggy program

```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {1, 2, 3, 4, 5}
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] ({5,4,3,2,1}, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = {1, 2, 3, 4, 5};
    assertArrayEquals(new int[]{1, 2, 3, 4, 5}, ArrayExamples.reversed(input1));
  }
}

```

In this example, two JUnit tests are written to test the two methods "reverseInPlace" and "reversed". The "testReverseInPlace" checks if the input array is correctly reversed in place and the "testReversed" checks if a new array with the reversed elements is returned. In both tests, the input array is {1, 2, 3, 4, 5} and the expected output is {5, 4, 3, 2, 1}. The assertArrayEquals method compares the expected and actual arrays, and will fail if they do not match. However, the first method "reverseInPlace" has a bug. It will only partially reverse the elements in the array, resulting in a buggy output. This is because the assignment `arr[i] = arr[arr.length - i - 1];>` does not swap the elements, but rather overwrites the first half of the array with the second half.

The second method "reversed" also has a bug where it returns the input array, which was not reversed, but rather overwritten with the values from the newly created array "newArray". To fix the bug, the return will need to be changed to "newArray" instead of "arr".

---
### An input that doesn’t induce a failure

```
{
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
}


```
The JUnit tests in the previous code block don't induce a failure because the input arrays {1} and {} are edge cases with a length of 1 and 0, respectively. The faulty reverseInPlace method uses the same array for input and output, so for an input array of length 1, it does not perform any modifications.

Similarly, the faulty reversed method returns the input array, so for an input array of length 0, it returns the same array without performing any modifications.

These specific inputs happen to not induce a failure in the faulty code, but the code is still incorrect for any other inputs that have a length greater than 1.

### The symptom, as the output of running the tests
#### JUnit Example: Running a failure-inducing input
![image](https://user-images.githubusercontent.com/114371214/215448366-99a69c04-cd90-4a1d-90ce-6ad43fbbe37e.png)

#### JUnit Example: Running input that doesn't induce a failure
![image](https://user-images.githubusercontent.com/114371214/215444678-cad667c5-9b57-4797-bb03-ee78784fc9f9.png)



### The bug, as the before-and-after code change required to fix it
#### The before
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

#### The after

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
}

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```


#### Explanation of bug and the fix 

In the first method "reverseInPlace", the bug was that it was overwriting the elements of the input array with the same value several times, leading to faulty outputs. The fix involved updating the assignment statement to correctly swap the elements by using the value from the end of the array instead of from the start.

The issue with the "reversed" method is that it was returning the original input array instead of a new array with reversed elements. The original line of code `arr[i] = newArray[arr.length - i - 1];` was incorrect, as it was modifying the original arr instead of the newArray. The corrected line is `newArray[i] = arr[arr.length - i - 1];`, which ensures the correct reverse of elements in the array. 

---

## Part 3
### Describe something you learned from lab in week 2 or 3 that you didn’t know before.
During the Week 2's Lab, I watched a tutorial that explains the steps for cloning a repository from Github to your local computer using Github Desktop and further was able to apply and use this information to create my own repository. Additionally, I learned about the concept of URLHandler interface, which is used to process URLs in web servers, and provides a link to a sample web server implementation. I was also able to play around with a class called Server, which is used to start the web server with a specified port and URLHandler. The lab explains how to build and run the server using javac and java commands and shows the expected output when the server is started successfully. All of these aforementioned, are key conceps from the lab that I wasn't familiar with earlier, but gained a thorough understanding on to the extent that I was able to successfully apply them.


![image](https://user-images.githubusercontent.com/114371214/215430627-b1141f6f-dc14-4e60-bdca-05c6a86e625a.png)

