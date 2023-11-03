## Part 1 - Bugs
Choose one of the bugs from lab 4.
```python
static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
Provide:
* A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
```python
 @Test
 public void testReverseInPlace2() {
     int[] input1 = {3,2,1};
     ArrayExamples.reverseInPlace(input1);
     assertArrayEquals(new int[]{1,2,3}, input1);
 }
```
* An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
```python
@Test
public void testReversed1() {
 int[] input1 = { };
 assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```
* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
<img width="1011" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/d241bc12-e697-4e5d-880d-ad612ae44fd7">
* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

before:
```python
static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
after:
```python
static void reverseInPlace(int[] arr) {
 for(int i = 0; i < arr.length/2; i += 1) {
   int temp = arr[i];
   arr[i] = arr[arr.length - i - 1];
   arr[arr.length - i - 1] = temp;
 }
}
```
Briefly describe why the fix addresses the issue.
The code initially changed the element starting from the left of the list with the element starting from the right, but failed to store the original element from the left, thus if we use the code to reverse array {3,2,1}, it will result in {1,2,1}. When the loop goes past the middle index, the result will become faulty. 
