**PART 1 - Debugging Scenario**
1. The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. (Don’t actually make the post! Just write the content that would go in such a post)
<img width="598" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/45817483-a9a1-4732-b1c6-5213f89a8ac4">

Student post: For some reason, my code doesn't pass the `testMerge2` test. Based on the output error, I am guessing there is something wrong with `merge` function on line 44. But I am not sure how to fix it. 
2. A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)

TA post: You are right that the error might occur on line 44. Maybe you can try take a look at the file content by using command `vim ListExamples.java` and see if you can locate the error.

3. Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
<img width="598" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/34eee9c5-248d-4468-99d9-8888e31b8361">
Student Post: Thanks for your help! Turns out I mistyped `index2` to `index1`. After I changed `index1` to `index2`, and run the bash script again I passed all the tests. 
<img width="340" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/795b0e2b-55d0-4625-a850-1952a5702f59">

4. At the end, all the information needed about the setup including:
- The file & directory structure needed
- <img width="858" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/ab94d7b8-120b-4d7f-a854-ea120e02bc81">
- The contents of each file before fixing the bug
- <img width="580" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/8857283c-a8da-47d2-8e67-596796d57fc8">
- <img width="846" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/1d13c175-a1d3-4f80-8515-71a43f4dc3b9">
- <img width="725" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/ece79458-dbfe-4f22-b6df-e853dcba4bad">
- The full command line (or lines) you ran to trigger the bug
- <img width="601" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/b082259d-697f-4028-9bb4-981d2f912d74">
- A description of what to edit to fix the bug
- changed `index1` to `index2`

**PART 2 - Reflection**

In a couple of sentences, describe something you learned from your lab experience in the second half of this quarter that you didn’t know before. It could be a technical topic we addressed specifically, something cool you found out on your own building on labs, something you learned from a tutor or classmate, and so on. It doesn’t have to be specifically related to a lab writeup, we just want to hear about cool things you learned!
