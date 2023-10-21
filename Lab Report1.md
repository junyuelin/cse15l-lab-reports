Create a new file named index.md for lab1 in CSE 15L.

**Lalala**

# Lab Report 1 - Remote Access and FileSystem


For each of the commands `cd`, `ls`, and `cat`, and using the workspace you created in this lab:

Share an example of using the command with no arguments.
Share an exmaple of using the command with a path to a directory as an argument.
Share an example of using the command with a path to a file as an argument.

What the working directory was when the command was run?
A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
Indicate whether the output is an error or not, and if it’s an error, explain why it’s an error.

<img width="509" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/b6276b5b-e7ec-4f77-a457-dff039374e40">

for `cd`,

with no argument: The working directory is home. If we run `cd`, by default, it will go to the /home directory. There is no additional output from the command. The command just directs me to the specific directory, in this case, home. No error. 

with a path to a directory as an argument: The working directory is lecture1, because the cd command directs me to this directory. No additional output. No error. 

with a path to a file as an argument: The working directory is lecture1. There is an error showing `bash: cd: Hello.java: Not a directory`. The error occurs because the argument of the `cd` command can only be a valid directory name. 

for `ls`,

with no argument: It will just show the files in the working directory. In my case, just the files in /home directory 

with a path to a directory as an argument: The working directory is /home. `ls lecture1` lists the file names in the lecture1 directory although it does not change the current directory. 

with a path to a file as an argument: `ls Hello.class` just lists the name of the file which is the argument. The working directory is lecture1.

<img width="733" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/e41a0ac1-60a7-4911-bedf-372c4dcf3cab">

for `cat`,

with no argument: Almost crash. It doesn't end. Don't do it again. I have to use control C to exit. The working directory is lecture1.

with a path to a directory as an argument: Outputs an error. `cat: lecture1: Is a directory`. So I guess `cat` cannot have a directory name as an argument. The working directory is /home. 

with a path to a file as an argument: Show the content in the file. The working directory is /home/lecture1.
