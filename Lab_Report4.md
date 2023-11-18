- Log into ieng6
<img width="676" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/e03c8686-995a-48f9-983d-d52fcabed7f9">

key pressed: `<up>` `<enter>`

The `ssh cs15lfa23aw@ieng6.ucsd.edu` command was 1 up in the history so I used the up arrow to access it.

- Clone your fork of the repository from your Github account (using the SSH URL)
<img width="672" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/7488bcc5-ccfb-4499-bc96-a0c7e3da1b7c">

key pressed: `<up>` `<enter>`

The `git clone git@github.com:junyuelin/lab7.git` command was 1 up in the history so I used the up arrow to access it. 

- Run the tests, demonstrating that they fail
<img width="675" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/6e75a1a6-458b-4625-8e9b-1e0f559f472f">

key pressed: `cd lab7` `command-c` `<enter>` `command-v` `<enter>` `command-c` `<enter>` `command-v` `<enter>`

First I changed my directory to `lab7` folder, and then I copied `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` from the lab instruction. Then I pasted the command to my ieng6 terminal. I did the same for command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` It showed that the test failed. 

- Edit the code file to fix the failing test
<img width="385" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/52cb9529-7eb1-408a-b3df-502fa053864f">
<img width="380" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/8a3d8fa7-5ae7-4009-87ed-04f65a0e4166">
<img width="395" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/f8c1d729-6a47-4743-8563-5e275f26cb36">
<img width="377" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/077c2b25-5702-43cd-9242-3b0005adb514">

key pressed: `vim ListExamples.java` `:44` `<enter>` `<e>` `<r2>` `<enter>` `:wq!` `<enter>`

First I open the `ListExamples.java` file in Vim. And then `:44` to navigate the cursor to the line 44. Then `<e>` skips to the end of the first word. Then, `<r2>` to replace 1 with 2. Lastly, `:wq!` to force the write and quit.
- Run the tests, demonstrating that they now succeed
<img width="672" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/0cab6fa9-82d2-4e70-9855-bea81924ccfc">

key pressed: `command-c` `<enter>` `command-v` `<enter>` `command-c` `<enter>` `command-v` `<enter>`

I copied `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` from the lab instruction. Then I pasted the command to my ieng6 terminal. I did the same for command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
- Commit and push the resulting change to your Github account (you can pick any commit message!)
