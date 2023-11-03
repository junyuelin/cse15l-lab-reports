## Part 1 - Bugs
Choose one of the bugs from lab 4.

Provide:

* A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)


* An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)


* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)


* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)


Briefly describe why the fix addresses the issue.
```python
static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
```python
    @Test
    public void testReverseInPlace2() {
        int[] input1 = {3,2,1};
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{1,2,3}, input1);
    }
```
