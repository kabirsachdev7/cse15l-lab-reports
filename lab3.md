# Lab Report 3
## Part 1


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

In this example, two JUnit tests are written to test the two methods "reverseInPlace" and "reversed". The "testReverseInPlace" checks if the input array is correctly reversed in place and the "testReversed" checks if a new array with the reversed elements is returned. In both tests, the input array is {1, 2, 3, 4, 5} and the expected output is {5, 4, 3, 2, 1}. The assertArrayEquals method compares the expected and actual arrays, and will fail if they do not match. However, the first method "reverseInPlace" has a bug. It will only partially reverse the elements in the array, resulting in a buggy output. This is because the assignment arr[i] = arr[arr.length - i - 1]; does not swap the elements, but rather overwrites the first half of the array with the second half.

The second method "reversed" also has a bug. It returns the input array, which was not reversed, but rather overwritten with the values from the newly created array "newArray". To fix the bug, return "newArray" instead of "arr".

```
{
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {1;
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


## Part 3
