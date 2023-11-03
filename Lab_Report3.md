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

## Part 2 - Researching Commands
* Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

* For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
-example1:
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -r "Tuesday, September 11, 2001" *
chapter-1.txt:    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
```
* That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

* Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.
