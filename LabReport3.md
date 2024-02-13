# LabReport3

## Part 1 - Bugs
- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown):
  ```
  @Test
  public void LongArrayTestReversed() {
    int[] input1 = {1,2,3,4,5};
    int[] input = ArrayExamples.reversed(input1);
    assertArrayEquals(new int[]{5,4,3,2,1}, input);
  }
  ```
- An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown):
  ```
  @Test
  public void LongArrayTestReversed1() {
    int[] input1 = {0};
    int[] input = ArrayExamples.reversed(input1);
    assertArrayEquals(new int[]{0}, input);
  }
  ```
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above):
  ![img](1.png)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown):
  before:
  ```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```
  after:
  ```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
  ```
  ![img](2.png)
  - Briefly describe why the fix addresses the issue: it should return the `newArray` instead of `arr`, and inside the for loop, `newArray` is the one that needs to be assigned with values from `arr`

