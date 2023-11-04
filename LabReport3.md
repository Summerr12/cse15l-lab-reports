## Benjamin Nhan, 
## CSE15L
## Lab Report 3
## Week 4
---
## P1
Provide:

**A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)**

```
	@Test 
	public void testReverseInPlaceBetterTest() {
    int[] inputT2 = { 2,4,6,8,10,12 };
    ArrayExamples.reverseInPlace(inputT2);
    assertArrayEquals(new int[]{12,10,8,6,4,2}, inputT2);
	}

```


**An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)**

```
	@Test 
	public void testReverseInPlaceAlwaysRightButWrong() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

**The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)**
![Image](p3inputR3.png)

**The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.**

```
  //before/old version of reverseInPlace
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

```
  //new version of reverseInPlace
  static void reverseInPlace(int[] arr) {
    int[] test = new int[arr.length];

    for(int i = 0; i < arr.length; i += 1) {
      test[i] = arr[arr.length - i-1];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = test[i];
    }
  }
```
The issue with the code was because when we would try to move the value at the right end of the array to the left, it would replace the values of the same array we were taking from. This is very wrong so to fix it, I made a temporary test array and moved the reverse in another array. Therefore the values didn't clash and I made another for loop to move the correct values from the temp array into the formal one. The error can be seen in the output where they expeceted a 6 but saw a 8 because the next iteration after the half, the right end of the values never got swapped.

## P2
